<h1 align="center">📋 Registros dos Testes: Phishing Detector (Versão 1.1)</h1>

---

## 📖 1. Apresentação

Este documento reúne os registros dos dez testes realizados com a segunda versão do prompt do projeto Phishing Detector, desenvolvido com o auxílio de um Modelo de Linguagem (LLM).

Os experimentos tiveram como objetivo avaliar as melhorias implementadas no prompt após a identificação de limitações durante a primeira rodada de testes.

Os cenários foram mantidos para permitir a comparação entre as versões 1.0 e 1.1, observando possíveis mudanças na identificação de indicadores de phishing, na classificação de riscos, na precisão conceitual e no reconhecimento das limitações do modelo.

Todos os cenários utilizaram a empresa fictícia Meridional e foram elaborados exclusivamente para fins educacionais.

---

## 🔬 2. Metodologia

Os testes foram conduzidos com o prompt versão 1.1, e os mesmos cenários da primeira rodada foram submetidos ao ChatGPT.

Cada resposta foi avaliada a partir dos seguintes critérios:

- ✔️ Classificação da mensagem
- ✔️ Nível de risco atribuído
- ✔️ Identificação dos indicadores de phishing
- ✔️ Diferenciação entre evidências e suspeitas
- ✔️ Coerência da análise apresentada
- ✔️ Qualidade das recomendações de segurança
- ✔️ Reconhecimento das limitações técnicas
- ✔️ Precisão dos conceitos de Segurança da Informação

A avaliação foi qualitativa e feita manualmente, com a comparação dos resultados obtidos com aqueles registrados na versão 1.0.

---

## 🗂️ 3. Registros dos testes

### 🧪 Teste 01 — Falsa suspensão de conta

**🏷️ Tipo de ameaça:** Phishing por urgência  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

A mensagem informa ao destinatário que sua conta será bloqueada caso os dados cadastrais não sejam atualizados em até 12 horas.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Ameaça de suspensão da conta.
- Prazo de 12 horas para a atualização cadastral.
- Uso de urgência e de pressão psicológica.
- Solicitação de atualização de informações.
- Remetente não verificado.
- Link apresentado sem a identificação de uma página específica.
- Justificativa genérica para um suposto problema cadastral.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os principais indicadores de phishing, em especial a ameaça de bloqueio e o prazo curto para a atualização cadastral.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais organizada e distinguiu melhor os indicadores observados das informações que não puderam ser verificadas.

Como ponto positivo, o modelo reconheceu que a aparência institucional do domínio não comprova sua autenticidade.

Houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

A classificação média pode ser justificada pela ausência de solicitação explícita de credenciais e de evidência de comprometimento. Ainda assim, a possibilidade de coleta indevida de dados cadastrais continua representando um risco relevante.

O resultado indica uma análise mais detalhada, mas evidencia a necessidade de critérios mais consistentes para a classificação de risco.

---

### 🧪 Teste 02 — Falso suporte de TI

**🏷️ Tipo de ameaça:** Phishing para roubo de credenciais  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

A mensagem, supostamente enviada pelo departamento de Tecnologia, solicita que os funcionários informem suas senhas corporativas e seus códigos de autenticação para uma atualização de segurança.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto ✅</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Solicitação de senha corporativa.
- Solicitação de códigos de autenticação multifator.
- Suposta atualização de segurança.
- Possível uso indevido da identidade do suporte de TI.
- Link apresentado para validação.
- Pressão para fornecer informações de acesso.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente a tentativa de obtenção de credenciais e códigos de autenticação, classificando o cenário como muito suspeito e de alto risco.

Um avanço em relação à versão 1.0 foi a interpretação mais precisa do domínio: o modelo reconheceu que o link utilizava o mesmo domínio do remetente, sem classificá-lo automaticamente como externo ou malicioso.

Também foi importante o reconhecimento de que a correspondência entre os domínios não comprova a autenticidade da mensagem.

A resposta apresentou recomendações adequadas, como não compartilhar credenciais, não utilizar o link recebido e procurar os canais oficiais de TI.

---

### 🧪 Teste 03 — Comunicado de manutenção

**🏷️ Tipo de ameaça:** Cenário legítimo utilizado como controle  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

