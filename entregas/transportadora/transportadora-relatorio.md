# Transportadora — análise AS-IS

## 1. Identificação e escopo

**Padrão:** Raias 1.0. **Modo:** AS-IS. **Data da análise:** 19/10/2026. **Situação:** modelo documental para validação, com manutenção parcial e lacunas explícitas; não é aprovação operacional.

**Fonte F001:** `Mapeamento_AS_IS_Transportadora_5W2H.pdf`, versão 1.0 de 19/10/2026, 11 páginas, todas extraídas como texto pesquisável, sem OCR. As citações curtas foram conferidas no texto extraído por coluna das tabelas; a página 6 foi também inspecionada visualmente. Localizadores são página e linha P01–P20, seção ou ação A01–A07. POPs, entrevistas e transcrições são citados pelo PDF, mas não foram fornecidos nem verificados independentemente. Nenhuma fonte externa foi usada para completar o processo.

**Objetivo:** documentar captação, avaliação, contratação, programação, coleta, transporte, descarga, acerto e financeiro do cliente, incluindo os recortes de jornada e manutenção. **Unidade:** uma operação/viagem, com faturamento por período conforme condição comercial. O pagamento ao prestador fica fora do trecho comprovado: P16 confirma somente a solicitação; adiantamento e saldo seguem pendentes.

**Gatilhos e fronteiras:** (1) oportunidade/programação → solicitação de pagamento do acerto ou encerramento sem fechamento/por impedimento; (2) CT-e/ciclo comercial → recebimento e baixa; (3) rotina diária/fechamento mensal → disponibilização de registros/tarefa DP; (4) problema do veículo → comunicação com fotos e pendência de manutenção. O documento descreve um macrofluxo ponta a ponta, mas não comprova que o faturamento tenha de aguardar o acerto. Por isso, o mesmo diagrama contém quatro componentes com inícios próprios e referências cruzadas: CT-e de P11 é insumo de P17. Eles não são representados como paralelismo sincronizado.

**Regras preservadas:** resultado ≥40% para fechar frete; Angel Lira para terceiros; retorno só em pendência; programação frota própria com Faturista e terceiro com Assistente; OC e CT-e/MDF-e de combustível com Faturista, demais conforme PDF; acompanhamento por modalidade; baixa manual no A2O. Janela de descarga é regra operacional e cobrança do cliente é processo validado, não novos gargalos. Divergências com POP não substituem as responsabilidades atuais.

**Limites:** P13 não detalha a execução física da descarga; P20 confirma apenas acionamento por problema/fotos. Ações A01–A07 (p.7–8) são propostas; não viraram etapas AS-IS, SLAs vigentes ou custos aprovados. Não foi criado TO-BE. Decisões de modalidade visualizam roteamento de responsabilidades já descritas, sem criar aprovação ou alçada. O desenho é largo por manter a escala fixa da skill; usar zoom/pan no editor, sem compactar a fonte.

## 2. Fluxo por raias

IDs, ordem e conexões abaixo constituem o inventário canônico legível. Nomes completos de papéis e detalhes de cada atividade constam no 5W2H. `pendencia` indica interrupção do conhecimento, não conclusão normal.

1. `inicio-demanda` — **Supervisor Comercial** — inicio: Oportunidade ou programação de carga. Próximos: atividade-captar-cargas.

2. `atividade-captar-cargas` — **Supervisor Comercial** — atividade: Receber e captar cargas. Próximos: decisao-operacao-tanque.

3. `decisao-operacao-tanque` — **Supervisor Comercial** — decisao: Operação de tanque?. Próximos: Não → atividade-avaliar-viabilidade-geral; Sim → atividade-avaliar-viabilidade-tanque.

4. `atividade-avaliar-viabilidade-geral` — **Supervisor Comercial** — atividade: Avaliar viabilidade e negociar — geral. Próximos: decisao-margem-minima.

5. `atividade-avaliar-viabilidade-tanque` — **Faturista e Gerente (tanque)** — atividade: Avaliar viabilidade e negociar — tanque. Próximos: decisao-margem-minima.

6. `decisao-margem-minima` — **Supervisor Comercial** — decisao: Resultado igual ou superior a 40%?. Próximos: Não: abaixo de 40% → fim-frete-nao-fechado; Sim: ≥40% → atividade-definir-frota.

7. `fim-frete-nao-fechado` — **Supervisor Comercial** — fim: Frete não fechado. Próximos: fim deste recorte.

8. `atividade-definir-frota` — **Supervisor Comercial** — atividade: Definir frota própria ou terceiro. Próximos: decisao-terceirizar.

9. `decisao-terceirizar` — **Supervisor Comercial** — decisao: Operação será terceirizada?. Próximos: Sim → atividade-buscar-terceiro; Não: frota própria definida → atividade-repassar-operacao.

10. `atividade-buscar-terceiro` — **Supervisor Comercial** — atividade: Buscar e negociar terceiro. Próximos: Carga e veículo definidos → atividade-repassar-operacao.

11. `atividade-repassar-operacao` — **Supervisor Comercial** — atividade: Repassar operação definida. Próximos: decisao-programar-terceiro.

12. `decisao-programar-terceiro` — **Assistente Comercial** — decisao: Operação de terceiro?. Próximos: Sim → atividade-consultar-risco; Não → atividade-programar-frota.

13. `atividade-consultar-risco` — **Assistente Comercial** — atividade: Solicitar documentos e consultar risco. Próximos: decisao-impedimento-risco.

14. `decisao-impedimento-risco` — **Assistente Comercial** — decisao: Existe impedimento de risco?. Próximos: Sim → fim-operacao-impedida; Não / aprovação → atividade-cadastrar-a2o.

15. `fim-operacao-impedida` — **Assistente Comercial** — fim: Operação não prossegue. Próximos: fim deste recorte.

16. `atividade-cadastrar-a2o` — **Assistente Comercial** — atividade: Cadastrar no A2O. Próximos: atividade-programar-terceiro.

17. `atividade-programar-terceiro` — **Assistente Comercial** — atividade: Programar viagem — terceiro. Próximos: decisao-ordem-combustivel.

18. `atividade-programar-frota` — **Faturista** — atividade: Programar viagem — frota própria. Próximos: decisao-ordem-combustivel.

19. `decisao-ordem-combustivel` — **Assistente Comercial** — decisao: Operação de combustível?. Próximos: Não → atividade-enviar-ordem-geral; Sim → atividade-enviar-ordem-combustivel.

