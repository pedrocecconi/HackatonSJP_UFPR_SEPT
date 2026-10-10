# Mapa do Pitch — Entrega 4 (slides até 15h15 · banca 15h40)

**3 minutos de apresentação + 3 de arguição.** Quem estoura o tempo perde a demo. Ensaiem com cronômetro.
**Números usados (só 2):** "3 em cada 4" e "151 chamados / 153 dias". Ambos foram calculados da base `chamados20261005.txt`, com o método descrito no fim deste documento.

---

## 1. O gancho (0:00–0:20)
> "Em 20 de outubro do ano passado, uma Unidade de Saúde pediu **um cabo HDMI**. Um cabo. Hoje, quase um ano depois, a ordem de serviço **14142** continua 'em execução'. Os andamentos dizem só 'N/D'. Ninguém sabe onde ela parou."

*(Slide 1: só a frase e o número da OS, grande.)*

## 2. O problema (0:20–0:50)
> "Isso não é descuido de ninguém. É um **ponto cego**: a OS é impressa, o técnico sai com o papel, e daí até ele voltar a gestão não sabe se ele chegou, se faltou material ou se resolveu. Os técnicos chamam isso de **apagão operacional**: o usuário fica ligando para o Help Desk sem saber se alguém vem.
> Na base de 2026, **3 em cada 4 chamados do Help Desk são fechados em lote**, depois do serviço. E **151 chamados estão parados no estoque, há 153 dias em média**, sem ninguém ser avisado."

## 3. A solução (0:50–1:20)
> "A **Missão SJP** transforma cada chamado numa missão que vai **para o celular de quem executa**. O técnico registra que saiu, que chegou, o que faltou e o que entregou, em poucos toques. O gestor vê os impedimentos **na hora**. E **quem pediu acompanha e confirma** se resolveu.
> Ela **não substitui** o sistema da Prefeitura: conversa com ele. E é **genérica**: TI, manutenção, vistoria ou jardinagem se configuram pela tela, sem programar."

## 4. A demo (1:20–2:20) — os cliques
*(Roteiro completo, com falas, em `ROTEIRO_DEMO.md`.)*
1. Sistema antigo → **Gravar OS**.
2. Gestor → abrir → **Aceitar sugestão** (IA) → **Atribuir e notificar**.
3. Celular do técnico → **Aceitar e ir ao local** → **Check-in**. O demandante vê "a caminho".
4. **Tenho um impedimento → Falta de material**. O gestor vê em vermelho, com o alerta de recorrência → **Impedimento resolvido**.
5. Técnico → **Concluir** com foto.
6. Demandante → **Sim, está resolvido** ★★★★★.
7. Sistema antigo mostra **FINALIZADO** → Ranking.

## 5. Por que se sustenta (2:20–2:40)
> "Ela roda **inteira no datacenter da SIMOT**, como manda a Lei 4.715: **sem nuvem, sem licença e sem nenhuma dependência externa**. É um comando para instalar, e o código é da Prefeitura. Quem opera é a SIMOT, com o gestor do Help Desk no dia a dia. A gamificação é **justa**: os pontos só somam, bloqueio por falta de material não pune e o reconhecimento é da equipe."

## 6. Impacto na cidade
*(Falar junto com o bloco 5, uma frase.)*
> "Cada chamado parado é uma UBS ou uma escola trabalhando pela metade. **Saúde e Educação são quase 6 em cada 10 chamados.**"

## 7. Próximos 90 dias (2:40–3:00)
> "Em 90 dias:
> - **conector com o Help Desk real**;
> - **piloto com uma equipe de campo**;
> - um segundo setor, a Manutenção Predial.
>
> Nossa meta é sair de 1 em cada 4 para **mais de 80% dos chamados com andamento registrado durante o atendimento**, e **nenhum chamado parado sem motivo e sem responsável visível**."

---

## 18 perguntas prováveis da banca (respostas de até 20 s)

1. **"Como isso conversa com o sistema que a Prefeitura já usa?"**
   Por API, nos dois sentidos. O chamado entra com o mesmo número da OS, e cada atualização volta para o sistema antigo. Na demo, o sistema antigo é simulado com os mesmos campos e estados das OS reais. Para o real, falta só um conector que leia as OS novas.

2. **"E se a conexão cair ou o sistema antigo estiver fora do ar?"**
   Nada se perde. Cada atualização é gravada numa fila, na mesma operação que muda o estado, e é reenviada até o sistema antigo confirmar. Podemos mostrar agora: desligo o sistema antigo, atualizo, religo e ele recebe tudo.

3. **"Como evitam registros duplicados?"**
   O número de origem é chave única no banco. Se o mesmo chamado chegar duas vezes, a plataforma responde "já existe" e não cria outro. No retorno, cada mensagem tem um identificador que o destino usa para ignorar repetições.

4. **"Onde está a IA? É de verdade?"**
   A IA faz a triagem (sugere tipo e prioridade e avisa o que falta perguntar), sugere o técnico e alerta impedimentos recorrentes. Ela roda num modelo aberto **local** (Ollama), sem nuvem. Na demo, se o modelo não estiver instalado, entra o modo reserva, marcado como simulado na tela. Sempre uma pessoa confere.

