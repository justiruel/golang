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
