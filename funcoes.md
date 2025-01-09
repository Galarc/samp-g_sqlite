## Aqui você encontrará todas as funções do g_sqlite e suas explicações

```
GSQL_TableExists(const table[]);
```
### Esta função serve para verificar se uma tabela existe ou não na database do sqlite (não tem muita utilidade para quem vai usar o sqlite, porém ela é usada pelo gsql).
### Utilização: basta usar o argumento 1 como o nome da tabela, por exemplo GSQL_TableExists("player");, verifica se a tabela player é existente
### Retorna true ou false (true caso exista, false caso não)

```
GSQL_ColumnExists(const table[], const column[])
```

### Esta função verifica se uma coluna foi criada ou não em uma tabela especifica na database (utilizada mais pelo gsql)
### Utilização: use o argumento 1 como o nome da tabela e o argumento 2 como o nome da coluna, por exemplo GSQL_ColumnExists("player", "id");, verifica se a coluna id na tabela player existe
### Retorna true ou false (true caso exista, false caso não)
