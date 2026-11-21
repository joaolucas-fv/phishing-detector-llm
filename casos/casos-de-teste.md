Casos de Teste — Phishing Detector com LLM

1. Apresentação

Este documento reúne os dez cenários utilizados para avaliar o protótipo Phishing Detector, desenvolvido com o apoio de um Modelo de Linguagem (LLM).

A proposta dos testes foi observar como o modelo identifica possíveis tentativas de phishing, reconhece técnicas de engenharia social e avalia os riscos envolvidos. Também foi analisado se ele consegue distinguir mensagens suspeitas de comunicações que, à primeira vista, parecem legítimas.

Todos os cenários foram elaborados com base na empresa fictícia Meridional. Portanto, nenhuma das mensagens apresentadas corresponde a uma comunicação real de uma empresa ou pessoa.

2. Metodologia de avaliação

Para realizar os testes, foram fornecidas mensagens fictícias ao ChatGPT, seguindo as orientações estabelecidas no prompt principal do projeto.

As respostas foram analisadas a partir dos seguintes critérios:

Identificação dos indicadores de phishing.
Classificação da mensagem.
Atribuição do nível de risco.
Coerência da análise apresentada.
Identificação dos possíveis impactos.
Qualidade das recomendações de segurança.
Reconhecimento das limitações do modelo.

Antes da execução, foram definidas as classificações e os níveis de risco esperados para cada cenário. Depois, esses parâmetros foram comparados com as respostas fornecidas pelo modelo.

A análise foi qualitativa e feita manualmente.

3. Resumo dos resultados

Ao todo, foram realizados dez testes. Os cenários envolveram diferentes formas de phishing, técnicas de engenharia social e também comunicados corporativos que poderiam ser considerados legítimos.

3.1 Resultados com classificação Muito suspeito

Em oito cenários, o LLM classificou as mensagens como muito suspeitas.

1. Teste 01 — Falsa suspensão de conta
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

2. Teste 02 — Falso suporte de TI
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

3. Teste 04 — Anexo com macros
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

4. Teste 05 — Fraude BEC
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

5. Teste 06 — Smishing
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

6. Teste 07 — Quishing
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

7. Teste 08 — Spear Phishing
   Nível de risco: Alto.
   Resultado esperado e observado: Coincidentes.

8. Teste 09 — Falsa redefinição de senha
   Nível de risco: Médio.
   Resultado esperado: Alto.
   Resultado observado: Divergência na classificação do risco.

3.2 Resultados sem indícios claros de phishing

Nos outros dois cenários, o modelo entendeu que não havia indícios claros de phishing.

1. Teste 03 — Comunicação de manutenção programada
   Nível de risco: Baixo.
   Resultado esperado e observado: Coincidentes.

2. Teste 10 — Comunicação corporativa com link informativo
   Nível de risco: Baixo.
   Resultado esperado e observado: Coincidentes.

3.3 Divergências e observações

Ao comparar as respostas com os resultados esperados, foram notadas três imprecisões que merecem destaque:

Teste 02: o modelo descreveu o link como externo, mas ele utilizava o mesmo domínio apresentado no endereço do remetente.
Teste 08: ao analisar CPF, salário e dados bancários, o modelo empregou incorretamente a classificação de dados pessoais sensíveis, considerando a definição da LGPD.
Teste 09: o nível de risco indicado pelo modelo foi Médio, enquanto o resultado esperado era Alto.

Esses pontos também foram levados em conta na avaliação técnica dos resultados.

4. Detalhamento dos testes

Teste 01 — Falsa suspensão de conta

Tipo de ameaça: Phishing por urgência.

Cenário: A mensagem fictícia informa que a conta do destinatário será bloqueada caso os dados não sejam atualizados dentro de 12 horas.

Indicadores esperados:
Ameaça de bloqueio da conta.
Prazo reduzido para realizar uma ação.
Pressão psicológica.
Remetente não verificado.
Presença de link para atualização cadastral.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

Nesse caso, o LLM reconheceu os principais sinais de phishing. A urgência da mensagem e a ameaça de bloqueio da conta foram identificadas corretamente, e a classificação ficou de acordo com as características do cenário.

Teste 02 — Falso suporte de TI

Tipo de ameaça: Phishing para roubo de credenciais.

Cenário: A mensagem, que supostamente foi enviada pelo departamento de Tecnologia, pede que os funcionários informem suas senhas e códigos de autenticação para uma atualização de segurança.

Indicadores esperados:
Solicitação de senha corporativa.
Solicitação de código de autenticação.
Uso de urgência.
Possível personificação do departamento de TI.
Link para validação de conta.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