20. `atividade-enviar-ordem-geral` — **Assistente Comercial** — atividade: Emitir/enviar OC — geral. Próximos: atividade-carregar.

21. `atividade-enviar-ordem-combustivel` — **Faturista** — atividade: Emitir/enviar OC — combustível. Próximos: atividade-carregar.

22. `atividade-carregar` — **Motorista e Embarcador** — atividade: Realizar carregamento. Próximos: decisao-documentos-combustivel.

23. `decisao-documentos-combustivel` — **Assistente Comercial** — decisao: Emissão para combustível?. Próximos: Sim → atividade-emitir-documentos-combustivel; Não: terceiros e demais frota → atividade-emitir-documentos-demais.

24. `atividade-emitir-documentos-combustivel` — **Faturista** — atividade: Emitir CT-e/MDF-e — combustível. Próximos: decisao-acompanhamento-modalidade.

25. `atividade-emitir-documentos-demais` — **Assistente Comercial** — atividade: Emitir CT-e/MDF-e — demais. Próximos: decisao-acompanhamento-modalidade.

26. `decisao-acompanhamento-modalidade` — **Assistente Comercial** — decisao: Modalidade de acompanhamento?. Próximos: Terceiros / Sider → atividade-acompanhar-terceiros-sider; Tanque / combustível → atividade-acompanhar-tanque; Outra modalidade, se existir [GAP] → pendencia-modalidade-acompanhamento.

27. `atividade-acompanhar-terceiros-sider` — **Assistente Comercial** — atividade: Acompanhar viagem — terceiros/Sider. Próximos: Antes da chegada → decisao-janela-exigida.

28. `atividade-acompanhar-tanque` — **Faturista** — atividade: Acompanhar viagem — tanque/combustível. Próximos: Antes da chegada → decisao-janela-exigida.

29. `pendencia-modalidade-acompanhamento` — **Responsável pela operação** — pendencia: Cobertura das demais modalidades a validar. Próximos: pendência de validação.

30. `decisao-janela-exigida` — **Responsável pela operação** — decisao: Destino exige janela de descarga?. Próximos: Sim → atividade-agendar-janela; Não: após descarga → atividade-confirmar-descarga.

31. `atividade-agendar-janela` — **Responsável pela operação** — atividade: Solicitar e confirmar janela de descarga. Próximos: Após descarga; reagendar se necessário → atividade-confirmar-descarga.

32. `atividade-confirmar-descarga` — **Responsável pela operação** — atividade: Confirmar descarga por WhatsApp. Próximos: No retorno do motorista → atividade-entregar-documentos-retorno.

33. `atividade-entregar-documentos-retorno` — **Motorista** — atividade: Entregar documentos de retorno. Próximos: atividade-conferir-documentos.

34. `atividade-conferir-documentos` — **Faturista** — atividade: Conferir e organizar documentação. Próximos: atividade-lancar-cargas.

35. `atividade-lancar-cargas` — **Assistente Comercial** — atividade: Lançar cargas no A2O. Próximos: atividade-validar-acerto.

36. `atividade-validar-acerto` — **Analista Administrativa** — atividade: Conferir documentos e validar acerto. Próximos: atividade-pedir-pagamento.

37. `atividade-pedir-pagamento` — **Analista Administrativa** — atividade: Solicitar pagamento no Bitrix. Próximos: fim-solicitacao-registrada.

38. `fim-solicitacao-registrada` — **Analista Administrativa** — fim: Solicitação de pagamento registrada. Próximos: fim deste recorte.

39. `inicio-ciclo-faturamento` — **Faturamento** — inicio: CT-e e ciclo comercial de faturamento. Próximos: atividade-faturar-cliente.

40. `atividade-faturar-cliente` — **Faturamento** — atividade: Faturar o cliente. Próximos: No vencimento / conforme condição → atividade-verificar-pagamento.

41. `atividade-verificar-pagamento` — **Faturamento** — atividade: Identificar pagamento no banco. Próximos: decisao-pagamento-identificado.

42. `decisao-pagamento-identificado` — **Faturamento** — decisao: Pagamento identificado?. Próximos: Sim → atividade-baixar-titulo; Não: título vencido → atividade-cobrar-atraso.

43. `atividade-baixar-titulo` — **Faturamento** — atividade: Realizar baixa manual no A2O. Próximos: fim-financeiro-cliente-encerrado.

44. `fim-financeiro-cliente-encerrado` — **Faturamento** — fim: Recebimento e baixa concluídos. Próximos: fim deste recorte.

45. `atividade-cobrar-atraso` — **Crédito e Cobrança** — atividade: Cobrar título vencido. Próximos: Até regularização → atividade-verificar-pagamento.

46. `inicio-rotina-jornada` — **Analista de Logística/Jornada** — inicio: Rotina diária / fechamento mensal. Próximos: atividade-controlar-jornada.

47. `atividade-controlar-jornada` — **Analista de Logística/Jornada** — atividade: Controlar jornada e dar suporte à frota própria. Próximos: No fechamento mensal → fim-ciclo-jornada-documentado.

48. `fim-ciclo-jornada-documentado` — **Analista de Logística/Jornada** — fim: Registros e tarefa para DP disponibilizados. Próximos: fim deste recorte.

49. `inicio-problema-manutencao` — **Motorista** — inicio: Problema relatado pelo motorista. Próximos: atividade-comunicar-problema.

50. `atividade-comunicar-problema` — **Motorista** — atividade: Comunicar problema e enviar fotos. Próximos: pendencia-detalhar-manutencao.

51. `pendencia-detalhar-manutencao` — **Manutenção** — pendencia: Fluxo de manutenção ainda não validado. Próximos: pendência de validação.

**Relações temporais:** P12 acompanha da saída até a descarga e abrange o intervalo de P13. As setas de P12 para P13 são passagem de contexto, não declaração de que a viagem terminou antes de agendar. P19 é rotina de apoio e P20 é evento independente; não se supõe uma execução por viagem. A consulta de risco só foi aplicada a terceiros. Não há bloco paralelo, pois a fonte não especifica divisão/junção sincronizadas.

## 3. Matriz 5W2H

P08, P09, P11 e P12 foram desdobrados por modalidade; P14/P15 mostram a entrega do motorista e a conferência do Faturista; P16 e P18 foram desdobrados por executor e resultado. P20 não reproduz o procedimento ainda em validação. A raia “Faturista e Gerente (tanque)” mantém a responsabilidade conjunta declarada em P02.

