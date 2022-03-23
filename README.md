# FakeAPI-Capstone

Esse é o repositório feito para ser usado no desenvolvimento no Capstone do M3, do grupo 3 do facilitador Vilson.

### URL: https://apifake-capstone-m3.herokuapp.com/

## USUÁRIO JÁ CADASTRADO

{
"email": "vilson@mail.com",
"password": "123456"
}

## ENDPOINTS

# /USERS

Endpoint para ser utilizado no gerencimento de usuários, como um POST para cadastro, PATCH para alterações e GET para busca.

## Formato POST

{
"email": "exemplo@mail.com",
"password": "exemplo",
"name": "exemplo exemplo",
"userName": "exemplo",
"biography": "Exemplo exemplo.",
"img": "https://exemplo.com",
"note": null
}

## Resposta exemplo

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imd1Z3VAbWFpbC5jb20iLCJpYXQiOjE2NDY3ODE0NjIsImV4cCI6MTY0Njc4NTA2Miwic3ViIjoiMiJ9.ALsEehQDwx0CA03nz1qc_G47S0StiNYp_tbvH1YhC2w",

"user": {
"email": "exemplo@mail.com",
"name": "exemplo exemplo",
"userName": "exemplo",
"biography": "Exemplo exemplo.",
"img": "https://exemplo.com",
"note": null
"id": 1
}
}

## Formato PATCH

/USERS/ID

Necessita de Autentificação do token.

{
"name": "Novo exemplo"
}

## Resposta exemplo

{
"email": "exemplo@mail.com",
"password": "$2a$10$gOyntRCklbSAErf5fJlSkuughTOL8YAUoN507gV/hHkZgNtbAKAUm",
"name": "Novo exemplo",
"userName": "exemplo",
"biography": "Exemplo exemplo.",
"img": "https://exemplo.com",
"note": null
"id": 1
}

## GET /USERS

Retorna todos os users cadastrados

## GET /USERS/ID

Retorna um user

## GET /USERS/ID/POSTS

Retorna todos os posts de um user

# /LOGIN

POST

Endpoint para um que um usuário com cadastro feito possa logar em sua conta e assim criar seus posts.

## Formato

{
"email": "exemplo@mail.com",
"password": "exemplo",
}

## Resposta exemplo

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imd1Z3VAbWFpbC5jb20iLCJpYXQiOjE2NDY3ODE0NjIsImV4cCI6MTY0Njc4NTA2Miwic3ViIjoiMiJ9.ALsEehQDwx0CA03nz1qc_G47S0StiNYp_tbvH1YhC2w",

"user": {
"email": "exemplo@mail.com",
"name": "exemplo exemplo",
"userName": "exemplo",
"biography": "Exemplo exemplo.",
"img": "https://exemplo.com",
"note": null,
"id": 1
}
}

# /POSTS

Endpoint para gerenciamento dos posts que seram feitos pelos usuários, POST para registrar, GET para buscar, PATCH para alterar e DELETE para deletar.

## Formato POST

Necessita de Autentificação do token.

{
"title": "Exemplo",
"text": "Exemplo exemplo exemplo",
"font": "www.font",
"theme": "Tema",
"date": "Date",
"primaryImage": "Image_exemplo.png",
"secondaryImages": ["Image_exemplo1.png", "Image_exemplo2.png"],
"votes": [],
"media": null,
"userId": id do user (número)
}

## Resposta exemplo

{
"title": "Exemplo",
"text": "Exemplo exemplo exemplo",
"font": "www.font",
"theme": "Tema",
"date": "Date",
"primaryImage": "Image_exemplo.png",
"secondaryImages": ["Image_exemplo1.png", "Image_exemplo2.png"],
"votes": [],
"media": null,
"userId": 1,
"id": 1
}

## Formato PATCH

/POSTS/ID

Necessita de Autentificação do token.

{
"font": ""www.Newfont",
"date": "NewDate"
}

## Resposta exemplo

{
"title": "Exemplo",
"text": "Exemplo exemplo exemplo",
"font": "www.Newfont",
"theme": "Tema",
"date": "NewDate",
"primaryImage": "Image_exemplo.png",
"secondaryImages": ["Image_exemplo1.png", "Image_exemplo2.png"],
"votes": [],
"media": null,
"userId": 1,
"id": 1,
}

## GET /POSTS

Retorna todos os posts registrados

## GET /POSTS/ID

Retorna um post

## DELETE /POSTS/ID

Necessita de Autentificação do token

Deleta um post

# /ACCEPT

Endpoint onde irão os posts para serem aceitos pelo administrador, POST para registrar, GET para buscar e DELETE para deletar.

## Formato POST

Necessita de Autentificação do token.

{
"title": "Exemplo",
"text": "Exemplo exemplo exemplo",
"font": "www.font",
"theme": "Tema",
"date": "Date",
"primaryImage": "Image_exemplo.png",
"secondaryImages": ["Image_exemplo1.png", "Image_exemplo2.png"],
"votes": [],
"media": null,
"userId": id do user (número)
}

## Resposta exemplo

{
"title": "Exemplo",
"text": "Exemplo exemplo exemplo",
"font": "www.font",
"theme": "Tema",
"date": "Date",
"primaryImage": "Image_exemplo.png",
"secondaryImages": ["Image_exemplo1.png", "Image_exemplo2.png"],
"votes": [],
"media": null,
"userId": 1,
"id": 1
}

## GET /ACCEPT

Necessita de Autentificação do token.

Retorna todos os posts a serem aceitados

## GET /ACCEPT/ID

Retorna um post a ser aceitado

## DELETE /ACCEPT/ID

Necessita de Autentificação do token

Deleta um post a ser aceitado
