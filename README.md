![logo](https://user-images.githubusercontent.com/44507419/91507497-616ff400-e8ab-11ea-80e6-c29dfa5da930.png )

# DOCUMENTAÇÃO: API- OCORRÊNCIAS CRIMINAIS
> A documentação foi deita usando o software [Insomnia Code](https://insomnia.rest/).

# Acesso
> Através do [Netlify](https://www.netlify.com/) a documentação e outros dados podem ser acessados através desse link:

[CRIME.DATA](https://crimepontodata.netlify.app/)

# CRIME.DATA
> Segue uma breve parte da documentação, para acessa-lá completa uso o link indicado anteriormente.

## Introdução

A interface de serviços da API público provê uma API REST para efetuar operações e consultas na base de dados sobre Ocorrências Criminais, SINESP - Ministério da Justiça.

A API possui um sistema de autenticação para maior segurança.\n\nAqui você encontrará todas as informações necessárias para integrar seu sistema com a API público, CRIME.DATA.

## Chaves de Acesso

Para conectar-se a API precisará primeiro autenticar-se com:
* __Email__
* __Senha__
Na rota /login, que retornará um:
* __Token__

## Autenticação

Usamos o jwt token como forma de autenticação. Ele deve ser passado como cabeçalho (Header) nas rotas protegidas que necessitam obrigatoriamente dele.
O JSON Web Token é um padrão da Internet para a criação de dados com assinatura opcional e/ou criptografia, cuja sua payload contém o JSON que afirma algum número de declarações.
Mais informações sobre o JSON Web Token poderão ser encontradas no site [jsonwebtoken.io](https://www.jsonwebtoken.io/).

## Formato das Respostas
Todos os recursos suportam o envio de respostas no formato JSON. Para obter a resposta basta enviar uma requisição HTTP.

## Recursos
Abaixo estão listados os recursos disponivéis pela API.

### User

> Recurso responsável por cadastrar e inserir um usuário no banco de dados.

### Login

> Recurso responsável por logar o usuário no sistema e retorná-lo o token de acesso.

### Quantidade de Crimes por Ano

> Este recurso retorna a quantidade de vítimas e ocorrências (independente da especificação dos mesmos) registradas em um dado ano ou todos os disponíveis na base.

* __Parâmetros__

O parâmetro _:ano_ recebe a identificação do ano, por exemplo **2020**. Caso demande a requisição para todos os anos presentes na base de dados, inserir **todos**.

### Quantidade de Ocorrências

> Este recurso retorna a quantidade de crimes notificados em um determinado estado.

* __Parâmetros__

O parâmetro _:sigla_ recebe a identificação do estado, por exemplo **ceara** ou **ce**. Caso demande a requisição para os dados do país inteiro, inserir **bra** ou **brasil**.

O parâmetro _:nomecrime_ recebe a especificação do crime, por exemplo **roubo_veiculo**. Caso demande a requisição para os dados de todos os crimes, inserir **todos**.

### Quantidade de Vítimas

> Este recurso retorna a quantidade de vítimas de um dado crime (ou todos os crimes da base) notificadas em um determinado estado (ou no país inteiro).  

* __Parâmetros__

O parâmetro _:sigla_ recebe a identificação do estado, por exemplo **ceara** ou **ce**. Caso demande a requisição para os dados do país inteiro, inserir **bra** ou **brasil**.

O parâmetro _:nomecrime_ recebe a especificação do crime, por exemplo **homicidio_doloso**. Caso demande a requisição para os dados de todos os crimes, inserir **todos**.

### Média de Ocorrências

> Este recurso retorna a média mensal de ocorrências de um crime em determinado período de tempo.

* __Parâmetros__

O parâmetro _:sigla_ recebe a identificação do estado, por exemplo **ceara** ou **ce**. Caso demande a requisição para os dados do país inteiro, inserir **bra** ou **brasil**.

O parâmetro _:nomecrime_ recebe a especificação do crime, por exemplo **roubo_veiculo**. Caso demande a requisição para os dados de todos os crimes, inserir **todos**.

Os parâmetros _início_ e _fim_ recebem uma data de início e fim para o cálculo da média dentro daquele intervalo.

### Média de Vítimas

> Este recurso retorna a média mensal de vítimas de um crime em determinado período de tempo.

* __Parâmetros__

O parâmetro _:sigla_ recebe a identificação do estado, por exemplo **ceara** ou **ce**. Caso demande a requisição para os dados do país inteiro, inserir **bra** ou **brasil**.

O parâmetro _:nomecrime_ recebe a especificação do crime, por exemplo **homicidio_doloso**. Caso demande a requisição para os dados de todos os crimes, inserir **todos**.

Os parâmetros _início_ e _fim_ recebem uma data de início e fim para o cálculo da média dentro daquele intervalo.

### Ranking Estadual por Crime

> Este recurso retorna o ranking de estados que apresentam uma maior ocorrência de determinado crime.

* __Parâmetros__

O parâmetro _:quantidade_ recebe um valor inteiro, por exemplo **10**. Determina a quantidade de elementos que devem aparecer no ranking. Caso demande a requisição para todos os estados, inserir **27**.

O parâmetro _:nomecrime_ recebe a especificação do crime, por exemplo **roubo_veiculo**. Caso demande a requisição para os dados de todos os crimes, inserir **todos**.

### Ranking Criminal por Estado
> Este recurso retorna o ranking de crimes que apresentam uma maior ocorrência em um dado estado (ou no país inteiro).

* __Parâmetros__

O parâmetro _:quantidade_ recebe um valor inteiro, por exemplo **10**. Determina a quantidade de elementos que devem aparecer no ranking. Caso demande a requisição para todos os crimes, inserir **todos**.

O parâmetro _:sigla_ recebe a especificação do estado, por exemplo **ceara** ou **ce**.  Caso demande a requisição para os dados do país inteiro, inserir **bra** ou **brasil**.

