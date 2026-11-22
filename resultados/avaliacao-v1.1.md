<h1 align="center">🛡️ Avaliação dos Resultados: Phishing Detector com LLM (Versão 1.1)</h1>

---

## 🎯 1. Objetivo da avaliação

Esta etapa tem como objetivo analisar o comportamento do Modelo de Linguagem utilizado na segunda versão do protótipo Phishing Detector, considerando os resultados dos dez testes realizados.

A avaliação busca identificar as melhorias observadas após a atualização do prompt, verificar se as limitações encontradas na primeira versão foram corrigidas e analisar quais aspectos ainda precisam de aprimoramento.

Os resultados também são comparados com os da primeira rodada de experimentos, o que permite observar as diferenças no comportamento do modelo diante dos mesmos cenários.

---

## 📊 2. Análise geral do desempenho

Ao longo dos dez experimentos, o LLM demonstrou ser capaz de identificar diferentes características de phishing e de engenharia social, entre elas:

- Uso de urgência e de pressão psicológica.
- Solicitação indevida de credenciais e de códigos de autenticação.
- Tentativas de obter dados pessoais e financeiros.
- Personificação de gestores e de departamentos corporativos.
- Alterações suspeitas de dados bancários.
- Uso de anexos com macros.
- Direcionamento para links e possíveis páginas fraudulentas.
- Uso de SMS e de QR Codes em tentativas de fraude.
- Tentativas de contornar procedimentos internos de segurança.

O modelo também demonstrou maior atenção à diferenciação entre informações confirmadas, suspeitas e não verificadas.

Outro aspecto positivo foi o reconhecimento mais detalhado das limitações técnicas, principalmente em situações que exigiriam a verificação de domínios, remetentes, links, anexos ou QR Codes.

### 2.1 Resumo das classificações

Ao final dos dez experimentos, foram observados os seguintes resultados:

- Oito mensagens foram classificadas como muito suspeitas.
- Duas mensagens foram classificadas como sem indícios claros de phishing.

### 2.2 Resumo dos níveis de risco

- Quatro mensagens receberam nível de risco alto.
- Quatro mensagens receberam nível de risco médio.
- Duas mensagens receberam nível de risco baixo.

Esses resultados correspondem às classificações fornecidas pelo modelo durante os experimentos e não constituem uma medição estatística de precisão.

---

## ✅ 3. Pontos positivos identificados

### 3.1 Melhoria na identificação de indicadores

O LLM apresentou respostas mais detalhadas na identificação de possíveis indicadores de phishing.

Durante os testes, mostrou-se capaz de reconhecer solicitações suspeitas, uso de autoridade institucional, pressão psicológica e tentativas de obtenção de informações confidenciais.

Passou também a distinguir melhor os elementos efetivamente observados daqueles que não poderiam ser confirmados apenas pelo conteúdo textual.

### 3.2 Maior precisão na interpretação técnica

Uma melhoria importante foi observada no teste 02.

Na versão 1.0, o modelo descreveu de forma incorreta um link como externo, embora ele utilizasse o mesmo domínio apresentado no remetente.

Na versão 1.1, essa imprecisão foi corrigida. O modelo reconheceu a correspondência entre os domínios, sem considerar essa característica como comprovação de autenticidade.

O mesmo comportamento foi observado nos testes envolvendo redefinição de senha e comunicação com a intranet corporativa.

### 3.3 Melhoria na precisão conceitual sobre a LGPD

Um dos resultados mais relevantes ocorreu no teste 08.

Na primeira versão, o modelo classificou CPF, salário e dados bancários como dados pessoais sensíveis.

Na versão 1.1, essa imprecisão foi corrigida.

O modelo passou a diferenciar dados pessoais e informações financeiras das categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

Essa melhoria demonstra a importância de incluir instruções específicas de precisão conceitual nos prompts utilizados em aplicações relacionadas à Segurança da Informação.

### 3.4 Reconhecimento das limitações técnicas

A versão 1.1 apresentou descrições mais completas sobre as verificações que não puderam ser realizadas durante os experimentos.

Entre as limitações reconhecidas estão:

- Impossibilidade de confirmar a autenticidade dos remetentes.
- Ausência de verificação da propriedade dos domínios.
- Impossibilidade de inspecionar links e identificar redirecionamentos.
- Ausência de análise técnica de anexos.
- Impossibilidade de verificar o destino de QR Codes sem acesso ao seu conteúdo.
- Ausência de análise dos mecanismos SPF, DKIM e DMARC.

Esse comportamento contribuiu para tornar as respostas mais cautelosas, evitando conclusões sem evidências suficientes.

### 3.5 Recomendações de segurança mais completas

As respostas passaram a apresentar orientações mais específicas para diferentes situações.

Entre elas:

- Confirmação de solicitações por canais independentes.
- Verificação de alterações bancárias com fornecedores.
- Comunicação de incidentes à equipe de Segurança da Informação.
- Revogação de sessões potencialmente comprometidas.
- Preservação de mensagens para investigação.
- Uso de procedimentos oficiais de resposta a incidentes.

Essas recomendações mostraram maior detalhamento na orientação dos usuários.

### 3.6 Diferenciação entre mensagens suspeitas e aparentemente legítimas

Nos testes 03 e 10, o modelo manteve a classificação sem indícios claros de phishing, com nível de risco baixo.

