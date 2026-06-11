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

# Querys utilizadas em localhost

```
mutation createCategory {
  createCategory(
    input: { 
      name: "Tecnologia", 
      description: "Cursos de Tecnologia"
    }
  ) {
    id 
    name
    description
  }
}

mutation createCourse {
  createCourse (
    input : {
      name: "Full Cycle", 
      description: "The best",
      categoryID: "a5c52c8b-8b5d-4348-8533-27adf82636ac"
    }
  ) {
    id
    name
    description
  }
}

query queryCategories {
  categories {
    id
    name
    description
  }
}

query queryCategoriesWithCourses {
  categories {
    id
    name
    description
    courses {
      id
      name
      description
    }
  }
}

query queryCourses {
  courses {
    id
    name
    description
  }
}

query queryCoursesWithCategory {
  courses {
    id
    name
    description
    category {
      id
      name
      description
    }
  }
}
```