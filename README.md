# go-logging

Logging utility. Control verbosity using an environment variable.

## Import

```
go get github.com/nu12/go-logging
```

## Usage

```go
package main

import "github.com/nu12/go-logging"

func main(){
    var log = logging.NewLogger()

    log.Debug("To print this line, set VERBOSITY to 4")
    
    log.Info("To print this line, set VERBOSITY to 3 or higher")

    log.Warning("To print this line, set VERBOSITY to 2 or higher")

    log.Error(errors.New("To print this line, set VERBOSITY to 1 or higher"))

    log.Fatal(errors.New("This will exit the program with code 1"))
}

```

If `VERBOSITY` is not provided as an environment variable `Info` is used by default. All logs with the corresponding verbosity and lower will be printed.

Note that `log.Error` and `log.Fatal` receive an error as argument. The last also terminates the program with exit code 1.