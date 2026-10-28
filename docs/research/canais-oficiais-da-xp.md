# Canais oficiais da XP para posição, movimentação e conta

Este arquivo está em `docs/research/canais-oficiais-da-xp.md`. O repositório não tinha convenção anterior para notas de pesquisa.

Consultado em 28 de outubro de 2026, só em páginas da XP. Esta nota lista os canais. Não escolhe um. Open Finance ficou de fora.

## API de parceiros

O [portal de desenvolvedores](https://developer.xpinc.com/) diz que as APIs atendem parceiros XP que precisam dos dados do próprio negócio, e nomeia captação, posição, movimentação, produto, conta e comissão. A mesma página anuncia documentação técnica e sandbox.

Sem login, o [catálogo](https://developer.xpinc.com/apis) mostra "No APIs found". A [documentação](https://developer.xpinc.com/documentacao) abre em branco. O [login](https://developer.xpinc.com/signin) pede para entrar pelo botão ACESSAR. Endpoints e campos não estão nessas páginas públicas.

A página fala em parceiro e em dados do negócio. Ela não diz que o assessor, como pessoa, chama a API, nem que existe uma API equivalente para o cliente.

## App XP, extrato da Conta investimento

O artigo [Como consulto o extrato de minha Conta investimento?](https://atendimento.xpi.com.br/artigo/2480-como-consulto-o-extrato-de-minha-conta-investimento) descreve o cliente logado no App XP. O caminho é a aba Investimentos, Saldo Conta Investimento Nacional, e então Saldo, que abre o extrato. Dá para filtrar o período e baixar PDF ou CSV.

Esse artigo cobre a movimentação da conta investimento. Não descreve a posição dos produtos e não descreve uma API.

## XP Mobile, posição da carteira

O artigo [Como acompanhar sua posição em carteira no XP Trader?](https://atendimento.xpi.com.br/artigo/1528-como-acompanhar-sua-posicao-em-carteira-no-xp-trader) manda abrir, no XP Mobile, a aba Posição. Em Minha Conta aparecem o patrimônio na XP Investimentos e o valor em ações, opções, termos, aluguel (BTC), mercadorias e futuros e ouro. A mesma tela cita proventos projetados, renda fixa e garantias, Tesouro Direto, fundos, fundos imobiliários, clubes, previdência, COE e financeiro disponível. O resumo de conta mostra o saldo disponível (D+0) e as garantias. A tela seguinte detalha a custódia de renda variável.

É uma tela do cliente sobre a própria carteira. O artigo não descreve movimentação histórica nem uma API, e não descreve o assessor vendo os clientes.

## HUB do assessor

A página [Seja um assessor](https://www.xpi.com.br/seja-um-assessor/) diz que o assessor tem acesso ao HUB e a ferramentas de CRM. Essa página não descreve leitura de posição, movimentação ou conta.

## O que a fonte pública não fecha

- A lista de operações da API de parceiros, e o formato de cada campo.
- Se quem consome a API é o assessor ou o escritório parceiro.
- Uma API pública equivalente, para o cliente, à API de parceiros.
