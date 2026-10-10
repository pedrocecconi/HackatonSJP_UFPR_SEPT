# Checklist do protótipo — antes da Entrega 3 (13h20) e da banca (15h40)

*Para qualquer pessoa do time, mesmo sem conhecimento técnico. Marque `[x]` conforme for testando. Se algo falhar, anote na seção F e avise quem cuida do código.*

---

## A. Preparar o notebook da demo (uma vez, de manhã)
- [ ] Node.js instalado: abra o "Prompt de Comando" e digite `node -v`. Deve aparecer **v22.13 ou maior**. Se não aparecer, instale o Node.js **LTS** em nodejs.org.
- [ ] Pasta `prototipo` copiada para o notebook. Se rodar de dentro do OneDrive, tudo bem: o `iniciar.bat` guarda os dados fora dele.
- [ ] Dois cliques em **`resetar.bat`** e confirme. Isso volta aos dados iniciais.
- [ ] Dois cliques em **`iniciar.bat`**. Abre uma janela preta (o servidor) e o navegador no **modo apresentação**. **Não feche a janela preta.**
- [ ] Se o Windows perguntar sobre o firewall, clique em **Permitir** (necessário para o celular acessar).
- [ ] Abra `http://localhost:3000/api/saude`. Deve aparecer `"ok":true`.
- [ ] **(Só se forem usar a IA local)** Rodar `verificar_ia.bat`, que instala o modelo, aquece e testa. Ou, manualmente: abrir a tela Atendente, escrever qualquer problema e clicar em **Analisar com IA**. O motor deve aparecer como "LLM local (qwen2.5:3b via Ollama)". A 1ª vez demora: repitam 5 min antes da banca para o modelo ficar carregado.
- [ ] Carregador do notebook na tomada; modo de suspensão desligado; notificações do Windows em "Não perturbe".
- [ ] Navegador em tela cheia (F11) e zoom em 100% (Ctrl+0). Se o projetor for de baixa resolução, teste zoom de 90% (Ctrl e −).

## B. Ensaio do fluxo completo (modo apresentação), cerca de 2 min
*Abas no topo: "Celular" (Técnico/Demandante) e "Tela grande" (Sistema antigo, Gestor…).*
- [ ] **Tela grande → Sistema antigo**: clicar em **Gravar OS**. Aparece a mensagem "Enviada à Plataforma de Missões".
- [ ] **Tela grande → Gestor**: a missão nova aparece em "Abertas", com a etiqueta **OS 200xx** e **IA: conferir**.
- [ ] Abrir a missão: o quadro roxo **Sugestão da IA** mostra tipo, prioridade e o que falta. Clicar em **Aceitar sugestão**.
- [ ] No mesmo quadro: a técnica **Bruna Barros** já vem marcada como **"— sugerido"** ("já está agora na UBS Jardim Exemplo"). É ela que está no celular da tela. Modalidade **Presencial**. Clicar em **Atribuir e notificar**.
- [ ] **Celular (Técnico)**: aparece o aviso azul **🔔 Nova missão**. A missão aparece na lista.
- [ ] Tocar na missão, depois em **🚗 Aceitar e ir ao local**. O estado muda para **A caminho**.
- [ ] Tocar em **📍 Cheguei — fazer check-in**, depois em **Fazer check-in e iniciar** (a foto é opcional).
- [ ] Marcar um item do checklist.
- [ ] Tocar em **⛔ Tenho um impedimento**, depois em **Falta de material/peça** e **Registrar impedimento**.
- [ ] **Gestor**: a faixa **vermelha** no topo mostra a missão bloqueada, há quanto tempo e "o tempo bloqueado não conta contra o técnico". Aparece o aviso de **impedimento recorrente**.
- [ ] Clicar em **Impedimento resolvido** e confirmar o texto.
- [ ] **Celular (Técnico)**: tocar em **✔ Concluir missão**, escrever o que foi feito, anexar uma foto (qualquer imagem) e tocar em **Concluir e enviar para confirmação**.
- [ ] **Celular → aba Demandante**: aparece o cartão amarelo **"O técnico concluiu. O problema foi resolvido?"** com a foto. Deixar 5 estrelas e tocar em **✔ Sim, está resolvido**.
- [ ] **Tela grande → Sistema antigo**: em até 5 s, a OS fica **FINALIZADO** e os andamentos mostram "(via Plataforma de Missões)".
- [ ] **Tela grande → Ranking e indicadores**: os pontos da Bruna subiram.
- [ ] **Celular (Técnico) → Meu progresso**: aparecem os pontos, as medalhas ("Desbloqueador") e o extrato.

