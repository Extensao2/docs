### **Envio para a API**
Quando o usuário interage com o frontend, como ao clicar para assistir a um vídeo ou pausá-lo, um evento é disparado no JavaScript e enviado para a API FastAPI usando o método POST com o evento e seus detalhes. Por exemplo, ao clicar em "play", a API recebe o evento started_video.

O frontend envia os seguintes tipos de eventos para o backend:

**started_video:** Quando o vídeo começa a ser assistido.

**paused_video:** Quando o vídeo é pausado.

**completed_video:** Quando o vídeo é finalizado.

**completed_quiz:** Quando o quiz é respondido.

**inactive_too_long:** Quando o usuário fica inativo por um período definido.

Esses eventos são armazenados no log e podem ser usados para análise futura.

### **Possibilidades de Consulta com IA**
Com os dados dos logs (eventos registrados), é possível utilizar a IA Mentora para analisar o comportamento do usuário e gerar recomendações ou insights. Algumas possibilidades incluem:

**Recomendações de Conteúdo:** A IA pode sugerir novos vídeos ou provas baseados nos conteúdos que o usuário mais interage.

**Detecção de Desmotivação:** Se a IA perceber que o usuário está pausando frequentemente vídeos ou demorando para terminar o conteúdo, ela pode sugerir formas alternativas de aprendizado.

**Personalização do Percurso de Estudo:** Com base no histórico de interações, a IA pode criar um plano de estudo adaptativo, ajustando-se conforme as preferências do aluno.

Além disso, a IA pode antecipar problemas (como um possível abandono) com base no comportamento observado nos eventos, agindo de forma proativa para engajar o usuário novamente.
