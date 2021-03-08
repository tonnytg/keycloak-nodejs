## Como executar

#### Como construir
`docker-compose up --build -d`


#### Cria os alias no seu hosts

Adicione os nomes para o localhost, o trafego será redirecionado para o NGINX e ele irá redirecionar internamente os demais pacotes.

echo "127.0.0.1  webserver.com.br" >> /etc/hosts
echo "127.0.0.1  keycloak.com.br" >> /etc/hosts


#### Access KeyCloak
`http://keycloak.com.br`

- Login Admin: `http://keycloak.com.br/auth/admin/master/console/#/realms/master`

Autentica com `admin` senha `admin`
Depois importa o arquivo JSON que tem os dados do cliente para o NODEJS usar

O KeyCloak vai gerar um REALM e ele tem um ID tem que pegar ele para alimentar o arquivo:
`webserver>>keycloak.json`

Feito a configuração o NodeJS já está pronto para usar.




#### Access Application
`http://webserver.com.br`

No arquivo do JSON que foi importado, existe um usuário `user` com a senha `password`
Você pode tentar usar ele... Se der acesso negado, pode ser erro com o REAML TOKEN no keycloak.json

#### Se tiver erros?

1. Aparecer erro "We are sorry."
Esse erro acontece porque o KeyCloak não está configurado
Como resolver: Tem que importar o json do keycloak

### Links

 1. Link do projeto
 https://github.com/keycloak/keycloak-nodejs-connect/tree/master/example

 2. Encode e Decode
https://www.jsonwebtoken.io/ 
