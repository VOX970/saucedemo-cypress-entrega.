Instruções para a atividade 14 :

Projeto de Automação E2E - SauceDemo com Cypress

Este repositório contém a suíte de testes automatizados End-to-End (E2E) desenvolvida em Cypress para a aplicação SauceDemo, cobrindo os fluxos de autenticação, gestão de catálogo/carrinho e finalização de compra.

1. Pré-requisitos e Instalação

Pré-requisitos do Ambiente

O projeto foi desenvolvido para ser executado em ambientes Node.js e sistemas Linux (como o GitHub Codespaces).

Caso esteja a executar num ambiente Linux sem interface gráfica (headless), é necessário instalar as dependências de sistema para suporte ao browser do Cypress:

# Atualizar repositórios e instalar dependências do sistema Linux/Ubuntu
sudo dpkg --add-architecture amd64
sudo apt-get update && sudo apt-get install -y libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libnss3 libnspr4 libx11-xcb1 libxtst6 xauth xvfb


Instalação do Projeto

Clone o repositório público:

git clone https://github.com/VOX970/saucedemo-cypress-entrega.git


Aceda ao diretório do projeto:

cd saucedemo-cypress


Instale as dependências do Node.js:

npm install


2. Execução dos Testes

Para executar toda a suíte de testes em modo headless (via terminal):

npm run cy:run


3. Descrição dos Testes Implementados

A suíte contempla 8 cenários automatizados End-to-End (E2E) organizados em 3 módulos funcionais:

1. Autenticação (cypress/e2e/auth/autenticacao.cy.js)

Login com Sucesso: Valida o acesso à plataforma utilizando credenciais válidas (standard_user), garantindo o redirecionamento correto para o catálogo de produtos.

Bloqueio de Usuário Inválido / Bloqueado: Valida o comportamento do sistema e a exibição de mensagens de erro apropriadas ao tentar autenticar com credenciais incorretas ou utilizador bloqueado (locked_out_user).

2. Catálogo e Carrinho (cypress/e2e/carrinho/catalogo-e-carrinho.cy.js)

Listagem e Visualização: Verifica se a lista de produtos é carregada corretamente com nomes, descrições e preços correspondentes.

Ordenação de Produtos: Testa a funcionalidade dos filtros de ordenação do catálogo (ex: preço do menor para o maior e ordem alfabética).

Adição de Itens ao Carrinho: Valida a inclusão de produtos no carrinho e a atualização em tempo real do contador do ícone do carrinho.

Remoção de Itens: Valida a remoção de produtos tanto na página principal do catálogo quanto dentro do carrinho de compras.

3. Finalização de Compra (cypress/e2e/checkout/finalizacao-compra.cy.js)

Preenchimento do Formulário de Checkout: Valida os campos obrigatórios do formulário do comprador (First Name, Last Name, Postal Code).

Revisão e Confirmação do Pedido: Valida o resumo dos itens selecionados, a precisão do cálculo de impostos e totais, e a conclusão com a mensagem de sucesso (THANK YOU FOR YOUR ORDER).