O LLM reconheceu os principais indicadores da tentativa de phishing e apontou os riscos relacionados ao possível roubo de credenciais.

Apesar disso, houve uma imprecisão na análise do link: o modelo o descreveu como externo, embora utilizasse o mesmo domínio informado no endereço do remetente. Ainda assim, não seria possível confirmar a legitimidade da página apenas com base no texto da mensagem.

Teste 03 — Comunicação de manutenção programada

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Cenário: O comunicado informa aos colaboradores sobre uma manutenção programada nos sistemas internos da Meridional. A mensagem não solicita informações nem exige que o destinatário tome alguma providência.

Indicadores esperados:
Ausência de solicitação de credenciais.
Ausência de pressão psicológica.
Ausência de links ou anexos.
Comunicação informativa.
Remetente ainda não autenticado.

Resultado esperado: Sem indícios claros / Baixo.

Resultado observado: Sem indícios claros / Baixo.

Avaliação técnica:

A mensagem recebeu uma classificação adequada. O LLM também observou que uma apresentação profissional, por si só, não comprova que o remetente seja legítimo. Nesse cenário, evitou classificar como phishing uma comunicação que não apresentava sinais claros da ameaça.

Teste 04 — Anexo com macros

Tipo de ameaça: Phishing com possível distribuição de malware.

Cenário: Uma mensagem falsa, atribuída ao departamento de Recursos Humanos, comunica uma atualização da folha salarial. Para consultar as informações, o funcionário é orientado a abrir um arquivo `.xlsm` e habilitar as macros.

Indicadores esperados:
Anexo com extensão `.xlsm`.
Solicitação para habilitar macros.
Utilização de informações salariais como isca.
Possível personificação do RH.
Remetente não verificado.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

O modelo apontou corretamente os riscos associados ao anexo e à habilitação de macros. Também mencionou a possibilidade de distribuição de malware, mas sem afirmar que o arquivo necessariamente continha código malicioso.

Teste 05 — Business Email Compromise (BEC)

Tipo de ameaça: Fraude por comprometimento ou personificação de e-mail corporativo.

Cenário: Uma mensagem que supostamente foi enviada pela diretoria solicita a alteração dos dados bancários de um fornecedor. Além disso, exige que o pagamento seja feito com urgência e em sigilo.

Indicadores esperados:
Solicitação urgente de pagamento.
Alteração de dados bancários.
Pedido de sigilo.
Possível personificação da diretoria.
Ausência de validação independente.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

A resposta identificou os sinais característicos de BEC e de engenharia social. O LLM também apontou o risco de desvio financeiro e recomendou confirmar a solicitação por outro canal, de forma independente, antes de realizar qualquer pagamento.

Teste 06 — Smishing

Tipo de ameaça: Phishing por SMS.

Cenário: Uma mensagem de texto avisa sobre uma suposta pendência na entrega de uma encomenda. Para evitar que o pacote seja devolvido, o destinatário precisa pagar uma taxa por meio do link informado.

Indicadores esperados:
Remetente não identificado.
Cobrança inesperada.
Urgência para pagamento.
Ameaça de devolução da encomenda.
Link para regularização.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

O LLM reconheceu os principais sinais de smishing. Na análise, destacou como a urgência e a pressão psicológica poderiam levar o destinatário a realizar o pagamento sem verificar se a cobrança era verdadeira.

Teste 07 — Quishing

Tipo de ameaça: Phishing por QR Code.

Cenário: Um comunicado fictício da Meridional informa sobre uma atualização da autenticação corporativa e orienta os funcionários a escanear um QR Code para validar suas contas.

Indicadores esperados:
Falsa atualização de autenticação.
Solicitação de validação de contas.
Prazo limite.
Ameaça de suspensão de acesso.
Utilização de QR Code como mecanismo de direcionamento.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

O modelo identificou corretamente os sinais de Quishing e destacou que QR Codes podem levar o usuário a páginas fraudulentas.

Como nenhum QR Code real foi disponibilizado durante o teste, a análise ficou limitada ao texto do comunicado. Por esse motivo, o modelo não chegou a verificar o endereço para o qual o código direcionaria o usuário.

Teste 08 — Spear Phishing

Tipo de ameaça: Engenharia social e possível phishing direcionado.

Cenário: Uma mensagem que supostamente veio da diretoria solicita uma planilha com nomes, CPFs, cargos, salários e dados bancários dos colaboradores. O remetente também pede que os canais habituais de validação não sejam utilizados.

