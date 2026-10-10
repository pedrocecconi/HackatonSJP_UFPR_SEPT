# Roteiro da demo — versão 2 (60 segundos, de 1:20 a 2:20)

A versão anterior está em `ROTEIRO_DEMO_v1.md`.

## Como vai ser apresentado

**A tela:**
- `http://localhost:3000/demo.html` (modo apresentação), em tela cheia (F11), no projetor.
- Ela mostra tudo de uma vez:
  - **à esquerda**, um celular (o técnico ou quem pediu);
  - **à direita**, a tela grande (sistema antigo, gestor ou ranking).
- Os botões no topo trocam o que aparece em cada lado. A banca nunca precisa trocar de janela.

**As pessoas:**
- **Quem fala** fica em pé, ao lado da tela, olhando para a banca. Aponta para a tela quando algo muda.
- **Quem clica** fica no notebook e **não fala**. Clica só quando ouvir a "deixa" (as palavras em **negrito** na coluna da fala).
- Uma terceira pessoa, se houver, segura o **vídeo de reserva** aberto numa aba.

**A frase de entrada** (quem fala, ainda no slide 5, antes do primeiro clique):
> "Vou mostrar ao vivo. À esquerda, o celular do técnico. À direita, o que a Prefeitura vê."

**Antes de subir ao palco:**
1. Rodar `resetar.bat`, depois `iniciar.bat`.
2. Deixar a tela grande em **Sistema antigo** e o celular em **Técnico**.
3. Já deixar escrito no campo Descrição do sistema antigo: "Ponto de rede da sala de vacina sem internet, computadores parados".
4. Copiar `prototipo/docs/foto_exemplo.jpg` para a Área de Trabalho.
5. **Microfone:** abrir o modo apresentação, fazer um teste do 🎤 e clicar em **Permitir** quando o navegador pedir. Assim o pedido não aparece no palco. Sem Whisper instalado, a fala de exemplo (marcada SIMULADO) aparece de qualquer jeito, e sem microfone também.
6. Abrir o vídeo de reserva (`entregas/video_demo_MissaoSJP.mp4`) numa aba.

---

## Clique a clique

| # | Tempo | Clique (quem opera) | O que a banca vê | Fala (quem apresenta) | O que isso prova |
|---|---|---|---|---|---|
| 1 | 0–6 s | Tela grande: **Sistema antigo** → **Gravar OS** | A OS nova aparece na lista do sistema antigo, com número | "A atendente registra **no sistema que a Prefeitura já usa**. Nada muda para ela." | Integração: não troca o sistema atual |
| 2 | 6–16 s | **Gestor** → abrir a missão nova → **Aceitar sugestão** → **Atribuir e notificar** | A missão chega ao painel com o mesmo número da OS. A caixa da IA sugere tipo, prioridade, o que falta perguntar e a técnica Bruna, "já está agora na UBS" | "O chamado chega **por API**, com o mesmo número, sem duplicar. A **IA** sugere a prioridade e avisa o que falta perguntar. E sugere a Bruna, porque **ela já está nessa unidade agora**: sem nova viagem. **Mas quem decide é o gestor.**" | IA com conferência humana e logística (menos viagem) |
| 3 | 16–26 s | Celular **Técnico**: tocar na missão → **Aceitar e ir ao local** → **Cheguei — check-in** → **Fazer check-in e iniciar** | O celular muda de "a caminho" para "em execução", com hora | "A missão chega **no celular, sem papel**. Ela toca em 'a caminho' e **quem pediu já recebe o aviso**, sem ligar para o Help Desk. **Chegou:** check-in com hora e local." | Papel zero, push, rastreabilidade e fim do "apagão" |
| 4 | 26–34 s | **Tenho um impedimento** → **Falta de material/peça** → **Registrar impedimento** | A missão fica vermelha no celular | "Faltou material? **Dois toques.** Antes, isso ficava no papel até o fim do dia." | Impedimento registrado na hora |
| 5 | 34–40 s | Tela grande: **Gestor** → mostrar a faixa vermelha → **Impedimento resolvido** → OK | Faixa vermelha no topo do painel com o motivo, o tempo parado e o aviso "2º bloqueio por falta de material no mês" | "O gestor vê **na hora**, e a IA avisa que é o **segundo no mês**: vira dado para compras. Hoje, chamado parado no estoque espera **153 dias**. E o tempo bloqueado **não conta contra o técnico**." | Gestão age no impedimento; gamificação justa |
| 6 | 40–50 s | Celular **Técnico**: **Concluir missão** → **🎤 Falar em vez de digitar** → (fala 2–3 s) → **⏹ Parar e transcrever** → foto → **Concluir e enviar** | A caixa roxa "IA organizou sua fala" mostra o que foi dito e o texto arrumado em feito / material / pendência. Depois, a missão vai para "concluída pelo executor", com a foto | "Ele **não digita: fala**, e a **IA local** escreve o relatório, com o material usado. Com **foto como evidência**. Mas **concluído não é resolvido**…" | IA de voz local, evidência, dado para compras |
| 7 | 50–55 s | Celular → aba **Demandante** → **Sim, está resolvido** → ★★★★★ | Quem pediu vê o histórico completo (a caminho, chegou, impedimento, foto) e confirma | "…**quem pediu confirma** e avalia. Só aí a missão está resolvida, e os pontos são liberados." | Validação pelo demandante |
| 8 | 55–60 s | Tela grande: **Sistema antigo** (mostrar FINALIZADO) → **Ranking e indicadores** | A OS no sistema antigo aparece como FINALIZADO. Depois, o ranking da equipe | "E o status **volta sozinho para o sistema da Prefeitura**. Tudo rodando **aqui, no datacenter, sem nuvem**: **soberania digital**." | Integração de volta e soberania digital |

**Saída da demo** (quem fala, voltando ao slide 6):
> "Isso foi um chamado. Agora multipliquem pelos quase 10 mil chamados de 2026."

---

## Dicas
- **Ensaiem com cronômetro.** Se passar de 60 s, cortem o passo 3: usem "Já estou no local" no lugar de "Aceitar e ir ao local".
- **Ranking:** a tela mostra pontos somados por missão. Não comentem o número. Se perguntarem, respondam: "a régua é configurável; para o piloto, a proposta é pontuar qualidade, não volume".
- **Textos curtos:** na conclusão, usem o 🎤 em vez de digitar. Se o microfone falhar, a IA usa a fala de exemplo. No impedimento, deixem o detalhe em branco.
- **Foto:** o tipo "Ponto de rede" exige foto, de propósito, porque é a evidência. Ensaiem o caminho até `foto_exemplo.jpg` na Área de Trabalho (cerca de 4 s).
- **Se algo travar:** não expliquem o erro. Digam "deixa eu mostrar no vídeo" e passem o vídeo de reserva (63 s, com legendas).
- **Se sobrar tempo na arguição:**
  - **Mapa** (celular → aba 🗺️ Mapa): mostra a geolocalização, o "mais perto de você" e km e minutos até a missão;
  - **"Simular queda do sistema" → Religar**: prova a fila de reenvio;
  - **Configuração → novo setor**: prova que é modular e se adapta a outras áreas.
