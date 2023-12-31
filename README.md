# API de Games
- Esta API foi desenvolvida para consolidar os conhecimentos sobre os verbos HTTP.
- Utilização da biblioteca Axios para consumir a API Rest.
- Realizar a Autenticação com JWT.

## Endpoints

### GET /jogos/:id
Esse endpoint é responsável por retornar a listagem de todos os jogos cadastrados no banco de dados com aquele id informado.

#### Parametros
ID do jogo solicitado.

#### Respostas
##### OK! 200
Caso essa resposta aconteça, você vai recebar a listagem de todos os jogos com base no ID informado.
Exemplo de resposta:
```

jogos: 
    [
        {
            id: 5,
            titulo: "Minecraft", 
            ano: 2005,
            preco: 362
        }
    ]
```


### GET /jogos
Esse endpoint é responsável por retornar a listagem de todos os jogos cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai recebar a listagem de todos os games.

Exemplo de resposta:
```

jogos: 
    [
        {
            id: 5,
            titulo: "Minecraft", 
            ano: 2005,
            preco: 362
        },
        {
            id: 10,
            titulo: "FIFA 2020", 
            ano: 2020,
            preco: 346
        },
        {
            id: 15,
            titulo: "GTA V", 
            ano: 2015,
            preco: 556
        }
    
    ]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token inválido!"
}
```

### POST /autenticacao
Esse endpoint é responsável por retornar fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
	"email": "victordevtb@guiadoprogramador.com",
	"password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JkZXZ0YkBndWlhZG9wcm9ncmFtYWRvci5jb20iLCJpYXQiOjE1OTE3ODI0NzUsImV4cCI6MTU5MTk1NTI3NX0.y8kp3BxKgC86KFiq6-tAABukR6vi1guTPeRQhO8IdwU"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:
```
{err: "Credenciais inválidas!"}
```
