<h1 align="center">🛡️ Avaliação dos Resultados: Phishing Detector com LLM</h1>

---

## 🎯 1. Objetivo da avaliação

Nesta etapa, o objetivo é analisar o desempenho do Modelo de Linguagem utilizado no protótipo Phishing Detector, levando em consideração os resultados dos dez testes realizados.

A avaliação busca observar os pontos positivos, identificar possíveis inconsistências nas respostas e compreender as limitações do modelo ao analisar ameaças relacionadas a phishing e engenharia social.

---

## 📊 2. Análise geral do desempenho

Ao longo dos experimentos, o LLM demonstrou ser capaz de reconhecer diferentes características comuns em tentativas de phishing, como:

- Uso de urgência e de pressão psicológica.
- Solicitação indevida de credenciais.
- Tentativas de obter dados pessoais e financeiros.
- Personificação de departamentos e de figuras de autoridade.
- Direcionamento para links potencialmente suspeitos.
- Uso de anexos que podem conter macros maliciosas.
- Uso de SMS e de QR Codes como meios para aplicar fraudes.

O modelo também conseguiu reconhecer mensagens aparentemente legítimas. Isso ficou evidente no fato de não ter classificado automaticamente uma comunicação como phishing apenas porque ela apresentava determinados elementos, como um link.

---

## ✅ 3. Pontos positivos identificados

### 3.1 Identificação de diferentes modalidades de phishing

O LLM conseguiu analisar situações envolvendo phishing tradicional, Smishing, Quishing, Spear Phishing e Business Email Compromise (BEC).

Esse resultado mostra que o modelo pode servir de apoio na identificação inicial de diferentes técnicas de engenharia social.

### 3.2 Reconhecimento de engenharia social

O modelo identificou situações em que autoridade, urgência, medo e confidencialidade eram utilizados para influenciar o comportamento dos funcionários.

Essas características apareceram principalmente nos testes relacionados ao falso suporte de TI, à alteração de dados bancários e à solicitação de informações dos colaboradores.

### 3.3 Diferenciação entre mensagens suspeitas e aparentemente legítimas

Nos testes 03 e 10, o modelo classificou as mensagens como sem indícios claros de phishing.

Esse comportamento indica que a ferramenta não se baseia apenas na presença de links ou no uso de uma comunicação institucional para decidir se uma mensagem representa uma ameaça.

### 3.4 Recomendações de segurança

As respostas também trouxeram orientações preventivas importantes, entre elas:

- Conferir a autenticidade do remetente.
- Utilizar canais oficiais de comunicação.
- Não compartilhar senhas ou códigos de autenticação.
- Comunicar possíveis incidentes à equipe de Segurança da Informação.
- Confirmar solicitações financeiras antes de realizar pagamentos.

---

## ⚠️ 4. Limitações e inconsistências identificadas

Apesar dos resultados positivos, os experimentos também permitiram observar algumas limitações do modelo.

### 4.1 Interpretação incorreta de informações

No teste 02, o modelo descreveu o link como externo, embora ele utilizasse o mesmo domínio apresentado no endereço do remetente.

Esse caso mostra que o LLM pode interpretar de maneira incorreta alguns elementos técnicos. Por isso, as informações apresentadas na análise precisam ser conferidas.

### 4.2 Imprecisão conceitual sobre a LGPD

No teste 08, o modelo classificou CPF, salário e dados bancários como dados pessoais sensíveis.

No entanto, essas informações não fazem parte automaticamente das categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

O resultado mostra que modelos de linguagem podem apresentar imprecisões conceituais e jurídicas, mesmo quando suas respostas parecem bem estruturadas.

### 4.3 Divergência na classificação de risco

No teste 09, o modelo classificou a mensagem como muito suspeita, mas atribuiu a ela nível de risco médio. O resultado esperado para esse cenário era alto.

Essa diferença mostra que a classificação do risco pode variar conforme a interpretação do modelo e as informações disponíveis durante a análise.

Por esse motivo, é importante estabelecer critérios mais objetivos para orientar a atribuição dos níveis de risco.

### 4.4 Dependência das informações fornecidas

As análises foram feitas com base no conteúdo textual apresentado pelo usuário. Durante os testes, não foram realizadas verificações técnicas reais de:

- Autenticidade dos remetentes.
- Reputação dos domínios.
- Destino dos links.
- Conteúdo dos anexos.
- Destino dos QR Codes.

Assim, as classificações devem ser entendidas como análises preliminares. Elas não comprovam, por si só, a existência ou a inexistência de uma ameaça.

---

## 🚀 5. Oportunidades de melhoria

A partir dos resultados, foram identificadas oportunidades de melhoria que orientaram o desenvolvimento da versão 1.1 do prompt. Algumas dessas melhorias foram incorporadas às novas instruções, enquanto outras permanecem como possibilidades de evolução do projeto.

### 5.1 Aprimoramento dos critérios de classificação

Definir orientações mais claras para diferenciar os níveis de risco baixo, médio e alto.

### 5.2 Melhoria da precisão técnica

Incluir instruções para que o modelo diferencie informações confirmadas, suspeitas e não verificadas. Dessa forma, será possível evitar conclusões que não tenham apoio no conteúdo analisado.

### 5.3 Ampliação dos cenários de teste

Criar novos exemplos que envolvam outras técnicas de phishing, diferentes canais de comunicação e situações do ambiente corporativo.

### 5.4 Validação das respostas

Comparar as respostas do LLM com referências confiáveis de Segurança da Informação, em vez de aceitar automaticamente todas as conclusões apresentadas pelo modelo.

### 5.5 Aprimoramento do prompt

Revisar as instruções fornecidas ao modelo, acrescentando critérios para analisar diferentes canais de comunicação, orientações mais precisas sobre os conceitos técnicos e parâmetros específicos para a classificação dos riscos.

---

## 🏁 6. Considerações finais

Os resultados mostram que modelos de linguagem podem auxiliar na análise inicial de mensagens suspeitas e na identificação de possíveis tentativas de phishing.

Nos dez experimentos, o protótipo conseguiu reconhecer diferentes modalidades de ameaça, identificar características de engenharia social e distinguir mensagens suspeitas de comunicações aparentemente legítimas.

Por outro lado, as inconsistências encontradas mostram que o uso de LLMs em Segurança da Informação ainda exige validação humana, critérios bem definidos e atenção às limitações do modelo.

A realização do projeto também permitiu explorar, na prática, a aplicação da Inteligência Artificial na Cibersegurança e desenvolver conhecimentos sobre Engenharia de Prompt, análise de ameaças, phishing e avaliação de riscos.

> [!NOTE]
> Por fim, é importante destacar que os resultados têm caráter exploratório. Eles não representam uma validação estatística da eficácia do modelo, nem comprovam sua capacidade de detectar ataques reais.
