# start_game
Solicita um novo jogo ao servidor e cria uma thread para lidar com usuário

## Resposta:
200 <span style="color:lightblue"> (Jogo Iniciado) </span>
```json
{
    "status_code": "200"
}
```

400  <span style="color:lightblue"> (Jogo já iniciado) </span>
```json
{
    "status_code": "400"
}
```

# restart_game
Solicita que o jogo atual seja reiniciado

## Resposta:
205 <span style="color:lightblue"> (Jogo Reiniciado) </span>

```json
{
    "status_code": "205"
}
```
# continue_game

206 <span style="color:lightblue"> (Jogo Continuado) </span>
```json
{
    "status_code": "206"
}
```

# exit_game
Solicita que o jogo atual se encerre

## Resposta:
201 <span style="color:lightblue"> (Jogo Encerrado) </span>
```json
{
    "status_code": "201"
}
```

401  <span style="color:lightblue"> (Jogo não iniciado) </span>
```json
{
    "status_code": "401"
}
```


# check_word
Envia uma palavra para validação no lado do servidor (checando se acertou)

## Requisição:
```json
{
    "word": "palavra"
}
```

## Resposta:
202 <span style="color:lightblue"> (Palavra Correta) </span>
```json
{
    "status_code": "202",
    "attempts": quantidade de tentativas restantes
}
```

203 <span style="color:lightblue"> (Palavra Incorreta) </span>

##### Código das cores:
 - 0: cinza 
 - 1: amarelo
 - 2: verde

```json
{
    "status_code": "203",


    "feedback": [
        {
            "index": 0,
            "modification": 2
        },
        {
            "index": 1,
            "modification": 1
        },
        {
            "index": 2,
            "modification": 1 
        },
        {
            "index": 4,
            "modification": 0
        }
    ],


    "remaining_attempts": quantidade de tentativas restantes

}
```

401  <span style="color:lightblue"> (Jogo não iniciado) </span>
```json
{
    "status_code": 401 
}
```

402 <span style="color:lightblue"> (Necessário Parâmetro) </span>
```json
{
    "status_code": 402, 
    "remaining_attempts": quantidade de tentativas restantes
}
```

403  <span style="color:lightblue"> (Tamanho Incorreto) </span>
```json
{
    "status_code": 403,
    "remaining_attempts": quantidade de tentativas restantes
}
```

404  <span style="color:lightblue"> (Palavra Inexistente) </span>
```json
{
    "status_code": 404, 
    "remaining_attempts": quantidade de tentativas restantes
}
```

405  <span style="color:lightblue"> (Palavra Repetida) </span>
```json
{
    "status_code": 405, 
    "remaining_attempts": quantidade de tentativas restantes
}
```

# list_words

## Resposta:

204 <span style="color:lightblue"> (Lista de Palavras já Digitadas) </span>

```json

{
    "status_code": "204" 
}

```

# BAD REQUEST

499  <span style="color:lightblue"> (Requisição Inválida) </span>
```json
{
    "status_code": 499, 
    "remaining_attempts": quantidade de tentativas restantes
}
```