| ID | O quê | Quem | Por quê | Onde | Quando | Como | Quanto | Estado | Evidência | GAPs |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| atividade-captar-cargas | Receber e captar cargas | Supervisor Comercial | Gerar demanda e manter veículos em operação | WhatsApp, contatos, visitas e grupos | Conforme oportunidades e programações recorrentes | Rede de contatos e visitas; couro: cliente define volume; piso: Diretoria envia carga de retorno; combustível dos postos: Compras envia programação no grupo; recorte: Recepção/captação pelo Supervisor; origens: cliente, Diretoria e Compras, conforme P01. | Não mensurado; valor depende do frete; valor não informado [gap-atividade-captar-cargas-custo] | extraido | F001 p.3, P01 | gap-atividade-captar-cargas-controle; gap-atividade-captar-cargas-custo |
| atividade-avaliar-viabilidade-geral | Avaliar viabilidade e negociar — geral | Supervisor Comercial | Evitar operações sem retorno financeiro | Ferramentas de rota, referências ANTT e controles de cálculo | Antes da confirmação do frete | Calcular distância, pedágio, combustível e despesas; negociar; fechar somente com resultado ≥40% | Margem mínima: 40%; custos variáveis | extraido | F001 p.3, P02 | Nenhum vinculado diretamente |
| atividade-avaliar-viabilidade-tanque | Avaliar viabilidade e negociar — tanque | Faturista e Gerente (tanque) | Evitar operações sem retorno financeiro | Ferramentas de rota, referências ANTT e controles de cálculo | Antes da confirmação do frete | Calcular distância, pedágio, combustível e despesas; negociar; fechar somente com resultado ≥40%; recorte: Responsabilidade conjunta Faturista + Gerente, conforme P02. Não separar uma decisão conjunta artificialmente. | Margem mínima: 40%; custos variáveis | extraido | F001 p.3, P02 | Nenhum vinculado diretamente |
| atividade-definir-frota | Definir frota própria ou terceiro | Supervisor Comercial | Alocar recurso adequado à carga | Planilha da frota e canais comerciais | Após oportunidade e antes do repasse operacional | Consultar disponibilidade; buscar terceiro se frota não atender ou se a estratégia exigir | Não mensurado; valor não informado [gap-atividade-definir-frota-custo] | extraido | F001 p.3, P03 | gap-atividade-definir-frota-custo |
| atividade-buscar-terceiro | Buscar e negociar terceiro | Supervisor Comercial | Atender demandas sem veículo próprio disponível | Fretebras, rede de contatos e visitas | Quando a operação será terceirizada | Localizar prestador, negociar carga/veículo e concluir definições antes do repasse | Frete variável; plano Fretebras sujeito a limite | extraido | F001 p.3, P04 | gap-atividade-buscar-terceiro-controle |
| atividade-repassar-operacao | Repassar operação definida | Supervisor Comercial | Iniciar documentação/programação sem transferir busca incompleta | Grupo de WhatsApp | Somente após carga e veículo definidos | Encaminhar contato e informações da carga ou veículo | Sem custo direto mensurado; valor não informado [gap-atividade-repassar-operacao-custo] | extraido | F001 p.3, P05 | gap-atividade-repassar-operacao-controle; gap-atividade-repassar-operacao-metodo; gap-atividade-repassar-operacao-custo |
| atividade-consultar-risco | Solicitar documentos e consultar risco | Assistente Comercial | Atender requisitos cadastrais e de segurança | WhatsApp e Angel Lira | Antes do cadastro e programação do terceiro | Receber/solicitar documentos; consultar; tratar pendência com Angel Lira; com impedimento não prosseguir | Taxa não validada no levantamento; valor não informado [gap-atividade-consultar-risco-custo] | extraido | F001 p.4, P06 | gap-atividade-consultar-risco-criterio; gap-atividade-consultar-risco-custo |
| atividade-cadastrar-a2o | Cadastrar no A2O | Assistente Comercial | Habilitar motorista, empresa e veículo | A2O | Após aprovação na gerenciadora de risco | Cadastrar pessoa/empresa e conjunto veicular conforme necessidade | Esforço interno; custo não mensurado; valor não informado [gap-atividade-cadastrar-a2o-custo] | extraido | F001 p.4, P07 | gap-atividade-cadastrar-a2o-custo |
| atividade-programar-terceiro | Programar viagem — terceiro | Assistente Comercial | Organizar veículo, motorista, carga, data e status | Planilhas separadas e A2O | Após definição/cadastro e antes da Ordem de Carregamento | Registrar viagem, atualizar status e manter controle por modalidade | Esforço interno; risco de duplicidade de controles; valor não informado [gap-atividade-programar-terceiro-custo] | extraido | F001 p.4, P08 | gap-atividade-programar-terceiro-controle; gap-atividade-programar-terceiro-custo |
| atividade-programar-frota | Programar viagem — frota própria | Faturista | Organizar veículo, motorista, carga, data e status | Planilhas separadas e A2O | Após definição/cadastro e antes da Ordem de Carregamento | Registrar viagem, atualizar status e manter controle por modalidade | Esforço interno; risco de duplicidade de controles; valor não informado [gap-atividade-programar-frota-custo] | extraido | F001 p.4, P08 | gap-atividade-programar-frota-custo |
| atividade-enviar-ordem-geral | Emitir/enviar OC — geral | Assistente Comercial | Autorizar e orientar carregamento | WhatsApp e grupo operacional | Depois da programação e antes do carregamento | Conferir ordem, enviar ao motorista e compartilhar no grupo | Sem custo direto mensurado; valor não informado [gap-atividade-enviar-ordem-geral-custo] | extraido | F001 p.4, P09 | gap-atividade-enviar-ordem-geral-custo |
| atividade-enviar-ordem-combustivel | Emitir/enviar OC — combustível | Faturista | Autorizar e orientar carregamento | WhatsApp e grupo operacional | Depois da programação e antes do carregamento | Conferir ordem, enviar ao motorista e compartilhar no grupo | Sem custo direto mensurado; valor não informado [gap-atividade-enviar-ordem-combustivel-custo] | extraido | F001 p.4, P09 | gap-atividade-enviar-ordem-combustivel-custo |
| atividade-carregar | Realizar carregamento | Motorista e Embarcador | Executar coleta da carga | Local de carregamento | Data/horário programados | Apresentar-se, cumprir checklist/procedimentos locais, carregar e receber NF | Custo incorporado à operação | extraido | F001 p.4, P10 | Nenhum vinculado diretamente |
| atividade-emitir-documentos-combustivel | Emitir CT-e/MDF-e — combustível | Faturista | Cumprir requisitos fiscais e documentais | A2O e WhatsApp | Após carregamento e recebimento da NF | Obter/importar XML, emitir documentos e encaminhar ao motorista | Tributos/taxas por operação; não mensurados; valor não informado [gap-atividade-emitir-documentos-combustivel-custo] | extraido | F001 p.5, P11 | gap-atividade-emitir-documentos-combustivel-custo |
| atividade-emitir-documentos-demais | Emitir CT-e/MDF-e — demais | Assistente Comercial | Cumprir requisitos fiscais e documentais | A2O e WhatsApp | Após carregamento e recebimento da NF | Obter/importar XML, emitir documentos e encaminhar ao motorista | Tributos/taxas por operação; não mensurados; valor não informado [gap-atividade-emitir-documentos-demais-custo] | extraido | F001 p.5, P11 | gap-atividade-emitir-documentos-demais-custo |
| atividade-acompanhar-terceiros-sider | Acompanhar viagem — terceiros/Sider | Assistente Comercial | Dar suporte, monitorar status e antecipar ocorrências | WhatsApp, rastreadores e controles | Da saída até a descarga | Acompanhar posição/status e contatar motorista quando necessário | Esforço interno; valor não informado [gap-atividade-acompanhar-terceiros-sider-custo] | extraido | F001 p.5, P12 | gap-atividade-acompanhar-terceiros-sider-custo |
| atividade-acompanhar-tanque | Acompanhar viagem — tanque/combustível | Faturista | Dar suporte, monitorar status e antecipar ocorrências | WhatsApp, rastreadores e controles | Da saída até a descarga | Acompanhar posição/status e contatar motorista quando necessário | Esforço interno; valor não informado [gap-atividade-acompanhar-tanque-custo] | extraido | F001 p.5, P12 | gap-atividade-acompanhar-tanque-custo |
| atividade-agendar-janela | Solicitar e confirmar janela de descarga | Responsável pela operação | Concluir entrega conforme exigência do destino | E-mail, WhatsApp ou canal do cliente; confirmação por WhatsApp | Antes da chegada e no término da descarga | Solicitar/confirmar janela se exigida; reagendar quando perdida; confirmar descarga por WhatsApp; recorte: Somente se o destino exigir. A perda é rara e permite reagendamento sem dificuldade. | Sem custo específico mensurado; valor não informado [gap-atividade-agendar-janela-custo] | extraido | F001 p.5, P13 | gap-atividade-agendar-janela-responsavel; gap-atividade-agendar-janela-custo |
| atividade-confirmar-descarga | Confirmar descarga por WhatsApp | Responsável pela operação | Concluir entrega conforme exigência do destino | E-mail, WhatsApp ou canal do cliente; confirmação por WhatsApp | Antes da chegada e no término da descarga | Solicitar/confirmar janela se exigida; reagendar quando perdida; confirmar descarga por WhatsApp; recorte: Confirmação após a descarga; não há execução física detalhada da descarga no PDF. | Sem custo específico mensurado; valor não informado [gap-atividade-confirmar-descarga-custo] | extraido | F001 p.5, P13 | gap-atividade-confirmar-descarga-custo |
| atividade-entregar-documentos-retorno | Entregar documentos de retorno | Motorista | Comprovar viagem e iniciar acerto | Documentação física/digital | No retorno do motorista | Entregar CT-e, NF assinada/carimbada, comprovantes de abastecimento, despesas e demais documentos; recorte: Entrega pelo motorista ao Faturista; recepção integra a conferência seguinte. | Sem custo direto mensurado; valor não informado [gap-atividade-entregar-documentos-retorno-custo] | extraido | F001 p.5, P14 | gap-atividade-entregar-documentos-retorno-custo |
| atividade-conferir-documentos | Conferir e organizar documentação | Faturista | Garantir integridade antes da validação final | Documentos e A2O | Logo após retorno | Conferir emissão de CT-e; imprimir, reunir documentos e entregar para conferência final; recorte: Inclui recebimento de P14 e entrega do conjunto à Analista Administrativa. | Esforço interno; valor não informado [gap-atividade-conferir-documentos-custo] | extraido | F001 p.5, P15 | gap-atividade-conferir-documentos-custo |
| atividade-lancar-cargas | Lançar cargas no A2O | Assistente Comercial | Fechar despesas da viagem e formalizar pagamento | A2O e Bitrix | Após entrega da documentação | Assistente lança cargas; Analista confere documentos, valida e abre solicitação de pagamento no Bitrix; recorte: Somente lançamento; validação e pedido de pagamento ficam com a Analista. | Valor conforme acerto da viagem | extraido | F001 p.5, P16 | Nenhum vinculado diretamente |
| atividade-validar-acerto | Conferir documentos e validar acerto | Analista Administrativa | Fechar despesas da viagem e formalizar pagamento | A2O e Bitrix | Após entrega da documentação | Assistente lança cargas; Analista confere documentos, valida e abre solicitação de pagamento no Bitrix; recorte: Após disponibilização dos lançamentos; ordem interna representada conforme redação P16, sujeita à validação operacional. | Valor conforme acerto da viagem | extraido | F001 p.5, P16 | gap-atividade-validar-acerto-sequencia; gap-atividade-validar-acerto-prazo |
| atividade-pedir-pagamento | Solicitar pagamento no Bitrix | Analista Administrativa | Fechar despesas da viagem e formalizar pagamento | A2O e Bitrix | Após entrega da documentação | Assistente lança cargas; Analista confere documentos, valida e abre solicitação de pagamento no Bitrix; recorte: Solicitação registrada não equivale a pagamento executado. | Valor conforme acerto da viagem | extraido | F001 p.5, P16 | gap-atividade-pedir-pagamento-metodo |
| atividade-faturar-cliente | Faturar o cliente | Faturamento | Transformar transporte em valor a receber | A2O, banco e e-mail | Semanal, quinzenal ou conforme condição comercial | CT-e gera título; agrupar CT-es em fatura, definir vencimento e enviar fatura com boleto ou instrução PIX | Valor total dos CT-es faturados | extraido | F001 p.6, P17 | Nenhum vinculado diretamente |
| atividade-verificar-pagamento | Identificar pagamento no banco | Faturamento | Realizar receita e encerrar financeiro | Banco, A2O e canais de cobrança | No vencimento e após ele, se necessário | Identificar crédito bancário; baixa manual no A2O; sem pagamento, cobrar até regularização; recorte: Verificação no vencimento e após, se necessário. | Saldo do título em aberto | extraido | F001 p.6, P18 | Nenhum vinculado diretamente |
| atividade-baixar-titulo | Realizar baixa manual no A2O | Faturamento | Realizar receita e encerrar financeiro | Banco, A2O e canais de cobrança | No vencimento e após ele, se necessário | Identificar crédito bancário; baixa manual no A2O; sem pagamento, cobrar até regularização; recorte: Após identificação do crédito bancário. | Saldo do título em aberto | extraido | F001 p.6, P18 | Nenhum vinculado diretamente |
| atividade-cobrar-atraso | Cobrar título vencido | Crédito e Cobrança | Realizar receita e encerrar financeiro | Banco, A2O e canais de cobrança | No vencimento e após ele, se necessário | Identificar crédito bancário; baixa manual no A2O; sem pagamento, cobrar até regularização; recorte: Cobrar até regularização; não inventar cadência, limite de tentativas ou regra jurídica. | Saldo do título em aberto | extraido | F001 p.6, P18 | Nenhum vinculado diretamente |
| atividade-controlar-jornada | Controlar jornada e dar suporte à frota própria | Analista de Logística/Jornada | Apoiar motoristas, cumprir jornada e alimentar folha | Omnilink/Sigra, Drive, WhatsApp e Bitrix | Diariamente e no fechamento mensal | Monitorar posição, coletar informações e complementar registros; controlar folgas/CNH/licenças; baixar planilha Drive e abrir tarefa no Bitrix para DP | Esforço interno; retrabalho não mensurado; valor não informado [gap-atividade-controlar-jornada-custo] | extraido | F001 p.6, P19 | gap-atividade-controlar-jornada-controle; gap-atividade-controlar-jornada-custo |
| atividade-comunicar-problema | Comunicar problema e enviar fotos | Motorista | Manter veículo seguro e disponível | WhatsApp confirmado; Bitrix e sistemas em validação | Confirmado: motorista informa problema; rotinas preventivas ainda não validadas (p.2 e p.11) | Motorista comunica problema e envia fotos. Procedimento posterior não informado [gap-pendencia-detalhar-manutencao-metodo]. | Variável; não mensurado; valor não informado [gap-atividade-comunicar-problema-custo] | extraido | F001 p.6, P20 | gap-atividade-comunicar-problema-custo |


