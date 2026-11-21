Registros dos Testes: Phishing Detector (Versão 1.1)
1. Apresentação

Este documento reúne os registros dos dez testes realizados com a segunda versão do prompt do projeto Phishing Detector, desenvolvido com o auxílio de um Modelo de Linguagem (LLM).

Os experimentos tiveram como objetivo avaliar as melhorias implementadas no prompt após a identificação de limitações durante a primeira rodada de testes.

Os cenários foram mantidos para permitir a comparação entre as versões 1.0 e 1.1, observando possíveis mudanças na identificação de indicadores de phishing, na classificação de riscos, na precisão conceitual e no reconhecimento das limitações do modelo.

Todos os cenários utilizaram a empresa fictícia Meridional e foram elaborados exclusivamente para fins educacionais.

2. Metodologia

Os testes foram conduzidos com o prompt versão 1.1, e os mesmos cenários da primeira rodada foram submetidos ao ChatGPT.

Cada resposta foi avaliada a partir dos seguintes critérios:

Classificação da mensagem.
Nível de risco atribuído.
Identificação dos indicadores de phishing.
Diferenciação entre evidências e suspeitas.
Coerência da análise apresentada.
Qualidade das recomendações de segurança.
Reconhecimento das limitações técnicas.
Precisão dos conceitos de Segurança da Informação.

A avaliação foi qualitativa e feita manualmente, com a comparação dos resultados obtidos com aqueles registrados na versão 1.0.

3. Registros dos testes
Teste 01 — Falsa suspensão de conta

Tipo de ameaça: Phishing por urgência.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem informa ao destinatário que sua conta será bloqueada caso os dados cadastrais não sejam atualizados em até 12 horas.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Médio.

Indicadores identificados:
Ameaça de suspensão da conta.
Prazo de 12 horas para a atualização cadastral.
Uso de urgência e de pressão psicológica.
Solicitação de atualização de informações.
Remetente não verificado.
Link apresentado sem a identificação de uma página específica.
Justificativa genérica para um suposto problema cadastral.

Avaliação técnica:

O LLM identificou corretamente os principais indicadores de phishing, em especial a ameaça de bloqueio e o prazo curto para a atualização cadastral.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais organizada e distinguiu melhor os indicadores observados das informações que não puderam ser verificadas.

Como ponto positivo, o modelo reconheceu que a aparência institucional do domínio não comprova sua autenticidade.

Houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

A classificação média pode ser justificada pela ausência de solicitação explícita de credenciais e de evidência de comprometimento. Ainda assim, a possibilidade de coleta indevida de dados cadastrais continua representando um risco relevante.

O resultado indica uma análise mais detalhada, mas evidencia a necessidade de critérios mais consistentes para a classificação de risco.

Teste 02 — Falso suporte de TI

Tipo de ameaça: Phishing para roubo de credenciais.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem, supostamente enviada pelo departamento de Tecnologia, solicita que os funcionários informem suas senhas corporativas e seus códigos de autenticação para uma atualização de segurança.

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
Justificativa técnica para a coleta de informações.
Presença de link para validação de contas.
Identidade institucional não verificada.

Avaliação técnica:

O LLM identificou corretamente os principais indicadores de phishing e os riscos relacionados ao roubo de credenciais corporativas.

Em comparação com a versão 1.0, observou-se melhora na interpretação do domínio.

Na primeira versão, o modelo havia descrito o link de forma incorreta, como externo. Na versão 1.1, reconheceu que o remetente e o endereço apresentado utilizavam o mesmo domínio, sem tratar essa característica como prova de autenticidade.

O modelo também apresentou uma explicação mais detalhada sobre os riscos de comprometimento da autenticação multifator (MFA), incluindo a possibilidade de uso indevido de códigos temporários.

Outro aspecto positivo foi a ampliação das recomendações, que passaram a incluir a revogação de sessões potencialmente comprometidas.

O resultado indica avanço na interpretação das informações técnicas e na apresentação das recomendações de segurança.

Teste 03 — Comunicação de manutenção programada

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Versão do prompt: 1.1.

Descrição do cenário:

O comunicado informa aos colaboradores sobre uma manutenção programada nos sistemas internos da Meridional, sem solicitar informações pessoais nem exigir qualquer ação.

Resultado esperado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Resultado observado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Indicadores identificados:
Remetente com identificação institucional, mas não autenticado.
Conteúdo informativo sobre manutenção programada.
Ausência de pressão psicológica.
Ausência de solicitação de credenciais.
Ausência de links e anexos.
Orientação para o uso dos canais internos habituais.

