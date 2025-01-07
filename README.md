# Include g_sqlite
Este é um include que adiciona novas funções no samp que facilitam consultas sqlite.

# Instalação

Para utilizar o include, basta baixar o g_sqlite.inc e adicioná-lo em sua pasta de includes, após, inclua-o como outra include (#include), como:
#include <g_sqlite>

# Uso

## Primeiramente, vale lembrar a diferença entre usar a include, usar o sqlite padrão do samp ou usar outra include (como as includes que salvam em .ini).

### 1° Ponto: Salvamento .ini não é estruturado, o que pode tirar a organização, facilidade e até mesmo desempenho do servidor.
### 2° Ponto: As consultas sqlite, podem ser chatas e até difíceis, tanto para quem sabe ou não utiliza-lo.

## Diferenças práticas entre usar a include ou a forma antiga (consulta com o db_query)

### Com o db_query:

```
new Query[90];

format(Query, sizeof Query, "SELECT `id` FROM `player` WHERE nome = '%s' LIMIT 1;", PlayerName(playerid));

new DBResult:result = db_query(dbSQL, Query);

if(db_num_rows(result) > 0)
{

  id = db_get_field_assoc_int(result, "id");

}
```

### Com o g_sqlite:

```
id = GSQL_GetInt("player", "id", "nome", PlayerName(playerid));
```


caso o "id" não exista, a função retorna 0 (lembrando que quando qualquer tabela é criada, é adicionado sempre uma coluna de id com auto increment, ou seja, sempre será maior ou igual a 1)
