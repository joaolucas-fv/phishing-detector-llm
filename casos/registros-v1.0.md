# 🧪 Registros dos Testes: Phishing Detector (Versão 1.0)

## 📌 Apresentação

Este documento reúne os registros dos dez testes realizados com a primeira versão do prompt do projeto Phishing Detector, desenvolvido com o auxílio de um Modelo de Linguagem (LLM).

Os experimentos tiveram como objetivo avaliar a capacidade do ChatGPT de identificar possíveis tentativas de phishing, reconhecer técnicas de engenharia social, analisar riscos e distinguir mensagens suspeitas de comunicações aparentemente legítimas.

Todos os cenários utilizaram a empresa fictícia Meridional, e as mensagens foram elaboradas exclusivamente para fins educacionais.

## 🔬 Metodologia

Os testes foram conduzidos com o prompt versão 1.0, e as mensagens fictícias foram submetidas à análise do ChatGPT.

Cada resultado foi avaliado a partir dos seguintes critérios:

- Classificação da mensagem.
- Nível de risco atribuído.
- Identificação dos indicadores de phishing.
- Coerência da análise.
- Identificação dos possíveis impactos.
- Qualidade das recomendações.
- Reconhecimento das limitações do modelo.

A avaliação foi qualitativa e feita manualmente. Os resultados registrados correspondem às respostas observadas durante os experimentos, acompanhadas da avaliação técnica realizada no âmbito do projeto.

## 📋 Registros dos testes

### ✅ Teste 01 — Falsa suspensão de conta

**Tipo de ameaça:** Phishing por urgência.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

A mensagem informa ao destinatário que sua conta será bloqueada caso os dados cadastrais não sejam atualizados em até 12 horas. Para isso, apresenta uma suposta situação de segurança e incentiva o usuário a acessar um link de atualização.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Ameaça de suspensão da conta.
- Prazo reduzido para a atualização cadastral.
- Uso de urgência e de pressão psicológica.
- Remetente não verificado.
- Presença de link para atualização de dados.

**Avaliação técnica:**

O LLM identificou corretamente os principais indicadores de phishing, em especial a ameaça de bloqueio e o prazo curto para a atualização cadastral.

A combinação desses elementos pode ser usada para pressionar o destinatário e levá-lo a informar dados pessoais em uma página potencialmente fraudulenta.

A classificação foi considerada coerente com as características da mensagem.

### ⚠️ Teste 02 — Falso suporte de TI

**Tipo de ameaça:** Phishing para roubo de credenciais.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

A mensagem, supostamente enviada pelo departamento de Tecnologia, solicita que os funcionários informem suas senhas corporativas e seus códigos de autenticação para a realização de uma atualização de segurança.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Solicitação de senha corporativa.
- Solicitação de código de autenticação.
- Uso de urgência.
- Possível personificação do departamento de TI.
- Presença de link para validação de conta.
- Remetente não verificado.

**Avaliação técnica:**

O LLM identificou corretamente os principais indicadores de phishing e os riscos associados ao roubo de credenciais.

No entanto, descreveu o link como externo, quando ele utilizava o mesmo domínio exibido no endereço do remetente.

Essa imprecisão mostra que o modelo pode interpretar de forma equivocada informações técnicas, o que torna necessária a validação humana das respostas.

### ✅ Teste 03 — Comunicação de manutenção programada

**Tipo de mensagem:** Comunicação corporativa aparentemente legítima.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

O comunicado informa aos colaboradores sobre uma manutenção programada nos sistemas internos da empresa, sem solicitar informações pessoais nem exigir qualquer ação por parte dos funcionários.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Sem indícios claros | Baixo |
| **Observado** | Sem indícios claros | Baixo |

**Indicadores identificados:**

- Ausência de solicitação de credenciais.
- Ausência de pressão psicológica.
- Ausência de links ou anexos.
- Conteúdo meramente informativo.
- Remetente não autenticado.

**Avaliação técnica:**

O LLM classificou adequadamente a mensagem como uma comunicação sem indícios claros de phishing.

Merece destaque o fato de o modelo ter reconhecido que a aparência profissional de uma mensagem não comprova a legitimidade do remetente.

O resultado indica que o modelo é capaz de evitar a classificação indevida de uma comunicação aparentemente legítima.

### ✅ Teste 04 — Anexo com macros

**Tipo de ameaça:** Phishing com possível distribuição de malware.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

A mensagem, supostamente enviada pelo departamento de Recursos Humanos, informa sobre uma atualização da folha salarial e solicita que o funcionário abra um arquivo com extensão .xlsm e habilite a execução de macros.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Anexo com extensão .xlsm.
- Solicitação para habilitar macros.
- Uso de informações salariais como isca.
- Possível personificação do departamento de RH.
- Remetente não verificado.

