# golang dotenv
<a href="https://github.com/goapt/dotenv/actions"><img src="https://github.com/goapt/dotenv/workflows/build/badge.svg" alt="Build Status"></a>

## Usage

Add your application configuration to your .env file in the root of your project:
```shell script
S3_BUCKET=YOURS3BUCKET
SECRET_KEY=YOURSECRETKEYGOESHERE
```
Then in your Go app you can do something like

```go
package main

import (
    "log"
    "os"

    "github.com/goapt/dotenv"
)

func main() {
  err := dotenv.Load()
  if err != nil {
    log.Fatal("Error loading .env file")
  }

  s3Bucket := os.Getenv("S3_BUCKET")
  secretKey := os.Getenv("SECRET_KEY")

  // now do something with s3 or whatever
}
```

## Thanks

https://github.com/joho/godotenv
