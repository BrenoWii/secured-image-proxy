Image Auth Proxy
image-auth-proxy é um serviço de camada intermediária para controlar o acesso a imagens baseadas em roles de usuários. Ele autentica os usuários e permite que apenas aqueles com permissões específicas acessem as URLs das imagens de serviços internos.

Funcionalidades
Autenticação: Usa tokens JWT para validar a identidade do usuário.
Autorização baseada em roles: Apenas usuários com permissões específicas (roles) podem acessar determinadas imagens.
Proxy para Serviço Interno: Encaminha a requisição de imagens para um serviço interno após validação.
Estrutura do Projeto
Este projeto é construído utilizando NestJS com as seguintes funcionalidades principais:

Autenticação (JWT): Garantia de que o usuário está autenticado antes de acessar as imagens.
Autorização por Roles: Validação das permissões do usuário com base em sua role (ex.: "admin", "user").
Camada Interceptadora: Intercepta as requisições e valida as permissões antes de encaminhar para o serviço interno.
Instalação
Clone o repositório:

bash
Copiar código
git clone https://github.com/seu-usuario/image-auth-proxy.git
cd image-auth-proxy
Instale as dependências:

bash
Copiar código
npm install
Configure a chave secreta do JWT: No arquivo src/auth/auth.module.ts, substitua 'your-secret-key' por uma chave secreta de sua preferência.

Inicie o servidor:

bash
Copiar código
npm run start
O servidor estará disponível em http://localhost:3000.

Endpoints
GET /images/
Este endpoint permite que usuários autorizados acessem as imagens protegidas. A requisição é validada com o token JWT e a role do usuário. Caso o usuário tenha permissão, a imagem será retornada.

Exemplo de Requisição:

http
Copiar código
GET /images/123 HTTP/1.1
Host: localhost:3000
Authorization: Bearer <seu-token-jwt>
Resposta:

Se autorizado: Retorna a imagem solicitada.
Se não autorizado: Retorna um erro 401 (não autorizado) ou 403 (proibido).
Módulos e Dependências
@nestjs/jwt: Para lidar com autenticação baseada em JWT.
@nestjs/passport: Para integração com Passport.js.
passport-jwt: Estratégia de Passport para autenticação JWT.
passport: Middleware de autenticação.
Contribuições
Sinta-se à vontade para contribuir com o projeto! Se você encontrar algum bug ou tiver uma ideia de melhoria, crie um issue ou um pull request.

Licença
Este projeto está licenciado sob a MIT License - veja o arquivo LICENSE para mais detalhes.