A mensagem informa aos funcionários sobre uma manutenção programada nos serviços internos da empresa. Não apresenta links, anexos ou solicitações de informações.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Sem indícios claros</td>
      <td align="center">Baixo ✅</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Comunicação informativa.
- Ausência de solicitação de credenciais.
- Ausência de links ou anexos.
- Ausência de ameaças ou pressão psicológica.
- Conteúdo compatível com um comunicado interno.

#### 🛠️ Avaliação técnica

O LLM apresentou uma classificação coerente com o cenário, sem identificar indevidamente uma tentativa de phishing.

A resposta também demonstrou cautela ao explicar que a ausência de indicadores suspeitos não comprova a autenticidade da mensagem.

Em comparação com a versão 1.0, a versão 1.1 apresentou melhor explicação das limitações técnicas, mencionando que a autenticidade do remetente não poderia ser confirmada apenas pelo conteúdo.

O resultado demonstra a importância de evitar falsos positivos durante a análise de mensagens.

---

### 🧪 Teste 04 — Falso comunicado do RH com anexo

**🏷️ Tipo de ameaça:** Phishing com anexo potencialmente malicioso  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

A mensagem apresenta um suposto comunicado do departamento de Recursos Humanos sobre informações salariais e disponibiliza um arquivo com extensão `.xlsm`, solicitando que o destinatário habilite macros para visualizar o conteúdo.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto ✅</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Suposta comunicação do departamento de RH.
- Arquivo com extensão `.xlsm`.
- Solicitação para habilitar macros.
- Possibilidade de execução de conteúdo ativo.
- Uso de informações salariais como chamariz.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os principais indicadores de risco relacionados ao anexo e à solicitação para habilitar macros.

Um ponto positivo foi a precisão técnica ao explicar que a extensão `.xlsm` permite a utilização de macros, mas não comprova, isoladamente, que o arquivo seja malicioso.

A versão 1.1 apresentou recomendações mais detalhadas, orientando o usuário a não habilitar macros, não abrir o arquivo e confirmar a comunicação diretamente com o RH por canais oficiais.

O resultado demonstra uma análise coerente e tecnicamente mais cuidadosa.

---

### 🧪 Teste 05 — Alteração fraudulenta de dados bancários

**🏷️ Tipo de ameaça:** Business Email Compromise (BEC)  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

Uma mensagem, assinada pela Diretoria da Meridional, solicita a alteração urgente dos dados bancários de um fornecedor. O destinatário é orientado a manter a solicitação em sigilo e realizar a alteração sem seguir o processo habitual de confirmação.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto ✅</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Solicitação de alteração de dados bancários.
- Uso de autoridade hierárquica.
- Urgência para executar a solicitação.
- Pedido de sigilo.
- Tentativa de contornar procedimentos internos.
- Ausência de confirmação independente da solicitação.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os indicadores de fraude associados ao cenário, especialmente a combinação de autoridade, urgência e solicitação de alteração bancária.

A resposta também reconheceu a necessidade de confirmação por um canal independente antes de qualquer alteração financeira.

Como melhoria, a versão 1.1 apresentou recomendações mais completas, incluindo a manutenção dos procedimentos internos de aprovação e a comunicação com as áreas responsáveis.

O cenário demonstra a capacidade do modelo de identificar características comuns de ataques BEC, mesmo sem um endereço de e-mail do remetente disponível na mensagem analisada.

---

### 🧪 Teste 06 — Falso SMS de entrega

**🏷️ Tipo de ameaça:** Smishing  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

Uma mensagem SMS informa que existe uma taxa pendente para a liberação de uma entrega. O destinatário é pressionado a realizar o pagamento ainda no mesmo dia por meio de um link, sob ameaça de devolução do pacote.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Cobrança inesperada de taxa.
- Prazo curto para pagamento.
- Ameaça de devolução do pacote.
- Link para realização de pagamento.
- Ausência de informações suficientes para confirmar a transportadora ou a entrega.
- Uso de urgência e pressão psicológica.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os principais indicadores de smishing, reconhecendo a tentativa de induzir o destinatário a realizar um pagamento por meio de um link.

A versão 1.1 apresentou uma análise mais detalhada das informações ausentes e deixou claro que não havia elementos suficientes para confirmar a existência de uma entrega ou a legitimidade da cobrança.

