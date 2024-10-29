# Comandos SQL - Referência

## Modelagem física

### Criar Banco de dados
```sql

CREATE DATABASE sistema CHARACTER SET utf8mb4;

```

<!-- ___________________________________________ -->

### Criar tabela usuarios
```sql

-- Expressão SQL para criar a tabela de usuários
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL,
    senha VARCHAR(255) NOT NULL
);

```

<!-- ___________________________________________ -->

### Criar tabela fornecedores
```sql

-- Expressão SQL para criar a tabela de fornecedores
CREATE TABLE fornecedores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100),
    telefone VARCHAR(20)
);

``` 

<!-- ___________________________________________ -->

### Criar tabela produtos
```sql

-- Expressão SQL para criar a tabela de produtos relacionada via FK com a tabela de fornecedores
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fornecedor_id INT,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2),
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);

``` 

<!-- ___________________________________________ -->

### Expressão SQL para cadastrar um usuário
```sql

-- Expressão SQL para cadastrar um usuário
INSERT INTO usuarios (usuario, senha) VALUES ('Ignacio', MD5('123'));
INSERT INTO usuarios (usuario, senha) VALUES ('Valmir', MD5('123'));


``` 