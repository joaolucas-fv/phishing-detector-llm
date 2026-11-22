# 📋 Registros dos Testes: Phishing Detector (Versão 1.1)

---

## 1. Apresentação

Este documento reúne os registros dos **dez testes** realizados com a **segunda versão do prompt** do projeto Phishing Detector, desenvolvido com o auxílio de um Modelo de Linguagem (LLM).

Os experimentos tiveram como objetivo avaliar as melhorias implementadas no prompt após a identificação de limitações durante a primeira rodada de testes.

Os cenários foram mantidos para permitir a comparação entre as versões 1.0 e 1.1, observando possíveis mudanças na identificação de indicadores de phishing, na classificação de riscos, na precisão conceitual e no reconhecimento das limitações do modelo.

> [!NOTE]
> Todos os cenários utilizaram a empresa fictícia **Meridional** e foram elaborados exclusivamente para fins educacionais.

---

## 2. Metodologia

Os testes foram conduzidos com o prompt **versão 1.1**, e os mesmos cenários da primeira rodada foram submetidos ao ChatGPT.

Cada resposta foi avaliada a partir dos seguintes critérios:

- Classificação da mensagem.
- Nível de risco atribuído.
- Identificação dos indicadores de phishing.
- Diferenciação entre evidências e suspeitas.
- Coerência da análise apresentada.
- Qualidade das recomendações de segurança.
- Reconhecimento das limitações técnicas.
- Precisão dos conceitos de Segurança da Informação.

A avaliação foi **qualitativa** e feita manualmente, com a comparação dos resultados obtidos com aqueles registrados na versão 1.0.

---

## 3. Registros dos testes

### 🧪 Teste 01 — Falsa suspensão de conta

**Tipo de ameaça:** Phishing por urgência.
**Versão do prompt:** 1.1.

**Descrição do cenário:**
A mensagem informa ao destinatário que sua conta será bloqueada caso os dados cadastrais não sejam atualizados em até 12 horas.

**Resultado esperado:**
- Classificação: Muito suspeito.
- Nível de risco: Alto.

**Resultado observado:**
- Classificação: Muito suspeito.
- Nível de risco: Médio.

**Indicadores identificados:**
- Ameaça de suspensão da conta.
- Prazo de 12 horas para a atualização cadastral.
- Uso de urgência e de pressão psicológica.
- Solicitação de atualização de informações.
- Remetente não verificado.
- Link apresentado sem a identificação de uma página específica.
- Justificativa genérica para um suposto problema cadastral.

**Avaliação técnica:**

O LLM identificou corretamente os principais indicadores de phishing, em especial a ameaça de bloqueio e o prazo curto para a atualização cadastral.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais organizada e distinguiu melhor os indicadores observados das informações que não puderam ser verificadas.

Como ponto positivo, o modelo reconheceu que a aparência institucional do domínio não comprova sua autenticidade.

Houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

A classificação média pode ser justificada pela ausência de solicitação explícita de credenciais e de evidência de comprometimento. Ainda assim, a possibilidade de coleta indevida de dados cadastrais continua representando um risco relevante.

O resultado indica uma análise mais detalhada, mas evidencia a necessidade de critérios mais consistentes para a classificação de risco.

---

### 🧪 Teste 02 — Falso suporte de TI

**Tipo de ameaça:** Phishing para roubo de credenciais.
**Versão do prompt:** 1.1.

**Descrição do cenário:**
A mensagem, supostamente enviada pelo departamento de Tecnologia, solicita que os funcionários informem suas senhas corporativas e seus códigos de autenticação para uma atualização de segurança.
