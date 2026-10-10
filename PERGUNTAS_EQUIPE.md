# Decisões para o time tomar às 8h30 (em 15 minutos)

*Cada item traz a minha recomendação. Se ninguém tiver argumento melhor em 1 minuto, fica a recomendação. Anotem a decisão na seção 6 do `CONTEXTO_HACKATHON.md`.*

| # | Pergunta | Recomendação | Por quê |
|---|---|---|---|
| 1 | **Nome da solução** | **Missão SJP** (já está no protótipo) | Curto, liga ao desafio ("jornada de missões") e à cidade. Se quiserem outro, trocar leva 5 min (texto em `public/*.html`). |
| 2 | **Feature da VRIO** (bloco 2, "uma só") | **Impedimento visível na hora, sem punir o técnico** | É a que tem evidência forte nos dados (151 chamados no estoque, OS 14142) e é a que aparece na demo. A alternativa "setor novo sem programar" está pronta no fim do `MATRIZ_VRIO.md`. |
| 3 | **Instalar a IA local (Ollama) no notebook da demo?** | **Sim, se alguém tiver internet boa até as 10h.** Senão, deixar o modo reserva e falar a frase pronta. | 20% da nota é "dados e IA". Mostrar um LLM local de verdade vale pontos. Instalação: ollama.com, depois **dois cliques em `prototipo/verificar_ia.bat`** (baixa o modelo de cerca de 2 GB, aquece e testa). Testar com a tela Atendente → "Analisar com IA": o motor deve aparecer como "LLM local". **A primeira análise demora** (o modelo carrega na memória): façam uma análise de aquecimento 5 min antes de subir ao palco. |
| 4 | **Quem apresenta o pitch?** | **Uma pessoa** fala; **outra** clica na demo | Quem clica não fala, para não perder tempo. Todos sobem: integrante ausente na banca perde pontos. |
| 5 | **Quem responde o quê na arguição?** | Dividir por tema: **integração, fila e soberania**; **gamificação, servidor e orçamento**; **IA e dados**; **telas e usabilidade**. Uma pessoa por tema. | A banca pode perguntar a qualquer um. Cada pessoa lê as 18 respostas do `MAPA_DO_PITCH.md` da sua área. |
| 6 | **Valores dos pontos** (10/25/50, +10 avaliação, +5 impedimento, 50% colaboração) | **Manter** | São os números da síntese da SIMOT (10/25/50). Dá para mostrar que mudam na tela Configuração. |
| 7 | **Ranking individual visível para todos?** | **Equipe em destaque, individual discreto** (como está) | Incentiva sem desanimar quem está embaixo. O técnico vê o próprio progresso e as medalhas. |
| 8 | **Demo ao vivo ou vídeo?** | **Ao vivo no modo apresentação, com o vídeo de reserva aberto** em outra aba | Ao vivo impressiona. O vídeo salva se a rede ou o notebook falharem. |
| 9 | **Celular de verdade na demo?** | **Não**, usar o celular dentro do modo apresentação | O push real exige HTTPS ou a configuração da flag do Chrome, que é risco desnecessário. Se alguém testar e funcionar até as 12h, mostrar como extra na arguição. |
| 10 | **Usar as telas estáticas da outra versão** (login com e-mail e senha, brasão)? | **Não no protótipo de hoje.** Mostrar aquele login como "próximo passo" se perguntarem | O brasão é símbolo oficial do Município: usar só com autorização da organização. O login real entra na integração com o diretório da Prefeitura. |
| 11 | **Link do protótipo na Entrega 3** | **A vitrine publicada** (vídeo da demo, telas, 7 requisitos, como rodar): `claude.ai/artifact/RR94ofArDEcseEjKpv8RdP`. **É preciso liberar o acesso no menu Compartilhar** (link público) antes de enviar. Se preferirem, pasta compartilhada com `prototipo/` + vídeo. | O formulário pede "link". A vitrine mostra o protótipo rodando, mesmo para quem não for instalar. Já está no canvas da VRIO preenchido. |
| 12 | **Congelar o código às 10h?** | **Sim** | Depois disso, só correção de erro. Mudança de última hora quebra a demo. |

## Perguntas para alinhar entre vocês (5 min)
- Todo mundo consegue explicar, em 1 frase, **o que é a fila de integração** e **por que o técnico não fecha sozinho**?
- Todo mundo sabe dizer **de onde vêm os 2 números do pitch**?
- Quem ficou com cada mentor (ver `PERGUNTAS_MENTORES.md`) e até que horas trazem as respostas?
- Quem grava o vídeo de reserva, e onde ele fica salvo (pendrive + celular)?
