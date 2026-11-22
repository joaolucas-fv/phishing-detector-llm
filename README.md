<div align="center">

# 🎣 Phishing Detector com LLM

**Análise preliminar de possíveis tentativas de phishing com apoio de um Modelo de Linguagem de Grande Escala**

`Segurança da Informação` • `Engenharia de Prompt` • `Finalidade Educacional`

</div>

---

## 📌 Sobre o projeto

Projeto educacional de Segurança da Informação que utiliza um **Modelo de Linguagem de Grande Escala (LLM)** para auxiliar na identificação e na análise preliminar de possíveis tentativas de phishing.

Ele foi desenvolvido para estudar como os LLMs podem apoiar a análise de mensagens suspeitas, identificar indicadores de risco e apresentar recomendações de segurança.

---

## 🎯 Objetivos

- 🔍 Explorar o uso de LLMs em atividades de Segurança da Informação.
- ✍️ Desenvolver e aprimorar prompts para a análise de possíveis tentativas de phishing.
- ⚖️ Comparar os resultados obtidos com diferentes versões de um prompt.
- ⚠️ Identificar limitações e possíveis inconsistências nas respostas do modelo.
- 📝 Documentar os testes e os resultados para fins de aprendizado.

---

## ⚙️ Como funciona

O projeto utiliza **mensagens fictícias** para simular diferentes situações de comunicação digital. O modelo analisa cada mensagem considerando os seguintes indicadores:

| 🔎 Indicador | 📋 O que é analisado |
|:---:|:---:|
| **Remetente e domínio** | Origem da mensagem e coerência do endereço |
| **Conteúdo e contexto** | Se o texto faz sentido para a situação apresentada |
| **Solicitações sensíveis** | Pedidos de senhas, códigos ou dados pessoais |
| **Links e anexos** | Presença de links ou arquivos suspeitos |
| **Urgência e pressão** | Urgência, ameaças e pressão psicológica |
| **Personificação** | Tentativas de se passar por pessoas ou organizações |

Ao final, o modelo apresenta:

> 🏷️ **Classificação** &nbsp;•&nbsp; 🚦 **Nível de risco** &nbsp;•&nbsp; 🧩 **Indicadores identificados** &nbsp;•&nbsp; 🛡️ **Recomendações de segurança**

---

## 🗂️ Estrutura do projeto

```text
📦 phishing-detector-llm
 ┣ 📂 prompts      → versões dos prompts utilizados
 ┣ 📂 casos        → registros dos cenários de teste
 ┣ 📂 resultados   → avaliações individuais e comparação entre as versões
 ┗ 📂 evidencias   → capturas de tela dos testes realizados
```

---

## 🧪 Metodologia

Foram elaborados **10 cenários fictícios** envolvendo diferentes situações de phishing, incluindo e-mails, SMS, mensagens com QR Code e tentativas de engenharia social.

Os mesmos cenários foram usados para avaliar duas versões do prompt:

| 🏷️ Versão | 📄 Descrição | 🧪 Avaliações |
|:---:|:---:|:---:|
| **1.0** | Prompt inicial | 10 |
| **1.1** | Prompt revisado, com melhorias de escopo, critérios de classificação, precisão técnica e apresentação das limitações | 10 |
| **Total** | — | **20** |

---

## 📊 Resultados

- ✅ A revisão do prompt trouxe **melhorias na precisão técnica** das respostas e na **identificação das limitações** da análise.
- 🔄 Também foram observadas **diferenças na classificação de risco** entre algumas avaliações, o que mostra que o uso de LLMs exige **validação e acompanhamento humano**.

📁 Os resultados completos estão documentados na pasta [`resultados/`](./resultados).

---

## ⚠️ Limitações

> [!WARNING]
> Este projeto possui **finalidade exclusivamente educacional**.

- A análise realizada pelo LLM é **preliminar** e não substitui ferramentas especializadas de segurança, verificações técnicas ou a avaliação humana.
- O modelo pode apresentar **inconsistências, interpretações incorretas ou classificações inadequadas**.
- Por isso, as respostas **não devem ser usadas como única fonte** para decisões de segurança.

---

## 🛠️ Tecnologias e ferramentas

| 🧰 Ferramenta | 💡 Uso no projeto |
|:---:|:---:|
| **ChatGPT (LLM)** | Análise das mensagens fictícias |
| **Engenharia de Prompt** | Criação e revisão das versões do prompt |
| **GitHub** | Versionamento e publicação do projeto |
| **Google Sheets** | Registro e comparação das avaliações |
| **Markdown** | Documentação técnica |

---

## 📚 Aprendizados

Durante o desenvolvimento, foram explorados conceitos de:

- 🔐 Segurança da Informação
- 🎣 Phishing e engenharia social
- ✍️ Engenharia de Prompt
- 🤖 Aplicações de LLMs em cibersegurança
- 📏 Avaliação e comparação de respostas de modelos de linguagem
- 📝 Documentação técnica e versionamento de projetos

---

## 🧭 Finalidade

Este projeto foi desenvolvido como parte do meu processo de aprendizado em **Segurança da Informação** e **Inteligência Artificial**, com foco na construção de conhecimentos práticos e na documentação dos estudos.
