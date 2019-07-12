# URUTAN INSTALASI
## Download dan instalasi Golang
## setting GOPATH => untuk menyimpan librari dan binaries file
## ngoding harus dalam gopath, kalau menggunakan gomod maka enggak harus dalam gopath



## download library
```
go get github.com/bxcodec/gomodmultiplies/v2
```
## remove library yang di download dengan "go get"
```
go clean -i -x github.com/bxcodec/gomodmultiplies/v2
```
```
remove manual folder $GOPATH/src/github.com/bxcodec/gomodmultiplies
```

## Go Module
#### ref, https://medium.com/easyread/mencoba-go-module-pada-golang-13ae343ce529
#### catatan, jika golang enggak support go mod maka upgrade dengan versi terbaru
Guna : dengan menerapkan go mod, maka proyek enggak harus ditaruh gopath dapat di runing serta dapat mengakses library pada folder C:\Users\user\go\pkg\mod

```
cd github.com/justiruel/myproyek
```
Jalankan
```
go mod init github.com/justiruel/myproyek
```
contoh main.go
```
package main
import (
 "fmt"
 "github.com/bxcodec/gomodmultiplies/v2"
)
func main() {
 a, b := int64(10), int64(23)
 res := gomodmultiplies.Multiply(a, b)
 fmt.Println(res)
}
```
- jalankan main.go => "go run main.go", maka library yang required akan otomatis terdownload ke C:\Users\user\go\pkg\mod, selanjutnya main.go bisa dijalankan difolder manapun (enggak harus di gopath)
Open go.mod, perhatikan semua required library (github.com/bxcodec/gomodmultiplies/v2) otomatis akan  tercatat di sini
```
module github.com/justiruel/myproyek

require (
	github.com/bxcodec/gomodmultiplies/v2 v2.0.0
)

go 1.12
```
# menggunakan library echo-gorm 
- Download echo
```
go get -u github.com/labstack/echo/...
```
- Download https://github.com/markpenaranda/echo-gorm

# menggunakan swagger pada echo-gorm
- Tutorial https://github.com/swaggo/echo-swagger
- rename echo-gorm/server.go => echo-gorm/main.go 
- jika ada error "Can't use with echo/v4" open $GOPATH/github.com/swaggo/echo-swagger/swagger.go (atau jika menggunakan gomod C:/Users/user/go/pkg/mod/github.com/swaggo/echo-swagger/swagger.go) rename "github.com/labstack/echo/v4" ke "github.com/labstack/echo"
- contoh penerapan D:\PROJECT\RISET\GO\revel\src\echo-gorm>

# JWT
- https://echo.labstack.com/cookbook/jwt
- https://www.naimibrahim.me/2018/11/20/echo-framework-gorm-blazing-fast-golang-server-side-application-authentication-example/

# CronJob
- github.com/jasonlvhit/gocron
- contoh
```
package main
import (
    "fmt"
    "github.com/jasonlvhit/gocron"
)

func task() {
    fmt.Println("Task is being performed.")
}

func main() {
    s := gocron.NewScheduler()
    s.Every(2).Hours().Do(task)
    <- s.Start()
}
```
