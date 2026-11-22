<h1 align="center">🔄 Comparação entre as Versões: Phishing Detector com LLM</h1>

---

## 🎯 1. Objetivo

Este documento apresenta uma comparação entre as duas versões do prompt desenvolvido para o projeto Phishing Detector.

O objetivo é analisar as mudanças observadas no comportamento do Modelo de Linguagem após o aprimoramento das instruções, considerando os resultados de vinte experimentos realizados em duas rodadas de testes.

A primeira rodada utilizou o prompt versão 1.0, enquanto a segunda utilizou a versão 1.1.

Os mesmos dez cenários serviram de referência para avaliar as mudanças na identificação de ameaças, na classificação de riscos, na precisão conceitual e no reconhecimento das limitações do modelo.

---

## 📊 2. Comparação geral dos resultados

As duas versões apresentaram resultados semelhantes na classificação geral das mensagens.

Em ambas as rodadas:

- Oito mensagens foram classificadas como muito suspeitas.
- Duas mensagens foram classificadas como sem indícios claros de phishing.

No entanto, foram observadas diferenças na atribuição dos níveis de risco.

**Versão 1.0:**

- Sete mensagens receberam nível de risco alto.
- Uma mensagem recebeu nível de risco médio.
- Duas mensagens receberam nível de risco baixo.

**Versão 1.1:**

- Quatro mensagens receberam nível de risco alto.
- Quatro mensagens receberam nível de risco médio.
- Duas mensagens receberam nível de risco baixo.

A principal diferença ocorreu na atribuição do nível de risco. A versão 1.1 classificou como risco médio três cenários anteriormente considerados de alto risco: falsa suspensão de conta, Smishing e Quishing.

No teste de falsa redefinição de senha, o risco médio foi mantido nas duas versões.

Essas diferenças mostram que a atualização das instruções influenciou a forma como o modelo avaliou a gravidade das situações apresentadas.

---

## 🧪 3. Comparação dos resultados por cenário

### Teste 01 — Falsa suspensão de conta

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente a ameaça de bloqueio da conta, o prazo reduzido e a pressão psicológica.

A versão 1.1 apresentou uma análise mais organizada e distinguiu melhor os elementos observados das informações não verificadas.

No entanto, houve divergência no nível de risco, que passou de alto para médio.

---

### Teste 02 — Falso suporte de TI

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente a tentativa de obtenção de senhas e de códigos de autenticação.

Na versão 1.0, o modelo apresentou uma imprecisão ao descrever o link como externo, embora ele utilizasse o mesmo domínio apresentado no remetente.

Na versão 1.1, essa interpretação foi corrigida. O modelo reconheceu a correspondência entre os domínios, sem considerar essa característica como prova de autenticidade.

A versão 1.1 também apresentou uma explicação mais detalhada sobre os riscos relacionados à autenticação multifator (MFA).

---

### Teste 03 — Comunicação de manutenção programada

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões reconheceram adequadamente a comunicação como uma mensagem sem indícios claros de phishing.

A versão 1.1 apresentou maior detalhamento sobre os riscos residuais, sobre a possibilidade de falsificação do remetente e sobre as limitações relacionadas aos mecanismos SPF, DKIM e DMARC.

A classificação permaneceu consistente entre as duas versões.

---

### Teste 04 — Anexo com macros

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente os riscos relacionados ao arquivo `.xlsm` e à solicitação para habilitar macros.

A versão 1.1 apresentou uma explicação mais detalhada sobre os possíveis impactos da execução de macros, além de recomendações mais específicas para a análise e a preservação do arquivo.

O modelo também demonstrou cautela ao não afirmar que a extensão do arquivo, isoladamente, comprova a presença de malware.

---

### Teste 05 — Business Email Compromise (BEC)

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente os indicadores de fraude financeira, de alteração de dados bancários, de urgência e de pedido de sigilo.

A versão 1.1 apresentou recomendações mais completas, entre elas os procedimentos a adotar nos casos em que uma transferência financeira já tenha sido realizada.

Desenvolveu ainda uma análise mais detalhada sobre a necessidade de validação independente e sobre os possíveis impactos financeiros e operacionais.

---

### Teste 06 — Smishing

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente a falsa cobrança de entrega, a urgência e a ameaça de devolução da encomenda.

A versão 1.1 apresentou uma análise mais detalhada sobre a ausência de identificação da transportadora, de código de rastreamento e de informações específicas da encomenda.

O modelo também reconheceu que o uso de HTTPS não comprova a legitimidade do endereço eletrônico.

No entanto, houve divergência no nível de risco, que passou de alto para médio.

---

### Teste 07 — Quishing

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões reconheceram o uso de QR Code como possível mecanismo de direcionamento para páginas fraudulentas.

A versão 1.1 apresentou maior detalhamento sobre as limitações da análise e destacou que não era possível confirmar a natureza maliciosa do código sem examinar seu conteúdo e seu destino.

Ampliou também as recomendações para situações em que o funcionário já tivesse escaneado o código ou fornecido suas credenciais.

A principal diferença foi a classificação do risco, que passou de alto para médio.

---

### Teste 08 — Spear Phishing e solicitação de dados dos colaboradores

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente a tentativa de obter informações pessoais e financeiras dos colaboradores, além do uso de autoridade, de urgência e de confidencialidade.