Entretanto, houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

A diferença demonstra que, mesmo com melhorias no prompt, a classificação de risco ainda pode apresentar inconsistências.

---

### 🧪 Teste 07 — Falso comunicado com QR Code

**🏷️ Tipo de ameaça:** Quishing  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

Uma comunicação fictícia informa que os funcionários devem realizar uma atualização de autenticação por meio de um QR Code, estabelecendo um prazo de 18 horas e ameaçando suspender o acesso à conta caso o procedimento não seja realizado.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Solicitação de autenticação por QR Code.
- Prazo de 18 horas.
- Ameaça de suspensão de acesso.
- Uso de urgência e pressão psicológica.
- Ausência de informações suficientes para confirmar a legitimidade da solicitação.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os indicadores de quishing, reconhecendo o risco associado à utilização de QR Codes para direcionar usuários a páginas fraudulentas.

A versão 1.1 apresentou uma limitação importante de forma adequada: como o cenário apresentava apenas uma comunicação textual, sem uma imagem real do QR Code ou seu endereço de destino, não era possível verificar o conteúdo para o qual o código direcionaria o usuário.

A resposta também apresentou recomendações apropriadas, como não escanear o código e confirmar a solicitação pelos canais oficiais.

Assim como no teste 06, houve divergência no nível de risco em relação à versão 1.0, que havia atribuído risco alto.

---

### 🧪 Teste 08 — Coleta indevida de dados por falsa solicitação da Diretoria

**🏷️ Tipo de ameaça:** Spear phishing e engenharia social  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

Uma mensagem supostamente enviada pela Diretoria solicita uma planilha contendo nomes, CPF, cargos, salários e dados bancários dos funcionários. A solicitação apresenta urgência, exige sigilo e orienta o destinatário a não utilizar os canais habituais de compartilhamento.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto ✅</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Solicitação de grande volume de dados pessoais.
- Solicitação de informações financeiras.
- Uso de autoridade hierárquica.
- Urgência para o envio da planilha.
- Pedido de sigilo.
- Tentativa de contornar procedimentos internos.
- Ausência de confirmação independente da solicitação.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os indicadores de engenharia social e o risco associado ao compartilhamento indevido de informações dos funcionários.

Um avanço importante da versão 1.1 foi a maior precisão conceitual na diferenciação entre dados pessoais, informações financeiras e dados pessoais sensíveis, conforme a terminologia da LGPD.

A resposta reconheceu que nomes, CPF e informações profissionais são dados pessoais, enquanto salário e dados bancários são informações de natureza financeira. Essas informações não são automaticamente classificadas como dados pessoais sensíveis pela definição do artigo 5º, inciso II, da LGPD.

O modelo também recomendou não enviar a planilha, confirmar a solicitação por um canal independente e seguir os procedimentos internos de proteção e compartilhamento de dados.

O resultado demonstra uma evolução importante na precisão técnica e conceitual da análise.

---

### 🧪 Teste 09 — Falso aviso de redefinição de senha

**🏷️ Tipo de ameaça:** Phishing para roubo de credenciais  
**📌 Versão do prompt:** 1.1

#### 📝 Descrição do cenário

A mensagem informa que a senha corporativa do destinatário precisa ser redefinida e ameaça bloquear o acesso à conta caso o procedimento não seja realizado por meio do link apresentado.

#### 🎯 Resultado

<table width="100%">
  <thead>
    <tr>
      <th width="20%" align="left">Avaliação</th>
      <th align="center">Classificação</th>
      <th align="center">Nível de risco</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Esperado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Alto</td>
    </tr>
    <tr>
      <td><b>Observado</b></td>
      <td align="center">Muito suspeito</td>
      <td align="center">Médio ⚠️</td>
    </tr>
  </tbody>
</table>

#### 🔍 Indicadores identificados

- Solicitação de redefinição de senha.
- Ameaça de bloqueio da conta.
- Link para realização do procedimento.
- Uso de urgência e pressão psicológica.
- Possibilidade de captura de credenciais.
- Ausência de confirmação da legitimidade da página apresentada.

#### 🛠️ Avaliação técnica

O LLM identificou corretamente os principais indicadores de phishing,
