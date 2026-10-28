# Fontes da cotação à vista contra o real

Este arquivo está em `docs/research/cotacao-a-vista-contra-o-real.md`.

Consultado em 28 de outubro de 2026, nas páginas de quem publica o número. Esta nota lista as fontes. Não escolhe uma.

A tela precisa de uma cotação à vista, uma por moeda, com preço, horário e o nome da fonte. Abaixo, o que cada fonte consultada publica: à vista, fechamento ou futuro; se o horário vem no dado; e quais moedas contra o real entram.

## Banco Central, boletins PTAX

O [conjunto de dados](https://dadosabertos.bcb.gov.br/dataset/taxas-de-cambio-todos-os-boletins-diarios) descreve cinco boletins por dia útil: abertura, três intermediários e fechamento. Desde 1º de julho de 2011, pela [Circular 3.506](https://normativos.bcb.gov.br/Lists/Normativos/Attachments/49545/Circ_3506_v4_L.pdf), a PTAX do dólar sai de quatro consultas aos dealers. Em cada consulta o dealer informa compra e venda do mercado interbancário à vista, liquidação em D+2, no instante em que a janela abre. O início de cada janela é sorteado entre 10h e 10h10, 11h e 11h10, 12h e 12h10, e 13h e 13h10.

O [estudo do Banco Central sobre a PTAX](https://www.bcb.gov.br/conteudo/relatorioinflacao/EstudosEspeciais/EE042_A_taxa_de_cambio_de_referencia_Ptax.pdf) diz que, em cada consulta, caem as duas maiores e as duas menores de cada ponta, e o boletim é a média simples do que resta. O quinto boletim, o de fechamento, é a média simples dos quatro. O conjunto de dados repete que o fechamento é a média aritmética dos boletins do dia.

A [documentação do serviço](https://www.bcb.gov.br/conteudo/dadosabertos/BCBDepin/gnastportal-dados-abertostaxas-de-cambio---todos-os-boletins-diarios.pdf) define `dataHoraCotacao` como data, hora e minuto, e `tipoBoletim` como Abertura, Intermediário, Fechamento Interbancário ou Fechamento. Na consulta de 28 de outubro de 2026 ao dólar, o campo voltou com hora, minuto e segundo, nos tipos Abertura, Intermediário e Fechamento PTAX.

As moedas do conjunto, conferidas no recurso Moedas no mesmo dia, são USD, EUR, GBP, JPY, CHF, CAD, AUD, DKK, NOK e SEK. A cotação é quantidade de reais por uma unidade da moeda. A paridade das outras moedas contra o dólar vem de agências de informação. A página nomeia a fonte: Refinitiv, exceto o USDBRL. A cotação em real dessas moedas é a cotação do dólar cruzada com essa paridade: tipo A divide, tipo B multiplica. No mesmo dia, o boletim de fechamento do euro trouxe paridade contra o dólar e cotação em reais, com `dataHoraCotacao`.

O dado publicado é boletim de consulta, algumas vezes ao dia, com horário. O fechamento é média. O intermediário também é média das cotações da janela, não o último negócio.

## B3, futuro de dólar

A página do [futuro de taxa de câmbio de reais por dólar comercial](https://www.b3.com.br/pt_br/produtos-e-servicos/negociacao/moedas/futuro-de-taxa-de-cambio-de-reais-por-dolar-comercial.htm) define o contrato DOL. O objeto é a taxa de reais por dólar. A cotação é em reais por USD 1.000. O vencimento é o primeiro dia útil do mês, com liquidação financeira.

A tabela de [câmbio e dólar pronto](https://www.b3.com.br/pt_br/solucoes/plataformas/puma-trading-system/para-participantes-e-traders/horario-de-negociacao/derivativos/cambio-e-dolar-pronto/) lista o DOL e o mini WDO das 9h às 18h30. A apuração do ajuste do dólar vai das 15h50 às 16h, e o ajuste do WDO é o do DOL do mesmo vencimento. A tabela também lista futuros de euro, libra, iene, franco suíço, dólares australiano e canadense, peso mexicano e outras moedas, em geral das 9h às 18h, além de opções, forward points e o casado. Não há uma linha que seja só o dólar pronto com um último preço.

O [UP2DATA de moedas](https://www.b3.com.br/pt_br/market-data-e-indices/servicos-de-dados/up2data/s_rds3/) entrega cadastro, posição em aberto, negócios, preço de ajuste e preço de referência de futuros e opções. O arquivo do DOL sai por volta das 18h; o das outras moedas futuras, por volta das 18h15. É arquivo do dia, com horário de publicação do arquivo.

## B3, dólar à vista e sinal de market data

A página de [dólar à vista](https://www.b3.com.br/pt_br/produtos-e-servicos/negociacao/moedas/dolar-a-vista.htm) descreve dois modos. No pregão, o produto é o casado CSD2: um futuro de dólar e a ponta inversa de dólar à vista. A cotação do casado é o diferencial entre o primeiro vencimento do futuro e o dólar à vista, em reais por USD 1.000. No balcão, a página diz que os preços das operações não são divulgados.

O [market data](https://www.b3.com.br/pt_br/market-data-e-indices/servicos-de-dados/market-data/plataformas-de-difusao/) diz que o vendor recebe, em tempo real, cotações de câmbio (dólar pronto) de operações no Sisbex, junto com derivativos. A página não mostra um preço, não descreve um campo de horário e não lista outra moeda contra o real. As [perguntas frequentes](https://www.b3.com.br/pt_br/market-data-e-indices/servicos-de-dados/market-data/distribuidores/perguntas-frequentes/) repetem o dólar pronto nesse segmento e dizem que a distribuição pode ser em tempo real ou com atraso de até 15 minutos.

O número que a página do produto publica é o diferencial do casado. O preço do balcão fica de fora. O sinal de dólar pronto é feed para vendor, só do dólar, sem um último preço e um horário numa página pública.

## B3, indicadores do boletim diário

O [boletim de 22 de dezembro de 2025](https://arquivos.b3.com.br/bdi/download/bdi/2025-12-22/BDI_02-0_20251222.pdf) publica os indicadores do dia usados para precificar futuros e opções. Para o DOL aparecem a PTAX800 de venda, o indicador RTDOLD1 chamado "DÓLAR B3 SPOT - 1 DIA" e também descrito como cotação de reais por dólar com liquidação em D+1 definida às 16h, o RTDOLD2 "DÓLAR B3 SPOT - 2 DIAS" e o dólar cupom limpo calculado pela B3. As linhas de spot das outras moedas são pares contra o dólar, com "16:00 horário local", ou preço WMR. O arquivo é diário. O horário que aparece é o das 16h da descrição, não o relógio de um último negócio contra o real.

## AwesomeAPI

A [documentação](https://docs.awesomeapi.com.br/api-de-moedas) chama o endpoint `/json/last/:moedas` de última ocorrência, atualizada em tempo real. Sem chave, a resposta fica em cache por um minuto. Cada par volta com compra (`bid`), venda (`ask`) e `timestamp`, que a legenda chama de hora da negociação em UTC. `create_date` é essa hora em UTC-3. O exemplo é um objeto por par: USD-BRL, EUR-BRL e BTC-BRL.

A mesma página separa essa série da PTAX e do turismo. A PTAX fica em códigos como USD-BRLPTAX e EUR-BRLPTAX, descrita como taxa do Banco Central. O turismo fica em USD-BRLT e EUR-BRLT. Outro endpoint, `/json/daily`, é o fechamento dos últimos dias.

A [lista de combinações](https://economia.awesomeapi.com.br/xml/available), lida em 28 de outubro de 2026, tinha 52 códigos no formato `XXX-BRL`, dez códigos `BRLPTAX` e dois de turismo. Os dez `BRLPTAX` são as mesmas dez moedas do Banco Central. Nos 52 entram moedas fiduciárias e também códigos de cripto e os metais XAU e XAG. A documentação não diz de qual mercado vem a hora da negociação do par `XXX-BRL`.

No mesmo dia, `/json/last/USD-BRL,EUR-BRL,GBP-BRL` devolveu um objeto por par, com `bid`, `ask`, `timestamp` e `create_date` naquela tarde.

## HG Brasil

A [página de mercado](https://hgbrasil.com/docs/finance) diz que as cotações são atualizadas em intervalos de 15 a 45 minutos durante o pregão. O bloco `currencies` do exemplo tem `source` igual a BRL, no sentido de moeda base, e compra e venda de USD, EUR, GBP, ARS, CAD, AUD, JPY, CNY e BTC. A tabela de campos desse bloco não tem horário.

A [página de moedas](https://hgbrasil.com/docs/finance/currencies) documenta outro endpoint, `/v2/finance/quotes`, com tickers `FOREX:USDBRL` e `FOREX:EURBRL`. `quote.value` é o último valor negociado. `quote.updated_at` é o timestamp da cotação. No exemplo, `source.name` é FOREX e `source.full_name` é Foreign Exchange Market. O exemplo e a lista da página ainda nomeiam ARS, AUD, CAD, CNY, GBP e JPY contra o real. A página não diz qual praça gerou o último valor.

## Yahoo Finance

A página [USD/BRL](https://finance.yahoo.com/quote/USDBRL=X/) titula o número como live rate e mostra o relógio no formato "As of", em GMT, com o mercado aberto. O endpoint de gráfico `USDBRL=X`, consultado na mesma data, classifica o instrumento como CURRENCY, põe `exchangeName` e `fullExchangeName` em CCY, a moeda em BRL, e traz `regularMarketTime`. `EURBRL=X` repete o mesmo tipo de campos, com outro `regularMarketTime`. As duas respostas não chamam o número de PTAX nem de contrato futuro, e não nomeiam um mercado além de CCY.

## Banco Central Europeu

A página das [taxas de referência do euro](https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/html/index.en.html) atualiza os números por volta das 16:00 CET em dia útil, a partir da concertação por volta das 14:10 CET. A tabela de 28 de outubro de 2026 tem uma coluna chamada Spot e inclui o real, cotado contra o euro. O [quadro da metodologia](https://www.ecb.europa.eu/stats/pdf/exchange/Frameworkfortheeuroforeignexchangereferencerates.en.pdf) diz que as taxas são de informação e desaconselha o uso em transação. É uma referência diária do euro, com o real na lista. O relógio é o da publicação do dia, não o de um último negócio contra o real.

## OANDA, conversor público

O [conversor](https://www.oanda.com/currency-converter/pt/?amount=25&from=USD&to=BRL) usa o OANDA Rates e diz que os valores são a média diária das taxas de compra e de venda recebidas de várias fontes. A página converte dólar e real. Não mostra o horário de um último negócio. A mesma família de páginas anuncia uma API de dados em tempo real; o texto do conversor não documenta os campos dessa API.

## O que essas páginas não fecham

- De qual mercado saem a hora da negociação da AwesomeAPI, o último valor negociado da HG Brasil e a taxa CURRENCY do Yahoo Finance.
- Uma página pública da B3 com um último preço à vista, um horário e cada moeda contra o real.
- Os campos da API em tempo real que a OANDA anuncia no conversor.
