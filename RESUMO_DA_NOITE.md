# Resumo da noite — o que foi feito (madrugada de 10/10)

## ☀️ Faça primeiro ao acordar (15 min)
1. **Teste o protótipo novo no seu notebook.** `prototipo\resetar.bat`, depois `prototipo\iniciar.bat`. Abre o **modo apresentação**. Siga a seção B do `CHECKLIST_PROTOTIPO.md`. É preciso Node.js 22.13 ou mais novo (`node -v`).
2. **Leia o `PERGUNTAS_EQUIPE.md`** e leve para a reunião das 8h30: são 12 decisões, cada uma com recomendação.
3. **Imprima ou abra no celular o `PERGUNTAS_MENTORES.md`** e distribua as perguntas. A mais importante: *qual é o nome do sistema do Help Desk?*
4. **Confirme com a equipe do Help Desk se a OS 14142 ainda está aberta.** Ela é o gancho do pitch.

## O que está pronto em `entregas/`
| Arquivo | Para quê |
|---|---|
| `Pitch_MissaoSJP.pptx` e `.pdf` | **Entrega 4**: 8 slides com capturas reais do protótipo e falas nas notas do apresentador |
| `MATRIZ_VRIO.md` | **Entrega 3**: VRIO pronta (falta só o link e o resultado do ensaio de sábado) |
| `MAPA_DO_PITCH.md` | Roteiro de 3 min nos tempos do canvas + **18 perguntas prováveis da banca** com respostas de até 20 s + como os números foram calculados |
| `ROTEIRO_DEMO.md` | Os cliques exatos e a fala da demo de 60 s |
| `CHECKLIST_PROTOTIPO.md` | Verificação passo a passo para quem não é técnico + plano B |
| `REVISAO_PROTOTIPO.md` | Revisão crítica: o que mudou, aderência aos 7 requisitos, pontos fracos priorizados, autoavaliação pelos critérios da banca |
| `PERGUNTAS_MENTORES.md` | Resumo do que os mentores disseram ontem + perguntas por área |
| `PERGUNTAS_EQUIPE.md` | Decisões para a reunião das 8h30 |
| `DECISOES.md` | Tudo o que decidi sozinho, e como desfazer |
| `TRANSCRICOES_MENTORES.md` | Transcrição automática dos 5 áudios (com erros; só como lembrete) |

## O que mudou no protótipo (versão 0.2.0)
Backup da versão anterior: `prototipo_backup_0422`. **Teste automático: 27 de 27 verificações aprovadas, sem erros nas telas.** O protótipo também foi testado rodando direto da sua pasta.

- **Modo apresentação** (`demo.html`): celular do técnico/demandante + gestor/sistema antigo numa tela só.
- Alinhado ao **fluxo do Lucidchart do time:**
  - estado "a caminho" e check-in com foto;
  - modalidade presencial, remota ou por telefone;
  - sugestão de técnico;
  - aviso ao almoxarifado/compras.
- Alinhado ao **que os mentores disseram:**
  - **rastreio em tempo real para o demandante** ("técnico a caminho"), contra o "apagão operacional";
  - sugestão de técnico **que já está na mesma unidade**;
  - **deslocamento medido à parte**;
  - alerta de **impedimento recorrente**.
- Alinhado à **síntese da SIMOT:**
  - **pontos proporcionais a avanço parcial validado**;
  - a prioridade ordena a lista do técnico.
- **Correções:**
  - um técnico via missões de colegas com número parecido;
  - os dados agora ficam **fora do OneDrive** para não travar o banco;
  - `iniciar.bat` checa o Node, e há o novo `resetar.bat`;
  - endpoint `/api/saude`;
  - migração automática do banco.
- **Técnica da demo agora é a Bruna:** a IA sugere ela, porque já está na mesma UBS.

## O que ficou pendente (precisa de vocês)
- [ ] **IA rodando de verdade:** instalar o Ollama + `qwen2.5:3b` no notebook da demo, se der tempo até as 10h. Sem ele, a tela mostra "modo reserva — SIMULADO".
- [ ] **Push no celular de verdade:** opcional e arriscado (exige HTTPS ou a flag do Chrome). O modo apresentação já mostra o aviso.
- [ ] **Docker** não foi testado (não havia Docker no ambiente). Se alguém tiver, rodar `docker compose up --build` uma vez.
- [ ] **Link do protótipo** na VRIO e **resultado do ensaio** no bloco 3.
- [ ] **Vídeo de reserva** de 60 s da demo (Win + Alt + R).
- [ ] Ajustar o pitch com o que os mentores responderem de manhã.

## Decisões que tomei sem vocês (detalhes em `DECISOES.md`)
- Não usei o brasão nem as telas estáticas da outra versão no protótipo funcional (símbolo oficial; login entra como próximo passo).
- Feature da VRIO: **impedimento visível na hora** (a alternativa "setor novo sem programar" está pronta no fim do arquivo).
- Pitch com só 2 números: "3 em cada 4 em lote" e "151 chamados / 153 dias no estoque".
