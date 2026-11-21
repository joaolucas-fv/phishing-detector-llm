Registros dos Testes: Phishing Detector (Versão 1.0)
1. Apresentação

Este documento reúne os registros dos dez testes realizados com a primeira versão do prompt do projeto Phishing Detector, desenvolvido com o auxílio de um Modelo de Linguagem (LLM).

Os experimentos tiveram como objetivo avaliar a capacidade do ChatGPT de identificar possíveis tentativas de phishing, reconhecer técnicas de engenharia social, analisar riscos e distinguir mensagens suspeitas de comunicações aparentemente legítimas.

Todos os cenários utilizaram a empresa fictícia Meridional, e as mensagens foram elaboradas exclusivamente para fins educacionais.

2. Metodologia

Os testes foram conduzidos com o prompt versão 1.0, e as mensagens fictícias foram submetidas à análise do ChatGPT.

Cada resultado foi avaliado a partir dos seguintes critérios:

Classificação da mensagem.
Nível de risco atribuído.
Identificação dos indicadores de phishing.
Coerência da análise.
Identificação dos possíveis impactos.
Qualidade das recomendações.
Reconhecimento das limitações do modelo.

A avaliação foi qualitativa e feita manualmente. Os resultados registrados correspondem às respostas observadas durante os experimentos, acompanhadas da avaliação técnica realizada no âmbito do projeto.

3. Registros dos testes
Teste 01 — Falsa suspensão de conta

Tipo de ameaça: Phishing por urgência.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem informa ao destinatário que sua conta será bloqueada caso os dados cadastrais não sejam atualizados em até 12 horas. Para isso, apresenta uma suposta situação de segurança e incentiva o usuário a acessar um link de atualização.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Ameaça de suspensão da conta.
Prazo reduzido para a atualização cadastral.
Uso de urgência e de pressão psicológica.
Remetente não verificado.
Presença de link para atualização de dados.

Avaliação técnica:

O LLM identificou corretamente os principais indicadores de phishing, em especial a ameaça de bloqueio e o prazo curto para a atualização cadastral.

A combinação desses elementos pode ser usada para pressionar o destinatário e levá-lo a informar dados pessoais em uma página potencialmente fraudulenta.

A classificação foi considerada coerente com as características da mensagem.

Teste 02 — Falso suporte de TI

Tipo de ameaça: Phishing para roubo de credenciais.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, supostamente enviada pelo departamento de Tecnologia, solicita que os funcionários informem suas senhas corporativas e seus códigos de autenticação para a realização de uma atualização de segurança.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Solicitação de senha corporativa.
Solicitação de código de autenticação.
Uso de urgência.
Possível personificação do departamento de TI.
Presença de link para validação de conta.
Remetente não verificado.

Avaliação técnica:

O LLM identificou corretamente os principais indicadores de phishing e os riscos associados ao roubo de credenciais.

No entanto, descreveu o link como externo, quando ele utilizava o mesmo domínio exibido no endereço do remetente.

Essa imprecisão mostra que o modelo pode interpretar de forma equivocada informações técnicas, o que torna necessária a validação humana das respostas.

Teste 03 — Comunicação de manutenção programada

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Empresa: Meridional (fictícia).

Descrição do cenário:

O comunicado informa aos colaboradores sobre uma manutenção programada nos sistemas internos da empresa, sem solicitar informações pessoais nem exigir qualquer ação por parte dos funcionários.

Resultado esperado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Resultado observado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Indicadores identificados:
Ausência de solicitação de credenciais.
Ausência de pressão psicológica.
Ausência de links ou anexos.
Conteúdo meramente informativo.
Remetente não autenticado.

Avaliação técnica:

O LLM classificou adequadamente a mensagem como uma comunicação sem indícios claros de phishing.

Merece destaque o fato de o modelo ter reconhecido que a aparência profissional de uma mensagem não comprova a legitimidade do remetente.

O resultado indica que o modelo é capaz de evitar a classificação indevida de uma comunicação aparentemente legítima.

Teste 04 — Anexo com macros

Tipo de ameaça: Phishing com possível distribuição de malware.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, supostamente enviada pelo departamento de Recursos Humanos, informa sobre uma atualização da folha salarial e solicita que o funcionário abra um arquivo com extensão .xlsm e habilite a execução de macros.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Anexo com extensão .xlsm.
Solicitação para habilitar macros.
Uso de informações salariais como isca.
Possível personificação do departamento de RH.
Remetente não verificado.

