# Revisão crítica do protótipo — Missão SJP

*Feita na madrugada de 10/10/2026, contra os 7 requisitos não negociáveis do Manual e os critérios da banca (OnePage). Versão revisada: **0.2.0**. Backup da versão anterior: `prototipo_backup_0422`.*

## 1. Resultado em uma frase
O fluxo ponta a ponta exigido pelo Manual funciona e foi testado de forma automática num navegador real. A versão 0.2.0 passou em **27 de 27 verificações**: entrada por API sem duplicar, impedimento, conclusão, confirmação, volta ao sistema antigo, fila com o sistema fora do ar, configuração de setor novo, permissões por papel, mapa do técnico e do gestor e nenhum erro de JavaScript.

## 2. O que foi corrigido ou acrescentado esta noite

| # | Mudança | Por quê |
|---|---|---|
| 1 | **Modo apresentação** (`demo.html`): celular do técnico/demandante + gestor/sistema antigo numa tela só | Na demo de 60 s, trocar abas e logins é onde mais se erra. Agora tudo fica visível ao mesmo tempo para a banca. |
| 2 | **Estado "A caminho" + check-in com foto inicial** | Está no fluxo do time (Lucidchart: "Aceita e inicia deslocamento", "Check-in. Foto inicial") e responde à primeira pergunta do Manual: "o técnico chegou ao local?". |
| 3 | **Modalidade de atendimento** (presencial / remoto / telefone) | Está no fluxo do time e no documento "Problema" (50–60% dos casos se resolvem por telefone). Remoto e telefone pulam o deslocamento. |
| 4 | **Sugestão de técnico** (menos missões ativas + experiência no tipo), sempre conferida pelo gestor | Está no fluxo do time ("Sugestão de Técnico"). Reforça o uso de IA e dados, com conferência humana, como o Manual exige. |
| 5 | **Alerta de impedimento recorrente** ("2º bloqueio por falta de material em 30 dias") + aviso ao almoxarifado/compras | O Manual cita "identificação de impedimentos recorrentes"; o fluxo do time tem "Notifica IA / compras". Ataca o caso real dos 151 chamados parados no estoque. |
| 6 | **Avanço parcial validado → pontos proporcionais**, sem duplicar no final | É exatamente o que a síntese da SIMOT de 03/10 pede ("parciais validadas geram pontos proporcionais, sem duplicação"). |
| 7 | **A prioridade ordena a lista do técnico** (alta primeiro; bloqueadas por último) | Também está na síntese da SIMOT ("prioridade orienta a ordem"). |
| 8 | **Bug corrigido:** o técnico de id 1 via missões de colaboradores com id 10, 11… (busca por texto) | Trocado por consulta JSON exata. |
| 9 | **`iniciar.bat` robusto:** checa a versão do Node, abre o modo apresentação e guarda os dados **fora do OneDrive** (`%LOCALAPPDATA%\MissaoSJP`) | A sincronização do OneDrive pode travar ou corromper o banco SQLite no meio da demo. |
| 10 | **`resetar.bat`** e endpoint **`/api/saude`** | Voltar ao estado inicial antes de cada ensaio, e um teste rápido de que o servidor está no ar. |
| 11 | **Migração automática do banco** | Quem já rodou a versão 0.1 não perde nada (a pasta `prototipo\dados` existente continua funcionando). |
| 12 | README reescrito; 19 capturas novas em `prototipo/docs/telas` (as antigas foram para `_versao_anterior`) | Documentação exigida pelo requisito 7 e imagens para os slides. |
| 13 | **Acompanhamento em tempo real para o demandante**: rastreio "Recebido → Encaminhado → A caminho → Em atendimento → Concluído" + avisos "seu chamado foi encaminhado", "técnico a caminho", "chegou", "aguardando material" | Pedido ouvido na mentoria: o usuário fica no **"apagão operacional"** e liga para o Help Desk perguntando se alguém vem. Depois, o Help Desk ainda liga para confirmar a conclusão. Agora isso é um toque no celular. |
| 14 | **Sugestão de técnico prioriza quem já está na mesma unidade** ("já está agora na UBS Jardim Exemplo") | Também ouvido na mentoria: as equipes se organizam por região e o ideal é "você está no lugar X, abriu uma ordem no mesmo lugar, já faz". O setor de Telecom chegou a criar um mapa em BI por conta própria. |
| 15 | **Indicador "deslocamento médio"**, separado do tempo de execução | Ouvido na mentoria: há unidades a 20–35 km, e viagem não pode ser confundida com serviço. |
| 16 | **Mapa das missões para o técnico** (aba 🗺️ Mapa no celular) e **"Mapa da operação" no painel do gestor**: unidades com missões coloridas pelo estado mais urgente, "Você" na unidade em atendimento, aviso de missão na mesma unidade, lista "Mais perto de você" e, ao escolher uma missão, o caminho com km e minutos | Ouvido na mentoria: as equipes se organizam por região e querem aproveitar a viagem. O mapa é desenhado pelo próprio sistema, sem serviço de mapa externo (soberania); as coordenadas são fictícias e, em produção, viriam do cadastro das unidades. |

## 3. Aderência aos 7 requisitos não negociáveis

