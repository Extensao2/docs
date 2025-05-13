## **O que Tracking?**
O Tracking funciona como o "sentido" da plataforma, monitorando todas as interações dos usuários. Ele registra ações importantes como:

- Assistir vídeo

- Pausar vídeo

- Finalizar quiz/prova

- Inatividade prolongada

Esses eventos são registrados automaticamente e enviados do frontend para a API do tracking, permitindo que a IA monitore e compreenda o comportamento do aluno. Exemplo de captura de evento no JavaScript:

`
videoElement.addEventListener('play', function() {
  sendEvent('started_video');
});
`

Com base nesses dados, a IA pode entender o engajamento do aluno, suas dificuldades ou até prever quando ele está prestes a desistir.

## **Tecnologias Utilizadas**

**FastAPI (Python):** Framework leve e rápido para construir APIs RESTful.

**JavaScript (Frontend):** Responsável por capturar eventos no navegador e enviar para a API via fetch.

## **Para que Tudo Isso Serve?**

- Aprender as preferências do aluno: O que ele gosta ou evita.

- Sugerir o conteúdo certo no momento certo: Propor novas atividades de acordo com o comportamento.

- Detectar sinais de desmotivação: A IA pode agir antes que o aluno desista.

- Criar uma experiência personalizada: Oferecendo uma mentoria ativa e estratégica, em vez de apenas uma assistente passiva.