**Quanto:** margens, valor do frete e saldo a receber são parâmetros operacionais; não são custo de execução da atividade. Onde o PDF informa “não mensurado” ou apenas esforço interno, a ausência foi mantida. Não se atribuíram valores zero. Frequências, custos de implantação das melhorias e duração/SLA não foram estimados. Ausências de metas e custo de melhorias estão consolidadas nas pendências documentais a seguir, sem multiplicá-las por toda tarefa.

## 4. Evidências e inferências

| ID do elemento | Estado | Fonte/localização | Trecho literal | Justificativa | Confiança |
| --- | --- | --- | --- | --- | --- |
| inicio-demanda | extraido | F001, p.3, P01 | Gerar demanda e manter os veículos em operação | Elemento extraído; ver documentação da atividade. | — |
| atividade-captar-cargas | extraido | F001, p.3, P01 | Gerar demanda e manter os veículos em operação | Elemento extraído; ver documentação da atividade. | — |
| decisao-operacao-tanque | extraido | F001, p.3, P02 | Margem mínima: 40%; | Elemento extraído; ver documentação da atividade. | — |
| atividade-avaliar-viabilidade-geral | extraido | F001, p.3, P02 | Margem mínima: 40%; | Elemento extraído; ver documentação da atividade. | — |
| atividade-avaliar-viabilidade-tanque | extraido | F001, p.3, P02 | Margem mínima: 40%; | Elemento extraído; ver documentação da atividade. | — |
| decisao-margem-minima | inferido | F001, p.3, P02 | Margem mínima: 40%; | Convergência visual do critério comum; alçada final no tanque não individualizada. | media |
| fim-frete-nao-fechado | extraido | F001, p.3, P02 | Margem mínima: 40%; | Elemento extraído; ver documentação da atividade. | — |
| atividade-definir-frota | extraido | F001, p.3, P03 | Consulta disponibilidade da frota própria. | Elemento extraído; ver documentação da atividade. | — |
| decisao-terceirizar | extraido | F001, p.3, P03 | Consulta disponibilidade da frota própria. | Elemento extraído; ver documentação da atividade. | — |
| atividade-buscar-terceiro | extraido | F001, p.3, P04 | Frete variável; plano Fretebras sujeito a limite | Elemento extraído; ver documentação da atividade. | — |
| atividade-repassar-operacao | extraido | F001, p.3, P05 | Somente após carga e veículo estarem definidos | Elemento extraído; ver documentação da atividade. | — |
| decisao-programar-terceiro | extraido | F001, p.4, P06 | se houver impedimento, o processo não prossegue. | Elemento extraído; ver documentação da atividade. | — |
| atividade-consultar-risco | extraido | F001, p.4, P06 | se houver impedimento, o processo não prossegue. | Elemento extraído; ver documentação da atividade. | — |
| decisao-impedimento-risco | extraido | F001, p.4, P06 | se houver impedimento, o processo não prossegue. | Elemento extraído; ver documentação da atividade. | — |
| fim-operacao-impedida | extraido | F001, p.4, P06 | se houver impedimento, o processo não prossegue. | Elemento extraído; ver documentação da atividade. | — |
| atividade-cadastrar-a2o | extraido | F001, p.4, P07 | Após aprovação na gerenciadora de risco | Elemento extraído; ver documentação da atividade. | — |
| atividade-programar-terceiro | extraido | F001, p.4, P08 | Terceiros: Assistente Comercial. Frota própria: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-programar-frota | extraido | F001, p.4, P08 | Terceiros: Assistente Comercial. Frota própria: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| decisao-ordem-combustivel | extraido | F001, p.4, P09 | Geral: Assistente Comercial. Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-enviar-ordem-geral | extraido | F001, p.4, P09 | Geral: Assistente Comercial. Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-enviar-ordem-combustivel | extraido | F001, p.4, P09 | Geral: Assistente Comercial. Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-carregar | extraido | F001, p.4, P10 | Motorista e embarcador | Elemento extraído; ver documentação da atividade. | — |
| decisao-documentos-combustivel | extraido | F001, p.5, P11 | Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-emitir-documentos-combustivel | extraido | F001, p.5, P11 | Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| atividade-emitir-documentos-demais | extraido | F001, p.5, P11 | Combustível: Faturista. | Elemento extraído; ver documentação da atividade. | — |
| decisao-acompanhamento-modalidade | extraido | F001, p.5, P12 | Da saída até a descarga | Elemento extraído; ver documentação da atividade. | — |
| atividade-acompanhar-terceiros-sider | extraido | F001, p.5, P12 | Da saída até a descarga | Elemento extraído; ver documentação da atividade. | — |
| atividade-acompanhar-tanque | extraido | F001, p.5, P12 | Da saída até a descarga | Elemento extraído; ver documentação da atividade. | — |
| decisao-janela-exigida | extraido | F001, p.5, P13 | A perda é rara; quando ocorre, reagenda. | Elemento extraído; ver documentação da atividade. | — |
| atividade-agendar-janela | extraido | F001, p.5, P13 | A perda é rara; quando ocorre, reagenda. | Elemento extraído; ver documentação da atividade. | — |
| atividade-confirmar-descarga | extraido | F001, p.5, P13 | A perda é rara; quando ocorre, reagenda. | Elemento extraído; ver documentação da atividade. | — |
| atividade-entregar-documentos-retorno | extraido | F001, p.5, P14 | No retorno do motorista | Elemento extraído; ver documentação da atividade. | — |
| atividade-conferir-documentos | extraido | F001, p.5, P15 | Faturista -> Analista Administrativa | Elemento extraído; ver documentação da atividade. | — |
| atividade-lancar-cargas | extraido | F001, p.5, P16 | Assistente lança cargas; | Elemento extraído; ver documentação da atividade. | — |
| atividade-validar-acerto | extraido | F001, p.5, P16 | Assistente lança cargas; | Elemento extraído; ver documentação da atividade. | — |
| atividade-pedir-pagamento | extraido | F001, p.5, P16 | Assistente lança cargas; | Elemento extraído; ver documentação da atividade. | — |
| fim-solicitacao-registrada | extraido | F001, p.5, P16 | Assistente lança cargas; | Elemento extraído; ver documentação da atividade. | — |
| inicio-ciclo-faturamento | extraido | F001, p.6, P17 | CT-e gera título; | Elemento extraído; ver documentação da atividade. | — |
| atividade-faturar-cliente | extraido | F001, p.6, P17 | CT-e gera título; | Elemento extraído; ver documentação da atividade. | — |
| atividade-verificar-pagamento | extraido | F001, p.6, P18 | realiza baixa manual no A2O. | Elemento extraído; ver documentação da atividade. | — |
| decisao-pagamento-identificado | extraido | F001, p.6, P18 | realiza baixa manual no A2O. | Elemento extraído; ver documentação da atividade. | — |
| atividade-baixar-titulo | extraido | F001, p.6, P18 | realiza baixa manual no A2O. | Elemento extraído; ver documentação da atividade. | — |
| fim-financeiro-cliente-encerrado | extraido | F001, p.6, P18 | realiza baixa manual no A2O. | Elemento extraído; ver documentação da atividade. | — |
| atividade-cobrar-atraso | extraido | F001, p.6, P18 | realiza baixa manual no A2O. | Elemento extraído; ver documentação da atividade. | — |
| inicio-rotina-jornada | extraido | F001, p.6, P19 | Diariamente e no fechamento mensal | Elemento extraído; ver documentação da atividade. | — |
| atividade-controlar-jornada | extraido | F001, p.6, P19 | Diariamente e no fechamento mensal | Elemento extraído; ver documentação da atividade. | — |
| fim-ciclo-jornada-documentado | extraido | F001, p.6, P19 | Diariamente e no fechamento mensal | Elemento extraído; ver documentação da atividade. | — |
| inicio-problema-manutencao | extraido | F001, p.6, P20 | Motorista comunica problema e envia fotos. | Elemento extraído; ver documentação da atividade. | — |
| atividade-comunicar-problema | extraido | F001, p.6, P20 | Motorista comunica problema e envia fotos. | Elemento extraído; ver documentação da atividade. | — |
| pendencia-detalhar-manutencao | gap | F001, p.6, P20 | Motorista comunica problema e envia fotos. | F001 p.2/p.11 prevalecem sobre menção genérica a rotinas preventivas na linha P20; não modelar OS/compras/aprovação/pagamento/liberação como fatos. | — |
| pendencia-modalidade-acompanhamento | gap | F001, p.5, P12 | Da saída até a descarga | Ramo condicional de validação: somente se houver modalidade não coberta pelas categorias descritas. Não afirma existência de outra frota. | — |
| atividade-validar-acerto | inferido | F001, p.5, P16 | Assistente lança cargas; | Ordem lançamento → validação inferida da redação; pode haver conferência anterior. | media |