Uma das melhorias mais importantes foi observada neste teste.

Na versão 1.0, o modelo classificou de forma incorreta CPF, salário e dados bancários como dados pessoais sensíveis.

Na versão 1.1, essa imprecisão foi corrigida. O modelo passou a diferenciar dados pessoais e informações financeiras das categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

Essa mudança indica uma melhora na precisão conceitual após a inclusão de instruções específicas no prompt.

---

### Teste 09 — Falsa redefinição de senha

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões identificaram corretamente os indicadores de possível roubo de credenciais, entre eles a urgência, a ameaça de bloqueio e o direcionamento para um portal de redefinição.

A versão 1.1 apresentou uma explicação mais detalhada sobre as possibilidades de captura de credenciais e reconheceu as limitações relacionadas à verificação do portal.

No entanto, a divergência entre o nível de risco esperado, inicialmente definido como alto, e o nível observado, médio, permaneceu nas duas versões.

Isso mostra que o aprimoramento do prompt não resolveu por completo a inconsistência na classificação de risco.

---

### Teste 10 — Comunicação corporativa com link informativo

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Versão</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Versão 1.0</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo</td>
    </tr>
    <tr>
      <td><b>Versão 1.1</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo</td>
    </tr>
  </tbody>
</table>

#### 🔍 Análise comparativa

As duas versões reconheceram adequadamente a comunicação como uma mensagem sem indícios claros de phishing.

A versão 1.1 apresentou uma análise mais detalhada sobre a relação entre o domínio do remetente e o endereço da intranet.

Identificou também riscos residuais e explicou que a correspondência entre os domínios não comprova a autenticidade da comunicação.

A classificação permaneceu consistente entre as duas versões.

---

## ✅ 4. Principais melhorias observadas na versão 1.1

A comparação dos vinte experimentos permitiu identificar algumas melhorias relevantes.

### 4.1 Melhor interpretação de domínios e links

O modelo passou a diferenciar melhor a correspondência entre o domínio do remetente e o endereço apresentado na mensagem.

Essa mudança foi observada principalmente nos testes 02, 09 e 10.

### 4.2 Maior precisão conceitual

A imprecisão relacionada à LGPD, identificada no teste 08, foi corrigida.

O modelo passou a diferenciar corretamente dados pessoais, informações financeiras e dados pessoais sensíveis.

### 4.3 Maior reconhecimento das limitações

A versão 1.1 apresentou explicações mais completas sobre as informações que não poderiam ser verificadas apenas pelo conteúdo textual.

Entre os pontos observados estão a autenticidade dos remetentes, a propriedade dos domínios, o destino dos links e a análise técnica de anexos e QR Codes.

### 4.4 Recomendações mais detalhadas

As orientações de segurança ficaram mais específicas e passaram a incluir procedimentos de verificação independente, comunicação de incidentes e medidas iniciais de proteção de contas comprometidas.

### 4.5 Ampliação do escopo de análise

A versão 1.1 passou a contemplar formalmente diferentes canais de comunicação, entre eles e-mails, SMS, mensagens instantâneas, comunicados digitais e QR Codes.

---

## ⚠️ 5. Limitações que permaneceram

Apesar das melhorias, a comparação também identificou aspectos que ainda precisam de aprimoramento.

### 5.1 Inconsistência na classificação de risco

A versão 1.1 atribuiu nível de risco médio a três cenários que haviam recebido nível alto na primeira versão.

Além disso, manteve a classificação média no teste de falsa redefinição de senha.

Essas diferenças mostram que a classificação de risco ainda depende da interpretação do modelo e pode variar mesmo quando os indicadores de ameaça são semelhantes.

### 5.2 Dependência da qualidade das informações

O modelo continua dependendo das informações fornecidas pelo usuário.

Quando faltam dados sobre remetentes, links, anexos ou procedimentos corporativos, a análise permanece limitada.

### 5.3 Ausência de validação técnica automatizada

As duas versões realizaram análises baseadas no conteúdo fornecido, sem integração com ferramentas especializadas para verificar domínios, links, anexos ou códigos QR.

Portanto, as respostas não devem ser interpretadas como confirmações técnicas de segurança ou de comprometimento.

---

## 🏁 6. Conclusão comparativa

A comparação entre as versões 1.0 e 1.1 mostrou melhorias qualitativas na organização das análises, na interpretação de informações técnicas, na precisão conceitual e no reconhecimento das limitações do modelo.

Um dos resultados mais relevantes foi a correção da imprecisão relacionada à LGPD, além da melhora na interpretação de domínios e links.

Por outro lado, as divergências na classificação de risco mostraram que nem todas as limitações foram resolvidas após a atualização do prompt.

Os experimentos reforçam que a qualidade das instruções influencia o comportamento do LLM, mas não garante respostas totalmente precisas ou consistentes.

O desenvolvimento das duas versões permitiu compreender a importância da Engenharia de Prompt, da avaliação crítica das respostas e da validação humana em aplicações de Inteligência Artificial voltadas à Cibersegurança.

> [!IMPORTANT]
> Esta comparação possui caráter exploratório e qualitativo. Os vinte experimentos não constituem uma validação estatística da eficácia do modelo, nem permitem afirmar que a versão 1.1 apresenta maior precisão geral na detecção de ataques reais.
