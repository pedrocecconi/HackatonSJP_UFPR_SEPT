# Roteiro da demo — 60 segundos (pitch de 1:20 a 2:20)

**Tela:** `http://localhost:3000/demo.html` (modo apresentação), em tela cheia (F11).
**Antes de subir ao palco:**
1. Rodar `resetar.bat`, depois `iniciar.bat`.
2. Deixar a tela grande em **Sistema antigo** e o celular em **Técnico**.
3. Escrever no campo Descrição do sistema antigo: "Ponto de rede da sala de vacina sem internet, computadores parados".

**Quem faz o quê:**
- Uma pessoa **fala**.
- Outra **clica**, de preferência quem mais ensaiou.
- Quem clica **não fala**, para não atrasar.

| Tempo | Clique (quem opera) | Fala (quem apresenta) |
|---|---|---|
| 0–6 s | **Sistema antigo** → **Gravar OS** | "A atendente registra o chamado **no sistema que a Prefeitura já usa**. Nada muda para ela." |
| 6–16 s | Aba **Gestor** → abrir a missão nova → **Aceitar sugestão** → **Atribuir e notificar** | "O chamado chega **por API**, com o mesmo número da OS. A IA sugere o tipo e a prioridade e **avisa o que falta perguntar**. E sugere a Bruna, porque **ela já está nessa UBS agora**: sem nova viagem. O gestor confere e atribui." |
| 16–26 s | Celular **Técnico**: tocar na missão → **Aceitar e ir ao local** → **Cheguei — check-in** → **Fazer check-in e iniciar** | "O técnico recebe **no celular, sem papel**. A gestão sabe que ele **saiu** e que **chegou**, e quem pediu recebe **'técnico a caminho'**, sem precisar ligar para o Help Desk." |
| 26–34 s | **Tenho um impedimento** → **Falta de material/peça** → **Registrar impedimento** | "Faltou material? Dois toques." |
| 34–40 s | **Gestor**: mostrar a faixa vermelha → **Impedimento resolvido** → OK | "O gestor vê na hora, com o aviso de que **é o 2º bloqueio por falta de material no mês**. Antes isso ficava parado, como os **151 chamados no estoque**. E o tempo bloqueado **não conta contra o técnico**." |
| 40–48 s | Celular **Técnico**: **Concluir missão** → texto → foto → **Concluir e enviar** | "Concluiu com foto. Mas **concluído não é resolvido**…" |
| 48–54 s | Celular → aba **Demandante** → **Sim, está resolvido** | "…quem pediu confirma e avalia. Só aí os pontos são liberados." |
| 54–60 s | **Sistema antigo** (mostrar FINALIZADO) → aba **Ranking** | "O status **volta sozinho para o sistema antigo**, e a equipe sobe no ranking. Tudo rodando **aqui, sem nuvem**, como exige a lei de soberania digital." |

## Dicas
- **Ensaiem com cronômetro.** Se passar de 60 s, cortem o check-in: usem "Já estou no local" no lugar de "Aceitar e ir ao local".
- O **texto do impedimento e da conclusão** pode ficar em branco ou curto ("Conector refeito"). Não digitem frases longas ao vivo.
- **Foto:** o tipo "Ponto de rede" **exige foto da entrega**, de propósito, porque é a evidência. Usem a imagem pronta `prototipo/docs/foto_exemplo.jpg` (copiem para a Área de Trabalho) e ensaiem o caminho até ela; leva uns 4 s. Se quiserem cortar esse tempo, na tela **Configuração** o gestor pode criar um tipo sem foto obrigatória. Mas mostrar a foto chegando ao demandante impressiona mais.
- Se algo travar: **não expliquem o erro**. Digam "deixa eu mostrar no vídeo" e passem o vídeo de reserva (`entregas/video_demo_MissaoSJP.mp4`, 63 s, já com legendas; deixem aberto numa aba).
- Se sobrar tempo na arguição, mostrem **"Simular queda do sistema" → Religar** (prova a fila de reenvio) e **Configuração → novo setor** (prova que é genérico).
