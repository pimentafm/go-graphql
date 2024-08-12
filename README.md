## Go GraphQL

[gqlgen](https://gqlgen.com)

* Initialize gqlgen: `go run github.com/99designs/gqlgen init`
* Update schema: `go run github.com/99designs/gqlgen generate`


## GraphQL queries and mutations
```graphql
mutation createCategory {
  createCategory(
    input: {
      name: "Tecnologia",
      description: "Curso de tecnologia"
    }
  ) {
    id,
    name,
    description
  }
}

mutation createCourse {
  createCourse(input: {
    name: "FullCycle",
    description: "Go Expert",
    categoryId: "b8bc8a5b-a5a5-4a30-b02a-e49167db86ab"
  }) {
    id,
    name
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
    Courses {
      id
      name
    }
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

query queryCourses {
  categories {
    id
    name
    description
  }
}

```