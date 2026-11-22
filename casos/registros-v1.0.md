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

| | Classificação | Nível de risco |
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

| | Classificação | Nível de risco |
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

| | Classificação | Nível de risco |
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

O resultado indica que o modelo é capaz de evitar a classificação indevida de uma comunicação
