# API de games

## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteca voçe vai receber a listagem de todos games
Exemplo de resposta:
```
[
    {
        "id": 1,
        "title": "GTA 6",
        "year": 2025,
        "price": 400
    },
    {
        "id": 2,
        "title": "Down Hill 2",
        "year": 2010,
        "price": 20
    },
    {
        "id": 3,
        "title": "Red dead 2",
        "year": "2038743",
        "price": "500"
    }
]
```

#### Falha na autenticação! 401
caso esssa resposta aconteça, isso significa que ocorreu alguma falha durante o processo de autenticação da requisição. 

Motivos: 
- token inválido
- token expirado

Exemplo de resposta:
```
{
    "err": "token ivalido!"
}
```


### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametros
Email: email do usuário cadastrado no sistema

Password: senha do usuário cadastrado no sistema, com aquele determinado email

Exemplo:
```
{
    "email": "gui@gmail.com",
    "password": "2045"          
}
```

#### Respostas
##### OK! 200
Caso essa resposta aconteca voçe vai receber o token JWT, assim podera acessar os endpoints protegidos na API.
Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MjAsImVtYWlsIjoiZ3VpQGdtYWlsLmNvbSIsImlhdCI6MTcwNjM4ODA0NywiZXhwIjoxNzA2NTYwODQ3fQ.SXsfyTYjV34RsI9MT1UjbqxoIPeD3VKhGTO_i4t9-PM"
}
```

#### Falha na autenticação! 401
caso esssa resposta aconteça, isso significa que ocorreu alguma falha durante o processo de autenticação da requisição. 

Motivos: 
- Senha incorreta ou
- Email incorreto

Exemplo de resposta:
```
{
    "err": "Credenciais inválidas"
}
```

