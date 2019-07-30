## ref => https://www.youtube.com/watch?v=OcjMi9cXItY

## kelebihan gomicro
rpc => untuk internal request lebih cepat karena passing byte data kalau rest kan string
service discovery dan load balancing lebih mudah karena integrated, tanpa gomikro registry ke consul ruwet (json post via rest) 
pembagain per service nya enak


## Instalasi
https://micro.mu/docs/go-micro.html

## running consul
```
consul agent -dev
```

## running + register ke consul
```
go run server.go -registry=consul
```

## compile proto
```
protoc --micro_out=. --go_out=. path/to/greeter.proto
```

## call rpc 
```
https://micro.mu/docs/cli.html
micro call greeter Greeter.Hello '{"name":"john"}'  ----> jalankan di console linux
```
## call rpc via web gui
```
micro web
```

## cara akses
```
format =>
[host]:[port]/[****servicename]/[****lowercase(nama fungsi pada api.go)]

contoh =>
http://localhost:8080/v1/bebas/greeter/hello?name=john

penjelasan =>
****servicename => misal nama service api "go.micro.api.v1.bebas" maka  => [host]:[port]/v1/bebas/[****lowercase(nama fungsi pada api.go)]
****lowercase(nama fungsi pada api.go) => misal nama fungsinya sama dengan word terakhir api service name "bebas()" maka enggak usah ditulis, contoh =>
										  [host]:[port]/v1/bebas bukan [host]:[port]/v1/bebas/bebas 
```

## jika antara api.go serta server.go beda server maka yang penting semua konek ke consul maka service discovery yang akan mengurusi, api.go hanya butuh define nama service nya saja
  
#### nanya :

health check
nanya otentikasi
middleware 
redis

```
curl -d 'service=greeter' \
     -d 'method=Greeter.Hello' \
     -d 'request={"name": "John"}' \
     http://localhost:8080/rpc
```	 
	 
	 
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"name": "John"}' \
 http://localhost:8080/v1/hello
