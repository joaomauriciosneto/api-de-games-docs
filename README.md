# API de Games
Esta API é utilizada para testar login com credenciais.
## Endpoints

### GET /games
Esta rota lista todos os games cadastrados.
#### Parâmetros
Nenhum
#### Respostas
##### Ok! 200
Caso está resposta aconteça você vai receber a listagem de todos os games.

>Exemplo
```
[
    {
        "id": 23,
        "title": "God of War",
        "year": 2015,
        "price": 150
    },
    {
        "id": 3,
        "title": "Hero Siege",
        "year": 2015,
        "price": 15
    },
    {
        "id": 123,
        "title": "Terraria",
        "year": "2000",
        "price": "10"
    }
]

```
##### Falha na autenticação! 401
Caso essa resposta acontecça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.

>Exemplo:
```
{
    "error": "Token inválido!"
}

```

### POST /auth
Esta rota é responsável por fazer o processo de `login`.
#### Parâmetros
`email`: E-mail do usuário cadastrado no sistema.

`password`: Senha do usuário cadastrado no sistema, com aquele determinado email.

>Exemplo:
```
{
    "email": "xuxu@x.com",
    "password": "123"
}
```
#### Respostas
##### Ok! 200
Caso está resposta aconteça você vai receber o token *JWT* para conseguir acessar endpoints protegidos na API.

>Exemplo:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTAsImVtYWlsIjoieHV4dUB4LmNvbSIsImlhdCI6MTcyMTA4MTMxMywiZXhwIjoxNzIxMjU0MTEzfQ.bbF8RKlAVW6nouvsyJlNoL32Vx7Sag4ZENKAXJVEc5w"
}

```
##### Falha na autenticação! 401
Caso essa resposta acontecça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.

- Motivos: Senha ou e-mail incorretos.

>Exemplo:
```
{ error: "credenciais inválidas" }

```