**Regra de interpretação:** as raias de decisões de modalidade identificam o ponto de leitura operacional, não um novo executor de autorização. A convergência da margem está marcada como inferência de confiança média; as atividades de avaliação mantêm os responsáveis extraídos. O ramo “outra modalidade, se existir” é apenas pendência condicional e não afirma uma modalidade adicional.

## 5. GAPs e perguntas

Lacunas abaixo incluem faltas de especificação e riscos de controle explicitamente documentados. Criticidade alta indica necessidade de validar o recorte, não prova de que a operação real esteja parada. Média indica controle, integração ou gestão; baixa indica mensuração. Um GAP por par elemento/tipo; cada registro é contado uma vez. A dúvida sobre cobertura de modalidades e seu ramo condicional compartilham o mesmo GAP, contado uma única vez.

| ID | Elemento | Tipo | Prioridade | Informação ausente | Pergunta de validação |
| --- | --- | --- | --- | --- | --- |
| gap-decisao-margem-minima-responsavel | decisao-margem-minima | responsavel | alta | Alçada de fechamento do tanque não individualizada entre Faturista, Gerente e Supervisor. | No tanque, quem confirma formalmente o resultado ≥40% e autoriza o fechamento? |
| gap-atividade-consultar-risco-criterio | atividade-consultar-risco | criterio | alta | Retorno da Angel Lira só em pendências; evidência objetiva para reconhecer aprovação sem retorno não detalhada (p.2/p.4). | Quando não há retorno da Angel Lira, qual registro ou regra confirma a aprovação para cadastrar? |
| gap-pendencia-modalidade-acompanhamento-destino | pendencia-modalidade-acompanhamento | destino | alta | Destino do acompanhamento para eventual modalidade não descrita é desconhecido. | Se houver modalidade fora de terceiros/Sider/tanque/combustível, qual é seu fluxo de acompanhamento? |
| gap-atividade-agendar-janela-responsavel | atividade-agendar-janela | responsavel | alta | P13 informa apenas “Responsável pela operação”, sem vincular formalmente cada modalidade ao cargo executor. | Qual cargo agenda/reagenda e confirma a descarga em cada modalidade? |
| gap-atividade-validar-acerto-sequencia | atividade-validar-acerto | sequencia | alta | P16 sucede documentação, mas não fixa dependência obrigatória entre lançamento de cargas e início da conferência final. | A conferência final só inicia após o lançamento no A2O ou pode antecedê-lo? |
| gap-atividade-pedir-pagamento-metodo | atividade-pedir-pagamento | metodo | alta | Regras de adiantamento e saldo do terceiro permanecem pendentes (p.11); pedido no Bitrix não comprova pagamento. | Quais regras, responsáveis e documentos autorizam adiantamento e saldo do prestador? |
| gap-pendencia-detalhar-manutencao-criterio | pendencia-detalhar-manutencao | criterio | alta | Gatilho não classificado como preventiva, corretiva ou ambas (p.11). | O acionamento por problema/fotos é corretivo, preventivo ou ambos, e qual critério separa os casos? |
| gap-pendencia-detalhar-manutencao-destino | pendencia-detalhar-manutencao | destino | alta | Regra de liberação do veículo e encerramento da manutenção não validada (p.11). | Quem libera o veículo, com quais evidências e como encerra a manutenção? |
| gap-pendencia-detalhar-manutencao-metodo | pendencia-detalhar-manutencao | metodo | alta | OS, compras, aprovações e pagamento de manutenção não validados (p.11); necessidade operacional não detalhada. | Qual sequência real e quais responsáveis tratam OS, compras, aprovações e pagamento após o acionamento? |
| gap-atividade-captar-cargas-controle | atividade-captar-cargas | controle | media | Contatos pessoais/WhatsApp sem garantia documentada de continuidade e histórico (p.9). | Como o histórico comercial fica acessível quando o responsável está ausente? |
| gap-atividade-buscar-terceiro-controle | atividade-buscar-terceiro | controle | media | Limite do Fretebras é gargalo confirmado; teto e incidência do bloqueio não quantificados (p.9, A01 p.7). | Qual limite do plano Fretebras se aplica e com que frequência impede localizar/contatar terceiros? |
| gap-atividade-repassar-operacao-controle | atividade-repassar-operacao | controle | media | Atualização dos POPs e validação de responsabilidades ainda pendentes (p.10/p.11). | Quem aprova a matriz de responsabilidades e publica os POPs alinhados ao AS-IS? |
| gap-atividade-repassar-operacao-metodo | atividade-repassar-operacao | metodo | media | Formato manual de repasse; campos mínimos e registro oficial não definidos (p.7 A03; p.10). | Quais campos e evidências tornam o repasse completo e onde está o registro oficial? |
| gap-atividade-programar-terceiro-controle | atividade-programar-terceiro | controle | media | Duplicidade de planilhas/A2O; sistema oficial por etapa ainda pendente (p.8 A07; p.9). | Qual registro é a fonte oficial da programação e como se conciliam as duplicidades? |
| gap-atividade-validar-acerto-prazo | atividade-validar-acerto | prazo | media | Metas e indicadores de tempo de acerto e pendências não definidos (p.11). | Qual meta de tempo de acerto será aprovada e como será medida? |
| gap-atividade-controlar-jornada-controle | atividade-controlar-jornada | controle | media | Horários dependem de contato posterior e lançamento manual (p.9); incidência e tratamento da exceção não quantificados. | Quais registros de jornada faltam, com que frequência e como se valida a complementação manual? |
| gap-atividade-captar-cargas-custo | atividade-captar-cargas | custo | baixa | Não mensurado; valor depende do frete; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de receber e captar cargas, por operação ou período? |
| gap-atividade-definir-frota-custo | atividade-definir-frota | custo | baixa | Não mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de definir frota própria ou terceiro, por operação ou período? |
| gap-atividade-repassar-operacao-custo | atividade-repassar-operacao | custo | baixa | Sem custo direto mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de repassar operação definida, por operação ou período? |
| gap-atividade-consultar-risco-custo | atividade-consultar-risco | custo | baixa | Taxa não validada no levantamento; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de solicitar documentos e consultar risco, por operação ou período? |
| gap-atividade-cadastrar-a2o-custo | atividade-cadastrar-a2o | custo | baixa | Esforço interno; custo não mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de cadastrar no a2o, por operação ou período? |
| gap-atividade-programar-terceiro-custo | atividade-programar-terceiro | custo | baixa | Esforço interno; risco de duplicidade de controles; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de programar viagem, por operação ou período? |
| gap-atividade-programar-frota-custo | atividade-programar-frota | custo | baixa | Esforço interno; risco de duplicidade de controles; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de programar viagem, por operação ou período? |
| gap-atividade-enviar-ordem-geral-custo | atividade-enviar-ordem-geral | custo | baixa | Sem custo direto mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de emitir/enviar ordem de carregamento, por operação ou período? |
| gap-atividade-enviar-ordem-combustivel-custo | atividade-enviar-ordem-combustivel | custo | baixa | Sem custo direto mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de emitir/enviar ordem de carregamento, por operação ou período? |
| gap-atividade-emitir-documentos-combustivel-custo | atividade-emitir-documentos-combustivel | custo | baixa | Tributos/taxas por operação; não mensurados; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de emitir ct-e/mdf-e e liberar motorista, por operação ou período? |
| gap-atividade-emitir-documentos-demais-custo | atividade-emitir-documentos-demais | custo | baixa | Tributos/taxas por operação; não mensurados; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de emitir ct-e/mdf-e e liberar motorista, por operação ou período? |
| gap-atividade-acompanhar-terceiros-sider-custo | atividade-acompanhar-terceiros-sider | custo | baixa | Esforço interno; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de acompanhar viagem, por operação ou período? |
| gap-atividade-acompanhar-tanque-custo | atividade-acompanhar-tanque | custo | baixa | Esforço interno; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de acompanhar viagem, por operação ou período? |
| gap-atividade-agendar-janela-custo | atividade-agendar-janela | custo | baixa | Sem custo específico mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de agendar e confirmar descarga, por operação ou período? |
| gap-atividade-confirmar-descarga-custo | atividade-confirmar-descarga | custo | baixa | Sem custo específico mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de agendar e confirmar descarga, por operação ou período? |
| gap-atividade-entregar-documentos-retorno-custo | atividade-entregar-documentos-retorno | custo | baixa | Sem custo direto mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de receber documentos do retorno, por operação ou período? |
| gap-atividade-conferir-documentos-custo | atividade-conferir-documentos | custo | baixa | Esforço interno; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de conferir e organizar documentação, por operação ou período? |
| gap-atividade-controlar-jornada-custo | atividade-controlar-jornada | custo | baixa | Esforço interno; retrabalho não mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de controlar jornada e dar suporte à frota própria, por operação ou período? |
| gap-atividade-comunicar-problema-custo | atividade-comunicar-problema | custo | baixa | Variável; não mensurado; valor do esforço/custo da atividade não apurado. | Qual é o custo ou esforço mensurado de tratar manutenção e documentação de manutenção, por operação ou período? |


