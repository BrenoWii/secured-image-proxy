# Image Auth Proxy

**image-auth-proxy** é um serviço de camada intermediária para controlar o acesso a imagens baseadas em roles de usuários. Ele autentica os usuários e permite que apenas aqueles com permissões específicas acessem as URLs das imagens de serviços internos.

## Funcionalidades

- **Autenticação:** Usa tokens JWT para validar a identidade do usuário.
- **Autorização baseada em roles:** Apenas usuários com permissões específicas (roles) podem acessar determinadas imagens.
- **Proxy para Serviço Interno:** Encaminha a requisição de imagens para um serviço interno após validação.

## Estrutura do Projeto

Este projeto é construído utilizando **NestJS** com as seguintes funcionalidades principais:

- **Autenticação (JWT)**: Garantia de que o usuário está autenticado antes de acessar as imagens.
- **Autorização por Roles**: Validação das permissões do usuário com base em sua role (ex.: "admin", "user").
- **Camada Interceptadora**: Intercepta as requisições e valida as permissões antes de encaminhar para o serviço interno.

## Instalação

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/seu-usuario/image-auth-proxy.git
   cd image-auth-proxy
