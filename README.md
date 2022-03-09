<h1 align="center">graphql-go</h1>
<p align="center">This is a POC (proof of concept) to understand better the behavior of graphQL with Go Lang.</p>


### Technologies:

* Go (https://golang.org/);
  * https://go.dev/ref/spec
* gqlgen - v0.13.0
  * https://gqlgen.com/

### How to get stated
#### Initialize Go module and dependecies
```console
bscpaz@2am:$ go mod init github.com/bscpaz/graphql-go
bscpaz@2am:$ go get github.com/99designs/gqlgen
```
#### Generete your own models (*.graphql files) into 'graph' folder and then...
```console
bscpaz@2am:$ go run github.com/99designs/gqlgen init
```

### Concepts of graphQL

#### File 'resolver.go'
It serves as dependency injection for your app. A kind of a datasource or a repositories provider of your application.
In this POC, we just use arrays.

#### File 'schema.resolvers.go'
This is a kind of service (or controller) implementation which you code queries, inserts, updates functions of your schemas files.

### Exemple of inputs

```console
query findCategories {
  categories {
    id
    name
    description
    courses {
      name
    }
  }  
}
```

```console
mutation createCategory {
  createCategory(input: {
    name:"Programming language",
    description: "Programming languages are one kind of computer language"
  }) {
    id
    name
    description
  }
}
```
<hr>
<h4 align="center">Known issues</h4>

```console
After running "go run github.com/99designs/gqlgen init"...
issue:
  missing go.sum entry for module providing package
solution:
  go mod tidy
  go get github.com/99designs/gqlgen
```

```console
After running "go run github.com/99designs/gqlgen init"...
issue:
  graph/schema.graphqls already exists
  exit status 1
solution:
  go mod tidy
  go get github.com/99designs/gqlgen@v0.13.0
  go run github.com/99designs/gqlgen init
```
