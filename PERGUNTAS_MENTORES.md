# Perguntas para os mentores — sábado de manhã e pré-pitch (13h20)

*Perguntas curtas, para ter resposta em 5 minutos. **Anotem a resposta** e, se for útil, peçam uma frase que possa ir para a VRIO ou para o pitch. Vários mentores também são banca: a conversa é uma prévia da avaliação.*

---

## O que já ouvimos nas mentorias de ontem

| Tema | O que foi dito (resumo) | O que mudamos |
|---|---|---|
| **Campo** | O maior problema é o **"timing"**: o usuário não sabe se a equipe está indo e fica ligando para o Help Desk ("**apagão operacional**"). Depois que a OS é fechada, **o Help Desk liga para confirmar**, e muitas vezes o usuário não está. As equipes se organizam **por região**. O ideal: "você está no lugar X, abriu uma ordem ali, já faz". | Estado **"a caminho"** + **rastreio para o demandante** + avisos + confirmação com um toque + motivo "local fechado/usuário ausente" + **sugestão de técnico que já está na mesma unidade** + **mapa das missões** para o técnico. |
| **Processo do Help Desk** | O atendimento por **telefone continua**; o usuário **não abre chamado sozinho**. **"O real problema está depois que sai do Help Desk, na parte presencial."** O técnico é **setorizado** (escolas, saúde). É preciso **medir o deslocamento** à parte (unidades a 20–35 km). | Abertura só pelo atendente. Indicador **"deslocamento médio"** separado da execução. Destaque na **parte de campo**; a IA de triagem é apoio. |
| **Prefeitura / dados e IA** | **"A barreira vai ser o servidor":** a ferramenta **não pode dar mais trabalho**. Uma solução que **não se integra ao legado** não faz sentido: descubram **o nome do sistema do Help Desk**. **Comecem pequeno.** Dados sem nuvem. | Pitch reforça "**menos trabalho**: sem papel, 2 toques" e "o registro vira **prova do trabalho do técnico**". Pergunta 1 abaixo. |
| **Negócio e método** | **Escolham uma fatia** do problema. Ouçam **histórias reais**. **Benchmark:** operadoras avisam quem vai atender e **mostram o técnico a caminho**. Pergunta-chave: "**por que uma ligação não resolve?**" Piloto na **própria Secretaria**; narrativa de **economia**. | Fatia = **depois que a OS sai do Help Desk**. Rastreio "a caminho". Piloto na SIMOT/Help Desk. CPSI (LC 182/2021) na VRIO. |

**Resposta pronta para "por que uma ligação não resolve?":** "Hoje já é por ligação, e é exatamente isso que gera o apagão: a ligação não deixa registro, não avisa o gestor do impedimento, não mede tempo e depende de alguém atender. Na plataforma, cada passo vira dado, e o gestor age antes de o usuário reclamar."

---

## 1. Integração e Help Desk — podem mudar a apresentação (fazer às 9h–10h)
1. **Qual é o nome do sistema do Help Desk hoje, e quem fornece?** Ele tem banco de dados acessível, ou alguma API? *(A integração da demo é simulada; com o nome, a fala fica concreta.)*
2. "Nossa integração lê as OS novas e devolve os andamentos por uma fila que reenvia se o sistema cair. **Isso é viável no ambiente de vocês, ou o mais realista seria ler e gravar direto no banco?**"
3. "**A OS 14142 (cabo HDMI da UBS) ainda está aberta hoje?**" *(Para não errar o gancho do pitch.)*
4. "Se o técnico registrar 'usuário ausente' no local, **a coordenação quer receber na hora para remanejar?**" *(Mostrar a faixa vermelha do painel.)*
5. "A divisão por setor (um técnico para escolas, outro para saúde): **cadastramos como equipe por secretaria?**"
6. "O **mapa das missões** no celular do técnico (o que está mais perto, quanto tempo leva) **ajuda a montar a rota do dia?**"

## 2. Dados e IA
7. "Para a IA local, um servidor com um modelo pequeno (3 a 8 bilhões de parâmetros) no datacenter é realista? **Que máquina estaria disponível?**"
8. "**Qual destas IAs usariam primeiro:** sugerir técnico pela unidade e pela carga, alertar impedimento recorrente (falta de material), ou triagem no cadastro?"
9. "Mostramos a IA rodando **local**, com o modo reserva marcado como simulado. **Isso convence a banca, ou é obrigatório mostrar o LLM rodando ao vivo?**"
10. "Fila outbox + chave única de origem: **está bem explicado como evitamos duplicado e perda?** O que um avaliador técnico perguntaria?"
11. "O push no celular exige HTTPS. **Na demo, mostrar no modo apresentação (notebook) é suficiente?**"

## 3. Gestão pública e adoção
12. "Na gestão de resíduos e serviços urbanos, **o mesmo fluxo** (missão → impedimento → confirmação) serviria? O que faltaria?" *(Prova do "genérico".)*
13. "Qual indicador **o secretário** olharia primeiro neste painel?"
14. "O que faz um técnico **adotar** um app no primeiro dia sem resistência? Nossa aposta: menos trabalho e gamificação que **nunca tira pontos**."
15. "Validação pelo demandante em um toque, e se ele não responder em 2 dias o gestor valida: **isso é aceitável na prefeitura?**"
16. "O histórico de missões e avaliações **poderia ser usado como reconhecimento formal** (elogio, certificado), sem benefício financeiro? Há risco jurídico ou sindical?"
17. "Para contratar a evolução: **CPSI (Marco Legal das Startups) ou desenvolvimento interno com o código cedido** — o que é mais realista em SJP?"

## 4. Pitch e negócio (pré-pitch das 13h20)
18. "**Assista aos nossos 3 minutos:** onde você se perdeu? O gancho (OS 14142) prende?"
19. "O slide 'configura qualquer setor pela tela' mostra bem a **flexibilidade** da solução?"
20. "Em uma frase, **qual é a nossa proposta de valor**?" *(Testar se repetem o que queremos.)*
21. "**Qual é o ponto mais fraco** do nosso modelo para a banca?"
22. "O argumento de custo ('zero licença, zero nuvem, um servidor no datacenter') é **suficiente**, ou a banca quer um número em reais?"
23. "A demo com todos os papéis numa tela (modo apresentação) **fica clara para quem nunca viu**, ou confunde?"
24. "A gamificação (níveis, medalhas, meta da equipe) parece **infantil** para servidor público? O que mudaria?"

---

### Como usar
- **Dividam por tema:** cada integrante fica com um dos 4 blocos e procura os mentores daquela área.
- **Anotem** as respostas nesta folha e tragam até as **10h**. O que mudar no pitch entra até as 14h20 (ajuste final).
- **Não peçam opinião sobre tudo:** levem a pergunta, mostrem 1 tela, ouçam, agradeçam.