Avaliação técnica:

O LLM classificou corretamente a mensagem como uma comunicação sem indícios claros de phishing.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais organizada e detalhou melhor as limitações técnicas da avaliação.

Merece destaque a identificação de possíveis riscos residuais, como a falsificação do remetente (spoofing), sem que fossem apresentados como evidências de ataque.

O modelo também reconheceu que não realizou verificações de SPF, DKIM e DMARC e que não confirmou a autenticidade da comunicação.

O resultado demonstra capacidade de distinguir uma mensagem aparentemente legítima de uma tentativa evidente de phishing, sem abandonar a cautela necessária.

Teste 04 — Anexo com macros

Tipo de ameaça: Phishing com possível distribuição de malware.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem, supostamente enviada pelo departamento de Recursos Humanos, informa sobre uma atualização da folha salarial e solicita que o funcionário abra um arquivo com extensão .xlsm e habilite macros.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Indicadores identificados:
Anexo com extensão .xlsm.
Solicitação explícita para habilitar macros.
Uso de informações salariais como isca.
Possível personificação do departamento de Recursos Humanos.
Remetente não verificado.
Ausência de evidências sobre a legitimidade do anexo.

Avaliação técnica:

O LLM identificou corretamente os indicadores de risco associados ao anexo e à solicitação para habilitar macros.

Em comparação com a versão 1.0, apresentou uma explicação mais detalhada sobre os riscos da execução de macros e sobre os possíveis impactos para o ambiente corporativo.

Como ponto positivo, o modelo distinguiu a extensão do arquivo da confirmação de conteúdo malicioso e reconheceu que não era possível afirmar que o documento continha malware sem uma análise técnica do arquivo.

Apresentou ainda recomendações mais específicas, como a preservação do e-mail original, a análise do anexo em ambiente controlado e a comunicação à equipe de Segurança da Informação.

O resultado demonstra uma análise coerente, com reconhecimento adequado das limitações técnicas do modelo.

Teste 05 — Business Email Compromise (BEC)

Tipo de ameaça: Fraude financeira por engenharia social e possível personificação corporativa.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem, supostamente enviada pela diretoria, solicita a alteração dos dados bancários de um fornecedor e exige que o pagamento seja feito com urgência e sigilo.

A versão da mensagem efetivamente enviada ao LLM não continha endereço eletrônico de remetente, e a identificação da Diretoria constava apenas na assinatura.

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
Uso da identidade da Diretoria.
Justificativa genérica para a alteração bancária.
Ausência de validação independente.
Ausência de informações sobre os novos dados bancários.

Avaliação técnica:

O LLM identificou corretamente os indicadores de Business Email Compromise (BEC) e de engenharia social.

Reconheceu os riscos de desvio financeiro e recomendou que a solicitação fosse confirmada por canais independentes antes de qualquer pagamento.

Em comparação com a versão 1.0, apresentou recomendações mais detalhadas, entre elas os procedimentos a adotar caso a transferência financeira já tenha sido realizada.

Também reconheceu que não havia informações suficientes para confirmar a identidade de quem enviou a comunicação nem para verificar se houve comprometimento de uma conta corporativa.

O modelo não presumiu a existência de um endereço de e-mail que não constava no cenário efetivamente enviado.

O resultado demonstra uma análise coerente dos indicadores comportamentais de fraude, acompanhada de recomendações preventivas mais completas.

Teste 06 — Smishing

Tipo de ameaça: Smishing / Fraude por falsa cobrança de entrega.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem SMS informa sobre uma suposta pendência na entrega de uma encomenda e exige o pagamento de uma taxa para evitar a devolução do pacote.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Médio.

Indicadores identificados:
Remetente não identificado.
Ausência de identificação da transportadora.
Cobrança inesperada de taxa de liberação.
Urgência para a realização do pagamento.
Ameaça de devolução da encomenda.
Link para a regularização da suposta pendência.
Ausência de código de rastreamento ou de identificação do pedido.

Avaliação técnica:

O LLM identificou corretamente os indicadores de Smishing e reconheceu o uso de urgência, de pressão psicológica e de cobrança inesperada para induzir o destinatário a efetuar um pagamento.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais detalhada sobre a ausência de informações da encomenda, sobre a identificação do remetente e sobre as limitações na verificação do domínio.

O modelo também reconheceu que a presença de HTTPS não comprova a legitimidade do endereço eletrônico.

Houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

