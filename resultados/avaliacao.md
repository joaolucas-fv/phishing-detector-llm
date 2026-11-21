Avaliação dos Resultados — Phishing Detector com LLM

1. Objetivo da avaliação

Nesta etapa, o objetivo é analisar o desempenho do Modelo de Linguagem utilizado no protótipo Phishing Detector, levando em consideração os resultados dos dez testes realizados.

A avaliação procura observar os pontos positivos, identificar possíveis inconsistências nas respostas e compreender quais são as limitações do modelo ao analisar ameaças relacionadas a phishing e engenharia social.

2. Análise geral do desempenho

Ao longo dos experimentos, o LLM demonstrou capacidade de reconhecer diferentes características comuns em tentativas de phishing, como:

Uso de urgência e pressão psicológica.
Solicitação indevida de credenciais.
Tentativas de obter dados pessoais e financeiros.
Personificação de departamentos e figuras de autoridade.
Direcionamento para links potencialmente suspeitos.
Utilização de anexos que podem conter macros maliciosas.
Uso de SMS e QR Codes como meios para aplicar fraudes.

O modelo também conseguiu reconhecer mensagens aparentemente legítimas. Isso ficou evidente quando não classificou automaticamente uma comunicação como phishing apenas por ela apresentar determinados elementos, como um link.

3. Pontos positivos identificados

3.1 Identificação de diferentes modalidades de phishing

O LLM conseguiu analisar situações envolvendo phishing tradicional, Smishing, Quishing, Spear Phishing e Business Email Compromise (BEC).

Esse resultado mostra que o modelo pode servir como apoio na identificação inicial de diferentes técnicas de engenharia social.

3.2 Reconhecimento de engenharia social

O modelo identificou situações em que eram utilizadas autoridade, urgência, medo e confidencialidade para influenciar o comportamento dos funcionários.

Essas características apareceram principalmente nos testes relacionados ao falso suporte de TI, à alteração de dados bancários e à solicitação de informações dos colaboradores.

3.3 Diferenciação entre mensagens suspeitas e aparentemente legítimas

Nos testes 03 e 10, o modelo classificou as mensagens como sem indícios claros de phishing.

Esse comportamento indica que a ferramenta não considera apenas a presença de links ou o uso de uma comunicação institucional para decidir se uma mensagem representa uma ameaça.

3.4 Recomendações de segurança

As respostas também trouxeram orientações preventivas importantes, entre elas:

Conferir a autenticidade do remetente.
Utilizar canais oficiais de comunicação.
Não compartilhar senhas ou códigos de autenticação.
Comunicar possíveis incidentes à equipe de Segurança da Informação.
Confirmar solicitações financeiras antes de realizar pagamentos.

4. Limitações e inconsistências identificadas

Mesmo com os resultados positivos, os experimentos também permitiram observar algumas limitações do modelo.

4.1 Interpretação incorreta de informações

No teste 02, o modelo descreveu o link como externo, apesar de ele utilizar o mesmo domínio apresentado no endereço do remetente.

Esse caso mostra que o LLM pode interpretar alguns elementos técnicos de maneira incorreta. Por isso, as informações apresentadas na análise precisam ser conferidas.

4.2 Imprecisão conceitual sobre a LGPD

No teste 08, o modelo classificou CPF, salário e dados bancários como dados pessoais sensíveis.

No entanto, essas informações não fazem parte automaticamente das categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

O resultado mostra que modelos de linguagem podem apresentar imprecisões conceituais e jurídicas, mesmo quando suas respostas parecem bem estruturadas.

4.3 Divergência na classificação de risco

No teste 09, o modelo classificou a mensagem como muito suspeita, mas atribuiu a ela um nível de risco médio. O resultado esperado para esse cenário era alto.

Essa diferença mostra que a classificação do risco pode variar conforme a interpretação do modelo e as informações disponíveis durante a análise.

Por esse motivo, é importante estabelecer critérios mais objetivos para orientar a atribuição dos níveis de risco.

4.4 Dependência das informações fornecidas

As análises foram feitas com base no conteúdo textual apresentado pelo usuário. Durante os testes, não foram realizadas verificações técnicas reais de:

Autenticidade dos remetentes.
Reputação dos domínios.
Destino dos links.
Conteúdo dos anexos.
Destino dos QR Codes.

Assim, as classificações devem ser entendidas como análises preliminares. Elas não comprovam, por si só, que existe ou não uma ameaça.

5. Oportunidades de melhoria

A partir dos resultados, foi possível identificar algumas melhorias que podem ser consideradas em uma versão futura do projeto.

5.1 Aprimoramento dos critérios de classificação

Definir orientações mais claras para diferenciar os níveis de risco baixo, médio e alto.

5.2 Melhoria da precisão técnica

Incluir instruções para que o modelo diferencie informações confirmadas, suspeitas e não verificadas. Dessa forma, será possível evitar conclusões que não tenham apoio no conteúdo analisado.

5.3 Ampliação dos cenários de teste

Criar novos exemplos que envolvam outras técnicas de phishing, diferentes canais de comunicação e situações do ambiente corporativo.

5.4 Validação das respostas

Comparar as respostas do LLM com referências confiáveis de Segurança da Informação, em vez de aceitar automaticamente todas as conclusões apresentadas pelo modelo.

5.5 Aprimoramento do prompt

Revisar as instruções fornecidas ao modelo, acrescentando critérios para analisar diferentes canais de comunicação, orientações mais precisas sobre os conceitos técnicos e parâmetros específicos para classificar os riscos.

6. Considerações finais

Os resultados mostram que modelos de linguagem podem ajudar na análise inicial de mensagens suspeitas e na identificação de possíveis tentativas de phishing.

Nos dez experimentos, o protótipo conseguiu reconhecer diferentes modalidades de ameaça, identificar características de engenharia social e distinguir mensagens suspeitas de comunicações aparentemente legítimas.

Por outro lado, as inconsistências encontradas mostram que o uso de LLMs em Segurança da Informação ainda exige validação humana, critérios bem definidos e atenção às limitações do modelo.

A realização do projeto também permitiu explorar, na prática, a aplicação da Inteligência Artificial na Cibersegurança e desenvolver conhecimentos sobre Engenharia de Prompt, análise de ameaças, phishing e avaliação de riscos.

Por fim, é importante destacar que os resultados têm caráter exploratório. Eles não representam uma validação estatística da eficácia do modelo nem comprovam sua capacidade de detectar ataques reais.