**Avaliação técnica:**

O LLM identificou corretamente os riscos associados ao anexo e à solicitação para habilitar macros.

O modelo também reconheceu a possibilidade de distribuição de malware, de roubo de informações e de comprometimento dos sistemas corporativos.

Como ponto positivo, não afirmou que o arquivo continha código malicioso, já que essa confirmação dependeria da análise técnica do próprio arquivo.

### ✅ Teste 05 — Business Email Compromise (BEC)

**Tipo de ameaça:** Fraude por comprometimento ou personificação de e-mail corporativo.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

A mensagem, supostamente enviada pela diretoria, solicita a alteração dos dados bancários de um fornecedor e exige que o pagamento seja feito com urgência e sigilo.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Solicitação urgente de pagamento.
- Alteração dos dados bancários de fornecedor.
- Pedido de sigilo sobre a operação.
- Possível personificação da diretoria.
- Ausência de validação independente.

**Avaliação técnica:**

O LLM identificou corretamente os indicadores de BEC e de engenharia social.

Reconheceu os riscos de desvio financeiro e recomendou que a solicitação fosse confirmada por um canal independente antes de qualquer pagamento.

O modelo também demonstrou compreender como o uso de autoridade, urgência e confidencialidade pode ser empregado para manipular funcionários.

### ✅ Teste 06 — Smishing

**Tipo de ameaça:** Phishing por SMS.
**Empresa:** Meridional (fictícia, utilizada como referência nos experimentos).

**Descrição do cenário:**

A mensagem de texto informa sobre uma suposta pendência na entrega de uma encomenda e exige o pagamento de uma taxa para evitar a devolução do pacote.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Remetente não identificado.
- Cobrança inesperada.
- Urgência para a realização do pagamento.
- Ameaça de devolução da encomenda.
- Link para suposta regularização.

**Avaliação técnica:**

O LLM reconheceu corretamente os indicadores de Smishing e identificou o uso de urgência e de pressão psicológica para induzir o destinatário a efetuar um pagamento.

Também apontou os possíveis riscos de fraude financeira, de roubo de dados pessoais e de direcionamento para páginas fraudulentas.

> [!NOTE]
> **Observação metodológica:** o prompt versão 1.0 foi descrito, inicialmente, como um analisador de mensagens de e-mail. Este cenário ampliou o escopo de forma experimental para incluir mensagens SMS, sem que o prompt original tivesse sido formalmente atualizado.

### ✅ Teste 07 — Quishing

**Tipo de ameaça:** Phishing por QR Code.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

O comunicado informa sobre uma suposta atualização do sistema de autenticação corporativa e solicita que os funcionários escaneiem um QR Code para validar suas contas.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Falsa atualização de autenticação.
- Solicitação de validação de contas.
- Prazo limite para a realização do procedimento.
- Ameaça de suspensão do acesso.
- Uso de QR Code para direcionamento a uma página.
- Possível personificação do departamento de Tecnologia.

**Avaliação técnica:**

O LLM identificou corretamente os indicadores de Quishing e reconheceu que códigos QR podem ser usados para direcionar usuários a páginas fraudulentas.

O modelo também apontou os riscos de roubo de credenciais e de comprometimento da autenticação.

Como não foi fornecido um QR Code real, a análise limitou-se ao conteúdo textual do comunicado, e o modelo não verificou nenhum endereço de destino.

> [!NOTE]
> **Observação metodológica:** assim como no teste anterior, este cenário ampliou, de forma experimental, o escopo originalmente descrito no prompt versão 1.0.

### ⚠️ Teste 08 — Spear Phishing e solicitação de dados dos colaboradores

**Tipo de ameaça:** Engenharia social e possível phishing direcionado.
**Empresa:** Meridional (fictícia).

**Descrição do cenário:**

A mensagem, supostamente enviada pela diretoria, solicita uma planilha com nomes completos, CPFs, cargos, salários e dados bancários dos colaboradores.

A comunicação estabelece um prazo para o envio das informações e pede que os canais habituais de validação não sejam utilizados.

| Resultado | Classificação | Nível de risco |
|---|---|---|
| **Esperado** | Muito suspeito | Alto |
| **Observado** | Muito suspeito | Alto |

**Indicadores identificados:**

- Solicitação de dados pessoais.
- Solicitação de informações financeiras.
- Uso de urgência.
- Pedido de confidencialidade.
- Possível personificação da diretoria.
- Desvio dos procedimentos internos.
- Remetente não verificado.

**Avaliação técnica:**

O LLM identificou corretamente os indicadores de