| # | Requisito | Situação | Evidência no protótipo | Risco na arguição |
|---|---|---|---|---|
| 1 | Genérico + cadastro autorizado | ✅ | Tela Configuração cria setor, equipe, tipo, checklist, motivo, pessoa e regras sem código. A IA reconhece na hora o tipo novo. Só atendente ou gestor abrem tarefas. | "E um fluxo com etapas diferentes por setor?" Hoje o fluxo de estados é o mesmo para todos (de propósito: simples de manter); o que muda por setor é o checklist. |
| 2 | Integração bidirecional | ✅ | Entrada idempotente (chave única `origem + cod_origem`); saída por **outbox** na mesma transação; reenvio a cada 3 s; destino deduplica por `X-Id-Mensagem`. Botões "Simular queda" e "Reenviar" provam isso ao vivo. | "Como liga no sistema real?" É um conector pequeno que lê as OS novas do banco atual e chama a nossa API. Pedir ao mentor da Prefeitura que tecnologia o Help Desk usa. |
| 3 | Web + mobile com push | ✅ / ⚠️ | PWA + Web Push VAPID próprio + tempo real (SSE). | **O push do sistema operacional exige HTTPS** fora do localhost. Na demo: modo apresentação no notebook (o aviso aparece no app) ou a flag do Chrome Android (ver Checklist). |
| 4 | Rastreabilidade, validação, acesso | ✅ | A linha do tempo registra quem, quando, o quê e foto em cada etapa (deslocamento, check-in, impedimento, conclusão, confirmação). Concluído ≠ resolvido. A pendência reabre. Papéis checados em todas as rotas. | O login é simulado (header com o id do usuário). Dizer: "em produção, login da Prefeitura (AD/LDAP)". |
| 5 | Gamificação configurável | ✅ | Regras editáveis, ranking por equipe e individual, reinício mensal com histórico, bloqueio externo não pune, avaliação do demandante dá bônus, colaboração pontua, avanço parcial. | "Como evitar que o técnico force a nota do demandante?" A nota baixa não tira pontos, só deixa de dar o bônus; o ranking da equipe vem em destaque. |
| 6 | IA demonstrável com conferência humana | ✅ / ⚠️ | Triagem (tipo, prioridade, informação faltante), sugestão de técnico, alerta de recorrência. Tudo é aceito ou corrigido por uma pessoa. | **Sem Ollama instalado, a triagem roda no modo reserva por palavras-chave**, marcado como SIMULADO na tela. Se der tempo, instalar o Ollama + `qwen2.5:3b` no notebook (cerca de 2 GB) para demonstrar o LLM local de verdade. |
| 7 | Hospedagem municipal + código | ✅ | `docker compose up`; zero dependências npm; zero nuvem; README com licenças, o que é simulado e próximos passos. | O Docker não foi testado nesta máquina (não há Docker no ambiente de teste). Se alguém do time tiver Docker, rodar uma vez. |

## 4. Pontos fracos que ainda existem (priorizados)

**Alta: resolver ou ter resposta pronta antes da banca**
1. **Push no celular de verdade.** Testar no Android com a flag `unsafely-treat-insecure-origin-as-secure` (Checklist, seção C). Se não der, a demo usa o modo apresentação: o aviso aparece no "celular" da tela, em tempo real.
2. **IA em modo reserva.** Decidir até as 10h se vale instalar o Ollama no notebook da demo. Se não, a frase é: "a IA roda num modelo aberto dentro do datacenter; aqui ela está no modo reserva, identificado como simulado".
3. **Ensaiar a demo com `resetar.bat` antes de cada ensaio.** Os dados de exemplo usam horários relativos ("há 16 dias"); resetar deixa tudo coerente.

**Média: melhorias que valem se sobrar tempo (não mexer depois das 10h)**
4. Editar e excluir itens na Configuração (hoje só cria).
5. Login com senha (as telas estáticas da outra versão já têm o visual; dá para ligar depois).
6. ~~Mapa com a localização das missões~~ **feito** (item 16 da seção 2).
7. Check-in por QR Code na etiqueta de patrimônio (a etiqueta já existe nas OS reais: 07516, 04615…).

**Baixa: próximos passos, não para hoje**
8. Fluxos de estados diferentes por setor.
9. Trocar SQLite por PostgreSQL (o modelo de dados já é compatível).
10. Fotos guardadas como arquivo (hoje vão comprimidas dentro do banco).

## 5. Autoavaliação pelos critérios da banca (para saber onde reforçar a fala)

| Critério | Peso | Nossa força | O que falar ou mostrar |
|---|---|---|---|
| Impacto na vida do servidor | 25% | Alta | Técnico sem papel e sem voltar à base; impedimento não pune; demandante sabe o status. Gancho com a OS 14142. |
| Dados e IA | 20% | Média-alta | Números reais da base 2026 (lote, estoque) + IA de triagem/sugestão/recorrência com conferência humana. **Ponto a reforçar: IA rodando de verdade (Ollama).** |
| Viabilidade de implantação | 20% | Alta | Zero licença, zero dependência, um comando para subir, datacenter da SIMOT, integração por fila. |
| Inovação e diferencial | 15% | Média-alta | Impedimento como protagonista, concluído ≠ resolvido, gamificação que não pune, configurável por qualquer setor. |
| Usabilidade | 10% | Alta | Botões grandes, no máximo 2 toques, estado com ícone + texto, modo apresentação. |
| Pitch | 10% | — | Ensaiar com cronômetro: a demo não pode passar de 60 s. |