Demonstrou também reconhecer que a presença de um link ou de um remetente com aparência institucional não comprova, isoladamente, a existência de uma ameaça.

Esse comportamento é importante para evitar a classificação indevida de comunicações aparentemente legítimas.

---

## ⚠️ 4. Limitações e inconsistências identificadas

Apesar das melhorias observadas, os experimentos mostraram que algumas limitações permaneceram.

### 4.1 Divergência na classificação de risco

Nos testes 01, 06 e 07, o modelo classificou as mensagens como muito suspeitas, mas atribuiu nível de risco médio, enquanto o resultado esperado era alto.

No teste 09, a mesma divergência já havia sido observada na primeira versão, pois o modelo também atribuiu risco médio.

Esses resultados mostram que a atualização do prompt não resolveu por completo a inconsistência na classificação de risco.

Embora a classificação como muito suspeito tenha sido mantida, a atribuição do nível de risco variou conforme a interpretação do modelo sobre as evidências disponíveis e sobre os possíveis impactos.

Essa situação indica a necessidade de critérios mais objetivos e consistentes para a avaliação de risco.

### 4.2 Persistência de limitações na interpretação do contexto

No teste 05, relacionado à fraude BEC, o modelo apresentou uma análise fundamentada nos indicadores comportamentais da mensagem.

No entanto, a análise dependeu das informações efetivamente fornecidas no cenário, e não foi possível confirmar a identidade de quem enviou a comunicação.

Esse resultado reforça a importância de fornecer informações completas e de não presumir características que não estejam presentes na mensagem analisada.

### 4.3 Dependência das informações fornecidas

Mesmo com as melhorias do prompt, o modelo continuou dependendo do conteúdo apresentado pelo usuário.

Durante os experimentos, não foram realizadas verificações técnicas reais de:

- Autenticidade dos remetentes.
- Reputação dos domínios.
- Destino dos links.
- Conteúdo dos anexos.
- Destino dos QR Codes.
- Cabeçalhos técnicos de e-mail.
- Integridade dos sistemas corporativos.

Por consequência, as classificações representam análises preliminares e não comprovam a existência ou a inexistência de uma ameaça.

### 4.4 Limitações na calibração de risco

Os testes mostraram que o modelo pode reconhecer corretamente uma ameaça e, ainda assim, apresentar divergências na atribuição de seu nível de risco.

Essa diferença reforça que classificar uma mensagem como suspeita e avaliar a gravidade de seus possíveis impactos são análises distintas.

Portanto, a atribuição de risco ainda precisa ser aprimorada para produzir resultados mais consistentes.

---

## 🚀 5. Oportunidades de melhoria

Com base nos experimentos realizados, foram identificadas novas oportunidades de evolução do projeto.

### 5.1 Aprimoramento dos critérios de risco

Desenvolver critérios ainda mais específicos para diferenciar riscos baixos, médios e altos.

A classificação deverá considerar tanto os indicadores observados quanto a gravidade dos possíveis impactos.

### 5.2 Maior consistência nas respostas

Aprimorar as instruções para reduzir interpretações incorretas e garantir que todas as informações relevantes fornecidas pelo usuário sejam consideradas durante a análise.

### 5.3 Ampliação da avaliação experimental

Realizar novos testes com diferentes modelos de linguagem e ampliar a quantidade de cenários analisados.

Isso permitiria verificar se o comportamento identificado se mantém em diferentes condições de uso.

### 5.4 Validação técnica complementar

Explorar, futuramente, ferramentas especializadas que permitam complementar a análise realizada pelo LLM, principalmente na verificação de domínios, links e arquivos suspeitos.

### 5.5 Aprimoramento contínuo do prompt

Continuar revisando as instruções do modelo com base nas inconsistências identificadas durante os experimentos.

As melhorias deverão considerar os resultados observados, evitando alterações que apenas forcem o modelo a apresentar as classificações esperadas sem justificativa técnica.

---

## 🏁 6. Considerações finais

A segunda rodada de experimentos mostrou melhorias qualitativas no comportamento do Modelo de Linguagem utilizado no protótipo Phishing Detector.

A atualização do prompt contribuiu para uma análise mais organizada, para maior precisão conceitual e para um melhor reconhecimento das limitações técnicas do modelo.

Um dos resultados mais relevantes foi a correção da imprecisão relacionada à classificação de dados pessoais e dados pessoais sensíveis segundo a LGPD.

Também foram observadas melhorias na interpretação de domínios, na identificação de informações não verificadas e na apresentação de recomendações preventivas.

No entanto, as divergências na classificação de risco mostraram que o aprimoramento das instruções não elimina todas as limitações dos modelos de linguagem.

O desenvolvimento do projeto permitiu explorar a aplicação prática da Engenharia de Prompt na Cibersegurança, além de desenvolver conhecimentos relacionados a phishing, engenharia social, proteção de dados e análise de riscos.

> [!NOTE]
> Por fim, é importante destacar que os resultados possuem caráter exploratório e qualitativo. Os experimentos não representam uma validação estatística da eficácia do modelo, nem comprovam sua capacidade de detectar ataques reais.

> [!IMPORTANT]
> O LLM deve ser utilizado como ferramenta complementar, e não como substituto de ferramentas especializadas de segurança ou da avaliação humana.