Avaliação técnica:

O LLM identificou corretamente os riscos associados ao anexo e à solicitação para habilitar macros.

O modelo também reconheceu a possibilidade de distribuição de malware, de roubo de informações e de comprometimento dos sistemas corporativos.

Como ponto positivo, não afirmou que o arquivo continha código malicioso, já que essa confirmação dependeria da análise técnica do próprio arquivo.

Teste 05 — Business Email Compromise (BEC)

Tipo de ameaça: Fraude por comprometimento ou personificação de e-mail corporativo.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, supostamente enviada pela diretoria, solicita a alteração dos dados bancários de um fornecedor e exige que o pagamento seja feito com urgência e sigilo.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Solicitação urgente de pagamento.
Alteração dos dados bancários de fornecedor.
Pedido de sigilo sobre a operação.
Possível personificação da diretoria.
Ausência de validação independente.

Avaliação técnica:

O LLM identificou corretamente os indicadores de BEC e de engenharia social.

Reconheceu os riscos de desvio financeiro e recomendou que a solicitação fosse confirmada por um canal independente antes de qualquer pagamento.

O modelo também demonstrou compreender como o uso de autoridade, urgência e confidencialidade pode ser empregado para manipular funcionários.

Teste 06 — Smishing

Tipo de ameaça: Phishing por SMS.

Empresa: Meridional (fictícia, utilizada como referência nos experimentos).

Descrição do cenário:

A mensagem de texto informa sobre uma suposta pendência na entrega de uma encomenda e exige o pagamento de uma taxa para evitar a devolução do pacote.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Remetente não identificado.
Cobrança inesperada.
Urgência para a realização do pagamento.
Ameaça de devolução da encomenda.
Link para suposta regularização.

Avaliação técnica:

O LLM reconheceu corretamente os indicadores de Smishing e identificou o uso de urgência e de pressão psicológica para induzir o destinatário a efetuar um pagamento.

Também apontou os possíveis riscos de fraude financeira, de roubo de dados pessoais e de direcionamento para páginas fraudulentas.

Observação metodológica:

O prompt versão 1.0 foi descrito, inicialmente, como um analisador de mensagens de e-mail. Este cenário ampliou o escopo de forma experimental para incluir mensagens SMS, sem que o prompt original tivesse sido formalmente atualizado.

Teste 07 — Quishing

Tipo de ameaça: Phishing por QR Code.

Empresa: Meridional (fictícia).

Descrição do cenário:

O comunicado informa sobre uma suposta atualização do sistema de autenticação corporativa e solicita que os funcionários escaneiem um QR Code para validar suas contas.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Falsa atualização de autenticação.
Solicitação de validação de contas.
Prazo limite para a realização do procedimento.
Ameaça de suspensão do acesso.
Uso de QR Code para direcionamento a uma página.
Possível personificação do departamento de Tecnologia.

Avaliação técnica:

O LLM identificou corretamente os indicadores de Quishing e reconheceu que códigos QR podem ser usados para direcionar usuários a páginas fraudulentas.

O modelo também apontou os riscos de roubo de credenciais e de comprometimento da autenticação.

Como não foi fornecido um QR Code real, a análise limitou-se ao conteúdo textual do comunicado, e o modelo não verificou nenhum endereço de destino.

Observação metodológica:

Assim como no teste anterior, este cenário ampliou, de forma experimental, o escopo originalmente descrito no prompt versão 1.0.

Teste 08 — Spear Phishing e solicitação de dados dos colaboradores

Tipo de ameaça: Engenharia social e possível phishing direcionado.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, supostamente enviada pela diretoria, solicita uma planilha com nomes completos, CPFs, cargos, salários e dados bancários dos colaboradores.

A comunicação estabelece um prazo para o envio das informações e pede que os canais habituais de validação não sejam utilizados.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Solicitação de dados pessoais.
Solicitação de informações financeiras.
Uso de urgência.
Pedido de confidencialidade.
Possível personificação da diretoria.
Desvio dos procedimentos internos.
Remetente não verificado.

Avaliação técnica:

O LLM identificou corretamente os indicadores de engenharia social e de possível Spear Phishing.