### Pontos críticos do próprio documento

| Ponto | Classificação preservada | Evidência | Tratamento documental |
| --- | --- | --- | --- |
| Limite Fretebras | Gargalo confirmado | F001 p.9; A01 p.7 | Quantificar bloqueios e validar limite; alternativa atual é rede de contatos. Upgrade não implantado nesta análise. |
| Contatos pessoais/WhatsApp | Gap de continuidade | F001 p.9; A02/A03 p.7 | Validar registro acessível e campos do repasse. CRM/base são propostas. |
| Complementação manual de jornada | Gap de controle | F001 p.9; P19 p.6 | Medir e validar a complementação; dispositivos/rotina de exceção são propostas. |
| Controles paralelos | Gap de integração | F001 p.9; A07 p.8 | Fonte oficial por etapa ainda precisa ser definida. |
| Responsabilidades versus POP | Gap documental | F001 p.10; A05 p.8 | Atualizar POP/RACI após validação; modelo usa a divisão atual. |
| Manutenção | Gap de mapeamento | F001 p.2/6/11 | Somente comunicação por problema/fotos confirmada; etapas seguintes pendentes. |
| Janela de descarga | Regra operacional | F001 p.2/5/9 | Perda rara e reagendamento funcional; não classificada como gargalo. |
| Cobrança do cliente | Processo validado | F001 p.2/6/9 | Preservados faturamento, cobrança, recebimento e baixa manual. Não confundido com financeiro do prestador. |


