# Contoh dasar
```
package main //main berarti ini adalah package executable, bukan package helper
//nama package selain main akan menjadi package nonexetutable/dependency/helper
import "fmt"

//nama func harus sama dengan nama package
func main() {
	//var card string = "Ace of Spades"
	card := "Ace of spades"
	card = "five of diamond"
	fmt.Println(card)

}
```

# :=
':=' digunakan untuk mempersingkat deklarasi sekaligus inisialisasi
contoh 
```
var card string = "Ace of Spades"
```
dapat ditulis dengan 
```
card := "Ace of spades"
```

# Semua variable yang dideklarasi harus digunakan
di GO semua variable yang dideklarasi harus digunakan jika tidak maka akan error<br/>
untuk meng-ignore/mengabaikan variable maka gunakan "_" <br/>
contoh :
```
for index, card := range d {
	fmt.Println(index, card)
}
```
pada code diatas jika ingin mengabaikan index lakukan seperti ini 
```
for _, card := range d {
	fmt.Println(card)
}
```
maka index tidak perlu di println

# ARRAY vs SLICE
Array : fixed length list of things
Slice : an array that can grow or shrink

# Akses Slice
```
dataku[StartIndexIncluding:upToIndexNotIncluding]
```

contoh 
```
dataku := []string{"satu", "dua", "tiga", "empat", "lima"}
fmt.Println(dataku[2:3])

//return
//["tiga"]
```
cara bacanya : start dari index 2 ("tiga"), dan index 2 ("tiga") termasuk  yang di ambil, sampai index 3 ("empat") dan index 4 tidak termasuk yang diambil 

# generic data type function?