Embora essa classificação possa ser defendida pela ausência de informações sobre o impacto financeiro efetivo, o cenário envolve uma possível fraude financeira, situação que também consta entre os critérios de risco alto do prompt.

A divergência evidencia a necessidade de aprimorar a consistência dos critérios de classificação de risco.

Teste 07 — Quishing

Tipo de ameaça: Quishing / Engenharia Social.

Versão do prompt: 1.1.

Descrição do cenário:

Um comunicado fictício da Meridional informa sobre uma atualização de autenticação corporativa e solicita que os funcionários escaneiem um QR Code para validar suas contas.

O cenário também esclarece que o QR Code não será utilizado de fato, sendo apresentado apenas como parte de uma simulação textual.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Médio.

Indicadores identificados:
Suposta atualização do sistema de autenticação.
Solicitação de validação de contas corporativas.
Prazo limite até as 18h.
Ameaça de suspensão temporária do acesso.
Uso de QR Code para direcionamento a uma página.
Uso da identidade institucional do departamento de Tecnologia.
Ausência de identificação técnica do remetente.

Avaliação técnica:

O LLM identificou corretamente os indicadores de Quishing e de engenharia social. Reconheceu que QR Codes podem ser usados para direcionar usuários a páginas fraudulentas e apontou os possíveis riscos de roubo de credenciais e de comprometimento da autenticação multifator.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma explicação mais detalhada sobre as limitações da análise e destacou que não seria possível confirmar a natureza maliciosa do QR Code sem examinar seu conteúdo e seu destino.

O modelo também apresentou recomendações específicas para diferentes situações, inclusive para o caso de um funcionário que já tenha escaneado o código ou informado suas credenciais.

Houve divergência no nível de risco: a versão 1.0 classificou o cenário como alto, enquanto a versão 1.1 atribuiu risco médio.

Essa classificação pode ser defendida diante da ausência de informações sobre o destino do QR Code, embora o potencial de comprometimento de contas corporativas represente um impacto significativo.

O resultado demonstra uma análise mais explícita sobre as limitações técnicas do modelo, mas também reforça a necessidade de critérios consistentes para a classificação de risco.

Teste 08 — Spear Phishing e solicitação de dados dos colaboradores

Tipo de ameaça: Engenharia social / Possível Spear Phishing e CEO Fraud.

Versão do prompt: 1.1.

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
Solicitação de nomes completos e CPFs.
Solicitação de salários e dados bancários.
Uso de autoridade institucional.
Prazo para o envio das informações.
Pedido de confidencialidade.
Tentativa de contornar os procedimentos internos.
Remetente não autenticado.

Avaliação técnica:

O LLM identificou corretamente os indicadores de engenharia social e de possível Spear Phishing. Reconheceu os riscos relacionados à exposição de dados pessoais e financeiros, à fraude e ao comprometimento da confidencialidade das informações corporativas.

Em comparação com a versão 1.0, observou-se uma melhora importante na precisão conceitual relacionada à LGPD.

Na primeira versão, o modelo havia classificado de forma incorreta CPF, salário e dados bancários como dados pessoais sensíveis. Na versão 1.1, diferenciou corretamente essas informações das categorias de dados pessoais sensíveis previstas no artigo 5º, inciso II, da LGPD.

O modelo identificou:
Nome completo e CPF como dados pessoais.
Cargo como dado pessoal, quando associado a uma pessoa identificada.
Salário como informação pessoal de natureza financeira.
Dados bancários como dados pessoais de natureza financeira.

Apresentou ainda uma análise mais detalhada sobre a tentativa de contornar os procedimentos internos e recomendou medidas de validação independente.

O resultado demonstra melhora na precisão conceitual e na identificação dos riscos relacionados à proteção de dados.

Teste 09 — Falsa redefinição de senha

Tipo de ameaça: Phishing para possível roubo de credenciais.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem, supostamente enviada pela equipe de Segurança da Informação, informa que a senha corporativa expirará no mesmo dia e direciona o funcionário para um portal de redefinição.

Resultado esperado:
Classificação: Muito suspeito.
Nível de risco: Alto.

Resultado observado:
Classificação: Muito suspeito.
Nível de risco: Médio.

Indicadores identificados:
Aviso de possível expiração da senha corporativa.
Urgência para a atualização da senha.
Ameaça de bloqueio do acesso.
Link para redefinição de senha.
Possível personificação da equipe de Segurança da Informação.
Remetente não autenticado.

Avaliação técnica:

O LLM identificou corretamente os indicadores de phishing e os possíveis riscos relacionados ao roubo de credenciais corporativas.