### Pendências adicionais já declaradas na fonte

F001 p.11 pede mensurar custos do Fretebras, CRM/base, dispositivos e integrações; aprovar metas e indicadores de prazo, retrabalho, utilização, margem e pendências; validar o 5W2H pelas áreas e atualizar POPs. São pendências de gestão e de propostas de melhoria; não receberam novos nós AS-IS ou prazos inventados. A cadência de cobrança e limite de tentativas não foram transformados em GAP de processo: a fonte valida a regra “até regularização”.

## 6. Resumo executivo

- Atividades: **30**, derivadas das 20 linhas P01–P20.
- Decisões: **10**. Blocos paralelos: **0**.
- Raias: **12**. Inícios: **4**; fins de recorte: **5**; pendências explícitas: **2**.
- GAPs únicos neste registro: **35** — Alta: **9**, Média: **7**, Baixa: **19**.
- Elementos totais: **51**. Conexões: **55**.

**Conclusões:** o macrofluxo comercial, operacional e financeiro do cliente está documentado. O documento não sustenta tratar janela de descarga ou cobrança validada como gargalos. O gargalo confirmado é o limite do plano Fretebras. As maiores incertezas para aprovação do modelo são o critério de aprovação do risco sem retorno, as alçadas no tanque, os responsáveis da descarga, a cobertura de modalidades, a sequência do acerto e o financeiro do prestador. A manutenção continua sem fluxo completo validado.