## C. Provas extras para a arguição (cerca de 1 min cada)
- [ ] **Sem duplicados:** no Sistema antigo, clicar em **Reenviar** numa OS. A mensagem diz "já existia, nenhum registro duplicado criado".
- [ ] **Falha de conexão:** no Sistema antigo, clicar em **Simular queda do sistema**. No Gestor, atribuir outra missão. Em **Integração**, aparece "⏳ Na fila". Clicar em **Religar sistema**: em até 5 s fica "✅ Entregue" e o Sistema antigo mostra o andamento.
- [ ] **Genérico:** em **Configuração**, criar o setor "Jardinagem", o tipo "Poda de árvore" (complexidade 3, checklist, palavras-chave "árvore, galho, poda"). Em **Atendente**, escrever "galho caiu na calçada" e clicar em **Analisar com IA**: a IA sugere o tipo novo.
- [ ] **Pendência:** concluir outra missão; no Demandante, tocar em **Ainda tem pendência**. A missão volta para o técnico como **Reaberta**.
- [ ] **Avanço parcial:** com uma missão em execução, o técnico move a barra "Avanço da missão" para 40%. No Gestor, abrir a missão e clicar em **Validar avanço de 40%**. Saem pontos proporcionais.
- [ ] **Permissões:** entrar como Demandante pelo início (`localhost:3000`). Não existe opção de abrir tarefa nem de ver missões de outros.
- [ ] **Mapa:** no **Celular (Técnico)**, tocar na aba **🗺️ Mapa** (embaixo). Aparecem as unidades com missões (cor = estado mais urgente), o ponto azul **"Você"** e o cartão verde de missão na mesma unidade. Tocar numa missão da lista **"Mais perto de você"**: o mapa traça o caminho com **km e minutos**. No **Gestor**, abrir **"🗺️ Mapa da operação"** e tocar num pino. Frase pronta: *"o mapa é desenhado pelo próprio sistema, sem Google Maps: nada sai do datacenter"*.

## D. Celular de verdade (opcional, só se sobrar tempo)
- [ ] Notebook e celular na **mesma rede Wi-Fi**. No notebook: `ipconfig` e anotar o "Endereço IPv4" (ex.: 192.168.0.15).
- [ ] No celular, abrir `http://192.168.0.15:3000` e entrar como **Bruna Barros** (técnica).
- [ ] Para o push **do sistema** (com a tela bloqueada) no **Android/Chrome**: abrir `chrome://flags/#unsafely-treat-insecure-origin-as-secure`, colar `http://192.168.0.15:3000`, mudar para **Enabled**, **Relaunch**. Voltar ao app e tocar em **🔔 Notificações**, depois em **Permitir**.
- [ ] Atribuir uma missão para a Bruna no notebook. A notificação chega no celular.
- [ ] **Se não funcionar em 10 minutos, desistam:** o modo apresentação já mostra o aviso em tempo real. Não gastem a manhã nisso.

## E. Plano B (internet ou notebook falharam)
- [ ] **O protótipo não precisa de internet.** Tudo roda no notebook (`localhost`). Só o push no celular depende da rede.
- [x] **Vídeo de reserva pronto:** `entregas/video_demo_MissaoSJP.mp4` (63 s, com legendas). Copiar para o pendrive **e** para o celular. Se quiserem gravar um com a voz de vocês: **Win + Alt + R** (Xbox Game Bar).
- [ ] Capturas de tela em `prototipo/docs/telas` (já prontas) e slides em PDF no pendrive.
- [ ] Segundo notebook com o protótipo instalado e testado (seção A).
- [ ] Se travar no meio: fechar a janela preta, `iniciar.bat` de novo. Não precisa resetar; os dados ficam salvos.

## F. Problemas encontrados
| Hora | O que aconteceu | Quem viu | Resolvido? |
|---|---|---|---|
| | | | |

## G. Congelamento
- [ ] **10h00: código congelado.** Depois disso, só correção de erro que impeça a demo.
- [ ] **12h–13h: demo ensaiada 3 vezes** com cronômetro (≤ 60 s) e vídeo de reserva gravado.
- [ ] **13h20:** Entrega 3 enviada pelo QR code da mesa (link ou pasta do protótipo + Matriz VRIO).
