<h1 align="center">graphql-go</h1>
<p align="center">This is a POC (proof of concept) to understand better the behavior of graphQL with Go Lang.</p>


### Technologies:

* Go (https://golang.org/);
  * https://go.dev/ref/spec
* gqlgen
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

<hr>
<h4 align="center">Known issues</h4>

```console
After running "go run github.com/99designs/gqlgen init"...
issue:
  missing go.sum entry for module providing package
solution:
  bscpaz@2am:$ go mod tidy
  bscpaz@2am:$ go get github.com/99designs/gqlgen
```

```console
After running "go run github.com/99designs/gqlgen init"...
issue:
  graph/schema.graphqls already exists
  exit status 1
solution:

```