Também reconheceu os riscos de exposição de informações pessoais, de fraude financeira, de roubo de identidade e de uso dos dados em ataques direcionados.

Houve, porém, uma imprecisão conceitual: o modelo classificou CPF, salário e dados bancários como dados pessoais sensíveis. Essas informações podem ser dados pessoais, mas não integram automaticamente as categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

A classificação de risco alto foi considerada coerente com a natureza das informações solicitadas e com a tentativa de contornar os procedimentos internos de segurança.

Teste 09 — Falsa redefinição de senha

Tipo de ameaça: Phishing para roubo de credenciais.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, supostamente enviada pela equipe de Segurança da Informação, informa que a senha corporativa expirará no mesmo dia e direciona o funcionário para um portal de redefinição.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Médio.

Indicadores identificados:
Urgência para a atualização da senha.
Ameaça de bloqueio do acesso.
Link para redefinição de senha.
Possível personificação da equipe de Segurança da Informação.
Remetente não verificado.

Avaliação técnica:

O LLM identificou corretamente os indicadores de phishing e os possíveis riscos de roubo de credenciais.

Houve, contudo, divergência entre o nível de risco esperado e o apresentado. O modelo classificou o risco como médio, por considerar que não havia evidências que confirmassem a natureza maliciosa do link ou a falsificação do remetente.

A diferença mostra que a classificação de risco pode variar conforme a interpretação do modelo e as informações disponíveis.

O risco médio pode ser defensável em uma análise preliminar, mas o cenário ainda representa uma ameaça potencial importante para a segurança das contas corporativas.

Teste 10 — Comunicação corporativa com link informativo

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Empresa: Meridional (fictícia).

Descrição do cenário:

A mensagem, do departamento de Recursos Humanos, informa sobre a disponibilização de um calendário de feriados e de funcionamento interno e apresenta um link para consulta na intranet corporativa.

Resultado esperado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Resultado observado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Indicadores identificados:
Remetente aparentemente institucional, mas não autenticado.
Assunto informativo.
Ausência de pressão psicológica.
Ausência de ameaças.
Ausência de solicitação de credenciais.
Presença de link sem evidências suficientes de maliciosidade.
Orientação para o uso dos canais internos habituais.

Avaliação técnica:

O LLM diferenciou corretamente a presença de um link da existência de uma ameaça.

Reconheceu que a aparência do endereço não comprova sua autenticidade e apresentou recomendações adequadas de verificação.

O resultado indica que o modelo é capaz de evitar um falso positivo diante de uma comunicação aparentemente legítima.

4. Síntese dos resultados

Ao final dos dez experimentos:

Oito mensagens foram classificadas como muito suspeitas.
Duas mensagens foram classificadas como sem indícios claros de phishing.
Sete mensagens suspeitas receberam nível de risco alto.
Uma mensagem suspeita recebeu nível de risco médio.
As duas mensagens sem indícios claros receberam nível de risco baixo.

Durante a avaliação, também foram identificadas três imprecisões relevantes:

Interpretação incorreta de um link como externo no Teste 02.
Classificação conceitual incorreta de dados pessoais como dados pessoais sensíveis no Teste 08.
Divergência entre o nível de risco esperado e o observado no Teste 09.

Esses resultados constituem uma avaliação exploratória e qualitativa, e não uma taxa estatística de precisão do modelo.

5. Considerações finais

A primeira rodada de experimentos mostrou que um Modelo de Linguagem pode auxiliar na análise preliminar de mensagens suspeitas, identificando indicadores de phishing e diferentes técnicas de engenharia social.

O protótipo conseguiu analisar situações envolvendo roubo de credenciais, anexos com macros, fraudes financeiras, mensagens SMS, QR Codes e solicitações indevidas de informações pessoais.

Também foi capaz de reconhecer comunicações aparentemente legítimas sem classificá-las automaticamente como maliciosas.

Por outro lado, os experimentos revelaram limitações na interpretação de informações técnicas, na precisão conceitual e na classificação de riscos.

Essas observações serviram de base para o desenvolvimento da versão 1.1 do prompt, que busca aprimorar a consistência das análises, estabelecer critérios mais claros e explicitar as limitações do modelo.

Importante: todos os cenários são fictícios. Os resultados não representam uma validação estatística da eficácia do modelo, nem comprovam sua capacidade de detectar ataques reais
