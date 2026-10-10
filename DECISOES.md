# Decisões tomadas na madrugada de 10/10 (a confirmar com o time)

*Toda decisão aqui pode ser revertida. Quando houver dúvida, a regra foi escolher o mais simples e seguro para a demo.*

| # | Decisão | Motivo | Como desfazer |
|---|---|---|---|
| 1 | **Backup** do protótipo antes de mexer: `prototipo_backup_0422` | Regra de não quebrar o que funciona | Copiar a pasta de volta |
| 2 | **Alinhei o protótipo ao fluxo do Lucidchart do time** ("Modelo de Fluxo de Processos de Negócios.json"): estado "a caminho", check-in com foto inicial, modalidade presencial/remoto/telefone, sugestão de técnico e aviso a compras | O fluxo foi desenhado pelo time e cobre perguntas do Manual ("o técnico chegou?") | — |
| 3 | **Não usei o brasão** do Município nem as telas estáticas da outra versão no protótipo funcional | O brasão é símbolo oficial: usar só com autorização da organização. Essas telas são estáticas; as funções delas (abrir chamado, painel, ranking, sugestão de IA) já existem no protótipo funcional. Login com senha fica como próximo passo. | Decisão do time na reunião das 8h30 (`PERGUNTAS_EQUIPE.md`, item 10) |
| 4 | **Sem IA de voz** (decisão do time). A IA do produto é: triagem (tipo, prioridade, informação faltante), sugestão de técnico e alerta de impedimento recorrente | Cumpre o requisito 6 de forma simples, local e com conferência humana | — |
| 5 | **Pontos parciais** proporcionais ao avanço validado pelo gestor | Pedido literal da síntese da SIMOT (03/10) | Regra pode ser ignorada; não muda o fluxo principal |
| 6 | **Técnica da demo passou a ser a Bruna** (antes, Tiago) | Com a nova regra "quem já está na mesma unidade", a sugestão da IA aponta a Bruna, que está atendendo na mesma UBS. Fica mais natural na demo: aceitar a sugestão sem trocar o técnico. | Em `public/demo.html`, trocar `['Técnico', 4, ...]` por `3` |
| 7 | **Dados do servidor fora do OneDrive** (`%LOCALAPPDATA%\MissaoSJP`) no `iniciar.bat` | A sincronização do OneDrive pode travar ou corromper o SQLite | Definir `PASTA_DADOS` antes de rodar |
| 8 | **Feature da VRIO = impedimento visível na hora** (alternativa "setor novo sem programar" deixada pronta) | Mais evidência nos dados e é o centro da demo | Trocar o bloco 2 pelo texto do fim do `MATRIZ_VRIO.md` |
| 9 | **Pitch com só 2 números** ("3 em cada 4" em lote; "151 / 153 dias" no estoque) | Recomendação do Mapa do Pitch: no máximo 2 números | — |
| 10 | Deck em **.pptx + PDF, 8 slides**, com capturas reais do protótipo | Entrega 4 pede PDF de no máximo 8 slides; o .pptx permite editar | Editar o .pptx e exportar PDF de novo |
| 11 | Não instalei o Ollama nem testei Docker | Não há internet aberta nem Docker no ambiente de teste. Fica como decisão do time (item 3 de `PERGUNTAS_EQUIPE.md`) | — |
| 12 | A OS 14142 "continua em execução" é afirmada **com base no PDF da OS**, que é um retrato de quando foi impresso | Se der, confirmar com a equipe do Help Desk antes do pitch. Se ela foi resolvida, dizer "ficou mais de X meses em execução". | Ajustar a frase do gancho |