**Recomendações para validação, sem alterar o AS-IS:** responder às lacunas altas na ordem apresentada; validar dependências entre P11/P16/P17 sem tornar o acerto um bloqueio de faturamento; quantificar limite Fretebras e complementação de jornada; pactuar fonte oficial dos controles; atualizar POPs com a divisão atual de responsabilidades. A01–A07 ficam registradas como propostas da fonte, dependentes de aprovação, não como TO-BE aprovado.

**Arquivos:** `transportadora-as-is.drawio` e `transportadora-relatorio.md`. O modelo técnico interno foi preservado no ambiente para reprodução, sem entrega JSON por padrão.

**Validações executadas:** gerador original Raias 1.0 sem alterações; XML bem formado; IDs únicos; referências de arestas/raias válidas; decisões com saídas rotuladas; todos os nós alcançáveis de algum início e com caminho a fim ou pendência; contagens derivadas do mesmo inventário; comparação byte a byte na repetição aprovada. **Estrutura XML validada; abertura visual no draw.io não realizada.** Não há ferramenta de visualização draw.io disponível nesta sessão. Validação técnica não significa aprovação das lacunas de negócio nem comprova a renderização visual.

## 7. Próximos passos

1. Abrir o arquivo `.drawio` em draw.io/diagrams.net, conferir legibilidade, conectores e raias com os responsáveis.
2. Responder às perguntas altas, especialmente manutenção e regras do prestador.
3. Confirmar os dois encadeamentos inferidos: convergência/alçada da margem e relação entre lançamento e conferência do acerto.
4. Validar com Comercial, Faturista, Assistente Comercial, Administrativo, Faturamento, Crédito e Cobrança, Jornada e Manutenção; atualizar POPs após aprovação.
5. Somente se solicitado, criar TO-BE separado para as melhorias A01–A07, com custos/metas aprovados e AS-IS preservado.
