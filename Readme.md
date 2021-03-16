## Como executar

#### Como construir
`docker-compose up --build -d`


#### Cria os alias no seu hosts

Adicione os nomes para o localhost, o trafego será redirecionado para o NGINX e ele irá redirecionar internamente os demais pacotes.
```
echo "127.0.0.1  webserver.com.br" >> /etc/hosts
echo "127.0.0.1  keycloak.com.br" >> /etc/hosts
```

#### Access KeyCloak
Isso vai fazser você cair no container do keyclaok<br/>
Acesse `http://keycloak.com.br`


- Login Admin: `http://keycloak.com.br/auth/admin/master/console/#/realms/master`

Autenticação:<br/>
login:`admin`<br/>
senha `admin`<br/>

1. Clique no Realm >> ADD 
2. Importe o arquivo: `keyclaok-import.json`<br/>

Depois de importar o arquivo JSON que tem os dados do cliente para o NodeJS usar

O KeyCloak vai gerar um REALM chamado `nodejs-example` <br/>
Feito a configuração o NodeJS já está pronto para usar.




#### Acessando a Applicação
`http://webserver.com.br`

Logue com o usuário: `user` com a senha `password`<br/>

### Links

 1. Link do projeto
 https://github.com/keycloak/keycloak-nodejs-connect/tree/master/example

 2. Encode e Decode
https://www.jsonwebtoken.io/ 
