# Comandos SQL - Referência

## Modelagem física

### Criar Banco de dados
```sql

CREATE DATABASE filmes CHARACTER SET utf8mb4;

```

<!-- ___________________________________________ -->

### Criar tabela generos
```sql

CREATE TABLE generos (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    genero VARCHAR(45) NOT NULL
)

```

<!-- ___________________________________________ -->

### Criar tabela filmes
```sql

CREATE TABLE filmes (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(45) NOT NULL,
    lancamento YEAR NOT NULL,
    genero_id INT NOT NULL
)

``` 

<!-- ___________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)
```sql
ALTER TABLE filmes
    ADD CONSTRAINT fk_filmes_generos
    FOREIGN KEY (genero_id) REFERENCES generos(id);


``` 