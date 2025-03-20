# sessionup-pgstore

[![Build status](https://travis-ci.org/jellydator/sessionup-pgstore.svg?branch=master)](https://travis-ci.org/jellydator/sessionup-pgstore)
[![Go Report Card](https://goreportcard.com/badge/github.com/jellydator/sessionup-pgstore)](https://goreportcard.com/report/github.com/jellydator/sessionup-pgstore)
[![GoDoc](https://godoc.org/github.com/jellydator/sessionup-pgstore?status.png)](https://godoc.org/github.com/jellydator/sessionup-pgstore)

PostgreSQL session store implementation for [sessionup](https://github.com/jellydator/sessionup)

## Installation
```
go get github.com/jellydator/sessionup-pgstore
```

## Usage
Create and activate a new PgStore:
```go
db, err := sql.Open("postgres", "...")
if err != nil {
      // handle error
}

store, err := pgstore.New(db, "sessions", time.Minute * 5)
if err != nil {
      // handle error
}

manager := sessionup.NewManager(store)
```