Em comparação com a versão 1.0, apresentou uma análise mais detalhada sobre a possibilidade de captura de credenciais e reconheceu que não havia evidências suficientes para confirmar a natureza maliciosa do portal.

Interpretou corretamente, ainda, que o remetente e o link utilizavam o mesmo domínio, sem considerar essa característica como prova de legitimidade.

A divergência identificada na primeira versão permaneceu: ambas as versões classificaram o risco como médio, embora o resultado esperado fosse alto.

Essa ocorrência mostra que a atualização do prompt aprimorou a organização e a precisão da análise, mas não resolveu por completo a inconsistência na classificação de risco.

O resultado foi considerado coerente quanto à identificação da ameaça, e a divergência entre o nível de risco esperado e o observado foi mantida.

Teste 10 — Comunicação corporativa com link informativo

Tipo de mensagem: Comunicação corporativa aparentemente legítima.

Versão do prompt: 1.1.

Descrição do cenário:

A mensagem, do departamento de Recursos Humanos, informa sobre a disponibilização de um calendário de feriados e de funcionamento interno e apresenta um link para consulta na intranet corporativa.

Resultado esperado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Resultado observado:
Classificação: Sem indícios claros.
Nível de risco: Baixo.

Indicadores identificados:
Remetente com identificação institucional, mas não autenticado.
Assunto informativo e coerente com o conteúdo.
Link para consulta de documento na intranet.
Correspondência entre o domínio principal do remetente e o domínio do link.
Ausência de pressão psicológica.
Ausência de solicitação de credenciais ou de informações pessoais.
Orientação para o uso dos canais internos habituais.

Avaliação técnica:

O LLM classificou corretamente a mensagem como uma comunicação sem indícios claros de phishing.

Em comparação com a versão 1.0, a versão 1.1 apresentou uma análise mais detalhada da relação entre o domínio do remetente e o endereço da intranet, reconhecendo que o uso de um subdomínio aparentemente relacionado não comprova sua autenticidade.

O modelo também identificou riscos residuais, como a falsificação do remetente, o comprometimento da página de intranet e possíveis redirecionamentos.

Outro ponto positivo foi o reconhecimento das limitações técnicas, entre elas a impossibilidade de verificar a propriedade do domínio, de inspecionar a página de destino e de analisar os mecanismos SPF, DKIM e DMARC.

O resultado demonstra consistência na identificação de comunicações aparentemente legítimas e maior detalhamento das limitações da análise.

4. Síntese dos resultados

Ao final dos dez experimentos:

Oito mensagens foram classificadas como muito suspeitas.
Duas mensagens foram classificadas como sem indícios claros de phishing.
Quatro mensagens receberam nível de risco alto.
Quatro mensagens receberam nível de risco médio.
Duas mensagens receberam nível de risco baixo.

Também foram observadas mudanças relevantes em relação à versão 1.0:

Melhora na interpretação da relação entre domínios e links.
Maior detalhamento das limitações técnicas.
Melhora na precisão conceitual relacionada à LGPD.
Recomendações de segurança mais completas.
Persistência de divergências na classificação dos níveis de risco em alguns cenários.

Esses resultados constituem uma avaliação exploratória e qualitativa, e não uma taxa estatística de precisão do modelo.

5. Considerações finais

A segunda rodada de experimentos mostrou que as alterações realizadas no prompt contribuíram para melhorar a organização das análises, a precisão conceitual e o reconhecimento das limitações do modelo.

O protótipo conseguiu analisar diferentes modalidades de phishing e de engenharia social, entre elas roubo de credenciais, anexos com macros, fraudes financeiras, Smishing, Quishing e tentativas de obtenção de dados pessoais.

Também foi capaz de reconhecer comunicações aparentemente legítimas sem classificá-las automaticamente como maliciosas.

Um dos resultados mais relevantes foi a correção da imprecisão conceitual relacionada à LGPD, identificada na primeira versão.

No entanto, algumas divergências na classificação de risco permaneceram, o que mostra que o aprimoramento das instruções não elimina todas as limitações dos modelos de linguagem.

Os experimentos reforçam que LLMs podem atuar como ferramentas de apoio à análise preliminar de ameaças, mas não substituem ferramentas especializadas, verificações técnicas nem a avaliação humana.

Importante: os dez cenários são fictícios e constituem uma avaliação exploratória. Os resultados não representam uma validação estatística da eficácia do modelo, nem comprovam sua capacidade de detectar ataques reais.
