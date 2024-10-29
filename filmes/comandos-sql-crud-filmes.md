# Comandos SQL para CRUD - Referência

## Resumo

C -> Create (Insere dados)
R -> Read (Ler dados)
U -> Update (Atualizar dados)
D -> Deletar (Excluir dados)

## Insert
### Generos

```sql
INSERT INTO generos (genero) VALUES('Ação');

INSERT INTO generos (genero)
 VALUES('Comédia'),('Terror'),('Ficção'),('Drama');

```

<!-- _____________________________________________ -->

## Insert
### Filmes

```sql
INSERT INTO filmes (titulo, lancamento, genero_id)
 VALUES('Vingadores: Ultimato', 2019, 1);

INSERT INTO filmes (titulo, lancamento, genero_id)
 VALUES('Divertida Mente', 2015, 2);

INSERT INTO filmes (titulo, lancamento, genero_id)
 VALUES('Interstellar', 2014, 4),
 ('Titanic', 1997, 5),
 ('Se beber, Não se case!', 2009, 2),
 ('Albergue', 2005, 3);

<!-- _____________________________________________ -->

```
## Select
### Listar (Leitura)

```sql

-- Lista os filmes de Comédia
SELECT titulo FROM filmes WHERE genero_id = 2 ; -- Comédia

-- Lista por ano lançamento em ordem decrescente
SELECT titulo, lancamento FROM filmes ORDER BY lancamento DESC;

```

<!-- _____________________________________________ -->

## Update
### Atualizar (Obs: Sempre usar Where)

```sql
-- Atualizar o título do filme de id = 1
UPDATE filmes SET titulo = 'Vingadores: Endgame' WHERE id = 1;

-- Atualizar o ano de lançamento do filme titanic para 1998
UPDATE filmes SET lancamento = 1998 WHERE titulo = 'titanic';

```
<!-- _____________________________________________ -->

## Delete
### Excluir (Obs: Sempre usar Where)

```sql

-- Exclui filmes com lançamento antes do ano 2000
DELETE FROM filmes WHERE lancamento < 2000;

```

<!-- _____________________________________________ -->

## Consulta em 2 tabelas diferentes (Junção)

```sql

-- Filmes com seus generos
SELECT filmes.titulo, generos.genero FROM filmes
INNER JOIN generos ON filmes.genero_id = generos.id;

```