Indicadores esperados:
Solicitação de dados pessoais e financeiros.
Utilização de urgência.
Pedido de confidencialidade.
Possível personificação da diretoria.
Desvio dos procedimentos internos.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Alto.

Avaliação técnica:

O LLM reconheceu os indícios de engenharia social e de possível Spear Phishing. Também apontou os riscos envolvidos no compartilhamento dessas informações, como exposição de dados pessoais, fraude financeira e roubo de identidade.

Nesse teste, porém, foi identificada uma imprecisão no uso do termo dados pessoais sensíveis. CPF, salário e dados bancários podem ser considerados dados pessoais, mas não fazem parte automaticamente das categorias de dados pessoais sensíveis definidas pela LGPD.

Teste 09 — Falsa redefinição de senha

Tipo de ameaça: Phishing para roubo de credenciais.

Cenário: Uma mensagem supostamente enviada pela equipe de Segurança da Informação informa que a senha corporativa expirará naquele mesmo dia. Para fazer a redefinição, o funcionário é direcionado a um portal por meio de um link.

Indicadores esperados:
Urgência para atualização da senha.
Ameaça de bloqueio de acesso.
Link para redefinição.
Possível personificação da equipe de segurança.
Remetente não verificado.

Resultado esperado: Muito suspeito / Alto.

Resultado observado: Muito suspeito / Médio.

Avaliação técnica:

O LLM identificou os sinais de phishing e os possíveis riscos de roubo de credenciais. No entanto, o nível de risco atribuído não foi o mesmo que havia sido definido como esperado.

A classificação ficou como médio porque o modelo considerou que não havia evidências suficientes para confirmar que o link era malicioso ou que o remetente havia sido falsificado.

A diferença entre os resultados mostra que é importante estabelecer critérios mais objetivos para definir os níveis de risco.

Teste 10 — Comunicação corporativa com link informativo

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Cenário: Uma mensagem do departamento de Recursos Humanos comunica que um calendário de feriados e de funcionamento interno está disponível. Para consultar o documento, apresenta um link direcionado à intranet corporativa.

Indicadores esperados:
Ausência de pressão psicológica.
Ausência de ameaças.
Ausência de solicitação de credenciais.
Conteúdo informativo.
Presença de link sem evidências suficientes de maliciosidade.
Remetente ainda não autenticado.

Resultado esperado: Sem indícios claros / Baixo.

Resultado observado: Sem indícios claros / Baixo.

Avaliação técnica:

O modelo fez a distinção entre a simples presença de um link e a existência de uma ameaça. Também ressaltou que a aparência do endereço não é suficiente para confirmar sua autenticidade e apresentou recomendações adequadas para que ele seja verificado.

5. Principais observações identificadas

Considerando os dez testes, foi possível observar tanto pontos positivos quanto algumas limitações na atuação do LLM.

Comportamentos positivos

Identificação de diferentes modalidades de phishing.
Reconhecimento de técnicas de engenharia social.
Identificação de solicitações indevidas de informações confidenciais.
Diferenciação entre mensagens suspeitas e aparentemente legítimas.
Reconhecimento de limitações na verificação de remetentes e links.
Apresentação de recomendações preventivas.

Limitações identificadas

Imprecisão ao descrever um link como externo quando ele utilizava o mesmo domínio do remetente.
Utilização incorreta da expressão dados pessoais sensíveis em um contexto relacionado à LGPD.
Divergência na atribuição do nível de risco em um dos testes.
Dependência das informações textuais fornecidas pelo usuário.
Impossibilidade de comprovar a autenticidade de remetentes, links, anexos ou QR Codes apenas pelo conteúdo apresentado.

6. Conclusão dos testes

Os testes mostram que um Modelo de Linguagem pode ser útil como apoio na análise inicial de mensagens suspeitas.

Durante a avaliação, o protótipo conseguiu reconhecer diferentes modalidades de phishing, entre elas ataques por e-mail, Smishing, Quishing, possíveis casos de Spear Phishing e fraudes BEC.

Outro ponto observado foi a capacidade de analisar mensagens com aparência de comunicados legítimos sem classificá-las automaticamente como maliciosas.

Mesmo com esses resultados, alguns limites ficaram evidentes, principalmente na interpretação de informações, na definição dos níveis de risco e na precisão de determinados conceitos.

Por isso, os resultados indicam que o LLM deve ser usado como uma ferramenta complementar. Ele não substitui ferramentas especializadas de segurança nem a avaliação humana.

É importante lembrar que os dez cenários são fictícios e fazem parte de uma avaliação exploratória. Os resultados não correspondem a uma taxa estatística de precisão e também não comprovam a capacidade do protótipo de detectar ataques reais.
