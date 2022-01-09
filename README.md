Execute playground

```zsh
go run server.go
```

Example

```console
igor@Igor:~$ go run server.go
2022/01/09 13:47:00 connect to http://localhost:8080/ for GraphQL playground
```

mutations and queries

```js
query findCategory {
  categories {
    id
    name
    description
    courses {
      name
    }
  }
}

query findCourses {
  courses {
    id
    name
    description
    chapters {
      name
    }
    category {
      name
    }
  }
}

mutation createCategory {
  createCategory(input: { name: "PHP", description: "PHP is awsome" }) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(
    input: {
      name: "Evolving with PHP"
      description: "Mega PHP is awsome"
      categoryId: "T5577006791947779410"
    }
  ) {
    id
    name
    description
    category {
      id
      name
    }
  }
}

mutation createChapter {
  createChapter(
    input: {
      name: "Evolving PHP - Chapter 1"
      courseId: "T8674665223082153551"
    }
  ) {
    id
    name
    course {
      name
    }
  }
}
```
