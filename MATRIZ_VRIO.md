# Matriz VRIO — Entrega 3 (sábado, 13h20)

**Equipe:** UFPR-SEPT · **Desafio:** IA na Gestão Pública (SIMOT) · **Solução:** Missão SJP
**Link do protótipo:** `claude.ai/artifact/RR94ofArDEcseEjKpv8RdP` (vitrine com vídeo e telas; **liberar o compartilhamento antes de enviar**) · roda com `iniciar.bat` → `http://localhost:3000/demo.html`

> Revisem os blocos 1 e 3 antes de entregar. O canvas pede **só o que roda**, e o que está escrito aqui foi testado de forma automática esta madrugada (27 de 27 verificações). Confirmem no notebook da demo.

---

### 1. O que o protótipo faz hoje (só o que roda)
Fluxo ponta a ponta:
1. Uma OS aberta no **sistema Help Desk antigo (simulado)** chega por **API** à plataforma, com o mesmo número de origem e sem duplicar.
2. A **IA sugere** tipo, prioridade e o que falta perguntar, e sugere o técnico (de preferência quem já está na mesma unidade); o **gestor confere** e atribui (presencial, remoto ou telefone).
3. O **técnico recebe no celular**: aceita, faz check-in no local, marca o checklist, **registra o impedimento em 2 toques**, conclui com foto.
4. O **demandante confirma e avalia**, ou indica pendência e a missão reabre.
5. O status **volta ao sistema antigo**; se ele estiver fora do ar, a atualização fica numa fila e é entregue depois.
6. **Ranking por equipe e individual** atualizado, com regras editáveis e reinício mensal.
7. Qualquer setor novo é **configurado pela tela, sem programar**.

### 2. A feature que testamos (uma só, a da demo de 60 s)
**Impedimento visível na hora, sem punir o técnico.** Em campo, o técnico registra "falta de material" em 2 toques. O gestor vê na hora, numa faixa vermelha, com há quanto tempo está parado e se é **recorrente** ("2º bloqueio por falta de material no mês"). O almoxarifado é avisado. O tempo bloqueado **pausa o relógio** e não tira pontos. Ao resolver, o técnico ganha bônus.

---

### V — Valor
*Que dor essa feature resolve, e como sabemos (evidência, não intenção)?*
- Na base real de chamados de 2026 (`chamados20261005.txt`, 9.969 chamados de 05/01 a 05/10), **151 chamados estão parados em Aquisições/Estoque**, todos como "ENCAMINHAR", com **idade mediana de 153 dias** (máximo de cerca de 270).
- A **OS 14142** pede um cabo HDMI de 15 m para uma UBS desde 20/10/2025. Os andamentos dizem "N/D" e ela segue "em execução".
- Cerca de **3 em cada 4 chamados do Help Desk** (73–78%, conforme o critério) são fechados **em lote**: 5 ou mais do mesmo técnico nos mesmos 5 minutos. O registro é feito depois, não durante o atendimento, e por isso o impedimento nunca aparece na hora.
- O sistema atual **tem uma tabela de "Pendências" que nunca é usada** (Total 0 nas 4 OS analisadas).

### R — Raridade
*A Prefeitura já tem algo assim? Existe pronto no mercado? O que a nossa faz diferente?*
- O sistema atual registra a OS, mas **não tem visão de campo**: sem estado de bloqueio com motivo, sem aviso ao gestor, sem confirmação do demandante.
- Ferramentas de mercado de gestão de equipes em campo fazem OS no celular, mas são **em nuvem e com licença**. A **Lei Municipal 4.715/2025 (art. 53)** veda nuvem e datacenter terceirizado.
- **O diferencial:**
  - Roda 100% no datacenter da SIMOT.
  - Integra com o sistema existente em vez de substituí-lo.
  - Trata o **impedimento como dado de gestão**: tempo parado, motivo e recorrência.
  - Tem uma **gamificação que não pune** o técnico por fator externo.

### I — Imitabilidade
*O que é difícil de copiar: o dado, o processo ou o modelo?*
- **Honestamente:** o código é simples e aberto. Uma equipe técnica copiaria as telas em semanas, e isso é **de propósito**, para a Prefeitura conseguir manter.
- **O que é difícil de copiar:**
  - **O processo calibrado com a realidade da SIMOT:** motivos de bloqueio, regras de pontos justas e a fila de integração com o sistema antigo.
  - **O histórico que se acumula:** impedimentos por material, unidade e equipe. Esse histórico vira base para compras e priorização.
  - **A adesão dos servidores:** quem já usa e confia no ranking não troca de ferramenta.
  - **O que os próprios técnicos já criaram:** o setor de Telecom montou por conta própria um mapa em BI das unidades atendidas. A plataforma institucionaliza esse tipo de solução informal em vez de competir com ela.

### O — Organização
*Quem, dentro da Prefeitura, opera isso na segunda-feira? De onde sai o orçamento de manutenção?*
- **Operação técnica:** **SIMOT**, que hospeda no datacenter municipal, administra e cadastra novos setores.
- **Operação do dia a dia:** **Gestor do Help Desk / Divisão de TI**, que distribui as missões, age nos bloqueios e confere as sugestões da IA.
- **Piloto:** 1 equipe de campo do Help Desk (sugestão do mentor de negócio: a própria Secretaria de Inovação). Depois, Manutenção Predial.
- **Orçamento:** rubrica de TI/modernização da SIMOT. **Não há licença nem API paga**; o custo é a sustentação pela equipe interna e um servidor no datacenter próprio. Para contratar a evolução: CPSI (Marco Legal das Startups, LC 182/2021) ou desenvolvimento interno com o código cedido.

---

### 3. Evidência do teste
*O que fizemos para testar e o que aconteceu. Com quem, quantas vezes, o que quebrou.*
- **Teste automatizado num navegador real** (madrugada de 10/10): o fluxo completo nos 4 papéis + sistema antigo, **27 verificações, 27 aprovadas**:
  - entrada sem duplicar;
  - "a caminho" e check-in, com aviso ao demandante;
  - impedimento com aviso ao almoxarifado;
  - pontos parciais sem duplicar;
  - confirmação pelo demandante;
  - status FINALIZADO no sistema antigo;
  - fila guardando a atualização com o sistema antigo fora do ar e entregando ao religar;
  - setor novo criado pela tela e reconhecido pela IA;
  - técnico bloqueado de atribuir e de ver missões alheias;
  - mapa do técnico (unidades, caminho com km e minutos) e mapa da operação no gestor;
  - nenhum erro nas telas.
- **O que quebrou e foi corrigido:**
  - Um técnico via missões de colegas com número parecido (corrigido).
  - Risco de o OneDrive travar o banco (dados movidos para fora do OneDrive).
- **[Preencher no sábado]:** ensaio em [N] rodadas; tempo da demo: [__] s; frase de um mentor: "[frase]".
- **Limitações declaradas:**
  - O push do sistema no celular exige HTTPS (em produção, o datacenter fornece).
  - A IA roda em modo reserva quando o modelo local não está instalado (marcado como SIMULADO na tela).
  - O login é simplificado.

---

> **Se o time preferir que a feature testada seja "configurar um setor novo sem programar":** troquem o bloco 2 por *"Em 1 minuto o gestor cria o setor Jardinagem, com tipo de tarefa, checklist e regra de pontos, e a primeira missão desse setor já roda no mesmo fluxo, com a IA reconhecendo o tipo novo"*. Em **Valor**, usem o argumento de que o Manual exige solução genérica para manutenção, vistoria e serviços urbanos, e que hoje cada setor dependeria de um sistema próprio.
