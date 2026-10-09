# ComparaAI - Laboratório OAuth Mercado Livre

## Finalidade Provisória
Este repositório serve como a estrutura mínima e estática para um laboratório de testes da autenticação OAuth 2.0 (Authorization Code) utilizando a API oficial do Mercado Livre. O foco atual é unicamente viabilizar URLs seguras (HTTPS) para o fluxo de redirecionamento, não compreendendo o desenvolvimento do produto final.

## Arquivos Existentes
- `index.html`: Página principal provisória.
- `callback/index.html`: Endpoint estático de destino para o fluxo de callback do OAuth.
- `README.md`: Documentação atual do projeto.

## Utilização do GitHub Pages
Os arquivos estão configurados para serem hospedados de forma gratuita e rápida via GitHub Pages. Isso provê automaticamente conectividade HTTPS válida, um requisito obrigatório da API do Mercado Livre para as URIs de redirecionamento.

## Limitações da Hospedagem Estática
Pelo fato do GitHub Pages prover um servidor estático:
- **Não há backend:** Códigos de autorização recebidos na URL não podem ser processados ou trocados por tokens de acesso automaticamente no lado do servidor.
- É estritamente proibido o uso de parâmetros de URL para realizar redirecionamentos baseados em JavaScript diretamente para o ambiente local sem prévia autorização.
- O laboratório real e o manuseio dos tokens ocorrerão no ambiente de execução isolado (local) conforme o andamento das fases.

## Cuidados com Credenciais OAuth e Proibições
- **NENHUM segredo (Client Secret, Access Tokens, Refresh Tokens) deve ser incluído neste repositório.**
- Não armazenar, sob hipótese alguma, credenciais em logs ou arquivos textuais.
- Dados sensíveis só devem existir em ambiente de desenvolvimento local devidamente ignorados por `.gitignore` (ex: arquivo `.env`), os quais ainda não foram criados nesta fase.

## Etapas Pendentes (Próximas Fases)
- Implementação e testes do fluxo de autorização (`/authorize`).
- Obtenção dos códigos de autorização.
- Troca do código de autorização por Access Token / Refresh Token através da rota de token via backend local.
- Consultas autorizadas (GET) à API do Mercado Livre utilizando os tokens.
