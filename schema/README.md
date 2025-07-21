# Current Database Structure Documentation

## Overview

This document describes the current MongoDB database structure as implemented in the codebase. The system is designed as a university extension platform with user authentication, resource management, and event tracking capabilities.

## Database Collections

### 1. Users Collection

**Collection Name:** `users`

**Schema Structure:**
```javascript
{
  _id: ObjectId,
  email: {
    type: String,
    required: true,
    lowercase: true,
    trim: true
  },
  name: {
    type: String,
    required: true,
    trim: true
  },
  role: {
    type: String,
    enum: ['user', 'admin'],
    default: 'user'
  },
  oauthProvider: {
    type: String,
    required: true
  },
  oauthId: {
    type: String,
    required: true
  },
  createdAt: Date,
  updatedAt: Date
}
```

**Indexes:**
- `{ email: 1 }` - Unique index for email lookup
- `{ oauthProvider: 1, oauthId: 1 }` - Compound index for OAuth authentication

**Key Features:**
- Google OAuth integration for authentication
- Role-based access control (user/admin)
- Automatic timestamp management
- Email normalization (lowercase, trimmed)

### 2. Resources Collection

**Collection Name:** `resources`

**Schema Structure:**
```javascript
{
  _id: ObjectId,
  title: {
    type: String,
    required: true,
    trim: true,
    maxlength: 200
  },
  content: {
    type: String,
    required: true
  },
  createdBy: {
    type: String,
    required: true,
    ref: 'User'
  },
  createdAt: Date,
  updatedAt: Date
}
```

**Indexes:**
- `{ title: 'text' }` - Text search index for title content
- `{ createdBy: 1 }` - Index for user resource queries
- `{ createdAt: -1 }` - Index for chronological ordering

**Key Features:**
- Base64 encoded content storage
- Full-text search capabilities
- User ownership tracking
- Automatic timestamp management

### 3. Events Collection

**Collection Name:** `events`

**Schema Structure:**
```javascript
{
  _id: ObjectId,
  nome: {
    type: String,
    required: true,
    trim: true,
    maxlength: 150
  },
  data: {
    type: Date,
    required: true
  },
  descricao: {
    type: String,
    required: true,
    trim: true
  },
  userId: {
    type: String,
    required: true,
    ref: 'User'
  },
  createdAt: Date,
  updatedAt: Date
}
```

**Indexes:**
- `{ userId: 1 }` - Index for user event queries
- `{ data: -1 }` - Index for chronological ordering
- `{ nome: 'text', descricao: 'text' }` - Text search index

**Key Features:**
- Event scheduling and management
- User association for event ownership
- Text search across name and description
- Chronological ordering capabilities

## Database Connection Configuration

**Connection String Format:**
```
mongodb://${MONGO_USER}:${MONGO_PASS}@${MONGO_HOST}:${MONGO_PORT}/${MONGO_DB_NAME}?authSource=admin
```

**Fallback Connection:**
```
mongodb://localhost:27017/sistema-aprendizagem
```

**Connection Options:**
- `maxPoolSize: 10` - Maximum connection pool size
- `serverSelectionTimeoutMS: 5000` - Server selection timeout
- `socketTimeoutMS: 45000` - Socket timeout
- `connectTimeoutMS: 10000` - Connection timeout

## Authentication System

### JWT Token Structure
```javascript
{
  sub: string,        // User ID
  email: string,      // User email
  name: string,       // User name
  iss: string,        // Issuer (sistema-aprendizagem)
  aud: string,        // Audience (api-users)
  exp: number,        // Expiration time
  iat: number         // Issued at time
}
```

### OAuth Integration
- Google OAuth token verification
- Automatic user creation on first login
- Internal JWT generation for API access

## API Endpoints and Data Flow

### Authentication Routes
- `POST /api/v1/login` - OAuth token validation and user authentication

### Resource Management Routes
- `PUT /api/v1/admin/resource` - Create new resource (admin only)
- `PATCH /api/v1/admin/resource/:resource_id` - Update resource (admin only)
- `DELETE /api/v1/admin/resource/:resource_id` - Delete resource (admin only)
- `GET /api/v1/resource/:resource_id` - Get specific resource
- `GET /api/v1/resources/search` - Search resources with pagination

### Event Management Routes
- `GET /api/v1/events` - Get all events
- `GET /api/v1/admin/events/:user_id` - Get events by user (admin only)

## Data Validation Rules

### Input Validation Schemas
```javascript
// Login validation
{
  token: Joi.string().required()
}

// Resource creation validation
{
  title: Joi.string().max(200).required(),
  content: Joi.string().required()
}

// Resource update validation
{
  title: Joi.string().max(200).optional(),
  content: Joi.string().optional()
}

// Search validation
{
  title: Joi.string().optional(),
  page: Joi.number().integer().min(0).default(0),
  size: Joi.number().integer().min(1).max(100).default(10)
}
```

## Environment Variables Required

```bash
# MongoDB Connection
MONGO_USER=your_username
MONGO_PASS=your_password
MONGO_HOST=your_host
MONGO_PORT=27017
MONGO_DB_NAME=your_database

# JWT Configuration
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=24h

# Application Configuration
PORT=3000
NODE_ENV=development
CORS_ORIGIN=*
```