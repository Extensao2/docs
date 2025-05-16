## 📦 Estrutura Padrão de Evento

Todos os eventos registrados devem seguir esta estrutura JSON:

```json
{
  "event_type": "nome_do_evento",
  "user_id": "user-123",
  "session_id": "sess-abc456",
  "timestamp": "2025-05-16T21:00:00Z",
  "metadata": {
    // Dados específicos do evento
  },
  "context": {
    "platform": "web",
    "device": "desktop",
    "browser": "Chrome",
    "user_agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64)",
    "language": "pt-BR"
  }
}
```

### 🧩 Descrição dos Campos

| Campo         | Tipo     | Obrigatório | Descrição                                                                 |
|---------------|----------|-------------|---------------------------------------------------------------------------|
| `event_type`  | string   | ✅           | Nome do evento que está sendo registrado                                 |
| `user_id`     | string   | ✅           | ID único do usuário                                                       |
| `session_id`  | string   | ✅           | ID da sessão atual                                                        |
| `timestamp`   | string   | ✅           | Data e hora do evento                                 |
| `metadata`    | objeto   | ✅           | Dados específicos do evento (varia conforme o tipo)                      |
| `context`     | objeto   | ✅           | Informações do ambiente e dispositivo do usuário                         |

---

## 📂 CLASSIFICAÇÃO DOS TIPOS DE EVENTOS

### 🎥 EVENTOS DE VÍDEO

| `event_type`         | Descrição                              | `metadata`                                                      |
|----------------------|----------------------------------------|------------------------------------------------------------------|
| `started_video`      | Vídeo iniciado                         | `video_id`, `current_time`                                       |
| `paused_video`       | Vídeo pausado                          | `video_id`, `current_time`                                       |
| `completed_video`    | Vídeo assistido até o fim              | `video_id`, `total_time`                                         |
| `replayed_video`     | Vídeo reiniciado do zero               | `video_id`, `from_time`                                          |
| `abandoned_video`    | Vídeo encerrado antes do fim           | `video_id`, `watched_duration`, `video_length`                   |
| `seeked_video`       | Avanço ou retrocesso manual            | `video_id`, `from_time`, `to_time`                               |
| `rewatched_segment`  | Trecho foi assistido repetidamente     | `video_id`, `start_time`, `end_time`, `times_rewatched`          |
| `video_playback_pattern` | Dados objetivos do padrão de consumo | `video_id`, `avg_speed`, `pause_count`, `skip_segments`          |
| `focused_watch`      | Vídeo assistido ininterruptamente      | `video_id`, `duration`                                           |

---

### 📄 EVENTOS DE TEXTO

| `event_type`         | Descrição                               | `metadata`                                                              |
|----------------------|-----------------------------------------|-------------------------------------------------------------------------|
| `started_reading`    | Início de leitura de um conteúdo textual | `text_id`                                                               |
| `scrolled_text`      | Scroll detectado durante leitura        | `text_id`, `scroll_depth`, `scroll_speed`, `paused_sections`            |
| `completed_reading`  | Scroll até o fim com tempo mínimo       | `text_id`, `read_duration`                                              |
| `abandoned_reading`  | Saída antes de terminar a leitura       | `text_id`, `last_position`, `read_duration`                             |
| `highlighted_text`   | Texto destacado pelo aluno              | `text_id`, `highlighted_text`, `start_offset`, `end_offset`             |
| `reading_loop`       | Trecho foi revisitado                   | `text_id`, `revisited_sections`                                         |

---

### 🌐 EVENTOS GERAIS

| `event_type`         | Descrição                                            | `metadata`                                                            |
|----------------------|-----------------------------------------------------|-----------------------------------------------------------------------|
| `inactive_too_long`  | O usuário ficou inativo por muito tempo             | `inactive_duration`                                                  |
| `inactivity_detected`| Inatividade temporária detectada                    | `duration`, `trigger_point`                                          |
| `hovered_doubt_zone` | Hover em área sensível (ex: termos complexos)       | `element_id`, `hover_duration`                                       |
| `revisited_content`  | Conteúdo acessado novamente após já ter sido finalizado | `content_type`, `content_id`, `last_accessed`                    |
| `distraction_signal` | Mudança de aba, foco perdido                        | `event_source` (ex: "blur", "visibilitychange")                      |
| `page_viewed`        | Página foi acessada                                 | `page_id`, `referrer`                                                |
| `search_performed`   | Pesquisa realizada                                   | `query`, `results_count`                                             |

---