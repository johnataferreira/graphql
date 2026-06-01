# Título

Projeto para subir uma aplicação em GO para simular algumas consultas utilizando o Graphql.

Projeto base: https://gqlgen.com/

# Rodando projeto

Execute dentro da pasta cmd/server: go run server.go

Acessar localhost:8080

# Banco de dados

Foram criadas duas tabelas para essa aplicação, uma de categorias e uma de cursos

CREATE TABLE categories (id string, name string, description string);

CREATE TABLE courses (id string, name string, description string, category_id string);