5. **"A IA pode errar a prioridade?"**
   Pode, e por isso ela só **sugere**. Quem decide é o gestor ou o atendente, e o sistema registra se a sugestão foi aceita ou corrigida. Isso também mede a qualidade da IA ao longo do tempo.

6. **"Isso respeita a lei de soberania digital?"**
   Sim. Sistema e banco rodam no datacenter municipal, com zero serviços em nuvem e zero bibliotecas externas. O push do celular vai **vazio** pelo serviço do navegador e o conteúdo é buscado na própria plataforma, então nenhum dado sai.

7. **"Quanto custa manter?"**
   Não há licença nem API paga. O custo é um servidor no datacenter e a sustentação pela equipe da SIMOT. O código é simples de propósito: HTML e JavaScript sem framework, que qualquer desenvolvedor mantém.

8. **"E se o técnico não quiser usar?"**
   Por isso ele ganha primeiro: sem papel, sem voltar à base, e o trabalho dele aparece. A gamificação **não pune**: bloqueio externo pausa o relógio e nota baixa não tira pontos. O reconhecimento é da equipe, para não virar competição tóxica.

9. **"Como a gamificação trata tarefa bloqueada por falta de material?"**
   O tempo bloqueado não conta contra o técnico, e quem supera um impedimento ganha bônus. O gestor vê o bloqueio na hora, com o motivo e se ele é recorrente.

10. **"E se o demandante nunca confirmar?"**
    Depois de 2 dias (configurável), a missão vai para revisão do gestor, que valida pela evidência (foto e descrição). O técnico recebe os pontos da missão, só sem o bônus da avaliação.

11. **"Por que o técnico não fecha o chamado sozinho, como hoje?"**
    Porque "concluído" não é "resolvido". A OS 9188 foi marcada como concluída e o usuário disse que nada tinha sido feito. Aqui o técnico conclui e quem pediu confirma; se houver pendência, a missão volta para ele.

12. **"Serve para outros setores além da TI?"**
    Sim. Na tela de configuração, o gestor cria setor, equipe, tipo de tarefa, checklist e regras de pontos sem programar. Posso criar "Jardinagem" agora, e a IA já passa a reconhecer.

13. **"E quando não tem internet no local?"**
    No protótipo, o técnico precisa de sinal para registrar. O próximo passo é guardar no celular e sincronizar depois, usando a mesma lógica de fila que já usamos com o sistema antigo.

14. **"Quem opera isso na segunda-feira?"**
    A SIMOT hospeda e administra. O gestor do Help Desk distribui as missões e age nos bloqueios. O piloto seria com uma equipe de campo da TI e, depois, a Manutenção Predial.

15. **"Como vocês sabem que funcionou?"**
    Pelo percentual de chamados com andamento registrado **durante** o atendimento: hoje cerca de 25%, meta acima de 80% em 90 dias. Também pelo tempo médio que os chamados ficam parados no estoque, que hoje é de 153 dias.

16. **"Isso não vai dar mais trabalho para o técnico?"** *(alerta ouvido na mentoria)*
    Dá menos. Hoje ele recebe papel, volta à base e digita tudo no fim do dia: 3 em cada 4 chamados são fechados em lote. No app, cada passo leva 1 ou 2 toques. E o registro vira **prova do trabalho dele**: hoje, 35% dos registros nem têm o nome do técnico.

17. **"Por que uma ligação não resolve?"** *(pergunta da mentoria SEBRAE)*
    Hoje já é por ligação, e é isso que gera o apagão: a ligação não deixa registro, não avisa o gestor do impedimento, não mede tempo e depende de alguém atender. Na plataforma, cada passo vira dado e o gestor age antes da reclamação.

18. **"Como o técnico sabe para onde ir? Usa Google Maps?"**
    O app tem um mapa das missões: mostra onde ele está, o que está mais perto e quanto tempo leva, e a IA sugere quem já está na mesma unidade, para aproveitar a viagem. O mapa é desenhado pelo próprio sistema, **sem Google Maps nem serviço externo**: nada sai do datacenter. No protótipo as posições são fictícias; em produção vêm do cadastro das unidades.

---

### Como os números foram calculados (para responder se perguntarem)
- **Fonte:** `chamados20261005.txt`, 9.969 chamados únicos de 05/01 a 05/10/2026.
- **"3 em cada 4 em lote":** chamados do Help Desk concluídos em que o mesmo técnico fechou 5 ou mais nos mesmos 5 minutos. Dá entre 73% e 78%, conforme a janela.
- **"151 parados no estoque":** status ENCAMINHAR em Aquisições/Estoque; idade mediana de 153 dias em 05/10.
- **"Saúde e Educação ≈ 58%":** pelo código da unidade solicitante.
- **"35% dos registros sem nome do técnico":** linhas da base com o campo do técnico vazio.
- **OS 14142, 9188 e 3368:** PDFs das OS na pasta "dados help desk".
