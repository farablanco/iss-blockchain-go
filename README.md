
### Get Golang Web middleware - GIN
* Install GIN library to your project home directory, further feature please refer to GIN documentation (https://github.com/gin-gonic/gin)

```
go get github.com/gin-gonic/gin
```

### Get Golang Websocket - GORILLA
* Install GORILLA libary to your project home directory, further feature please refer to GORILLA documentation (http://www.gorillatoolkit.org/pkg/websocket)

```
go get github.com/gorilla/websocket
```


### Utilities required
install gomon (https://github.com/johannesboyne/gomon)

```
npm install -g go-mon
```

### How to start the blockchain app

Go to your terminal and execute the following either one of the command line

```
gomon blockchain.go
```

alternatively 

```
go run blockchain.go
```

### Node synchornization using client server rather p2p
```
go run blockchain.go -h localhost:300
go run blockchain.go -h localhost:3002 -d localhost:3001
```


### Testing

Launch postman to test the following end point 

* GET http://localhost:3005/blocks
* GET http://localhost:3005/is-chain-valid
* POST http://localhost:3005/pay

Payload for the above POST

```
{
	"From": "Bala",
	"To": "Chuk",
	"Amount": 500
}
```


### Golang Notes

* short variable declaration := 
* Appending to a slice
⋅⋅⋅ func append(s []T, vs ...T) []T
* Go has pointers. A pointer holds the memory address of a value.

>The type *T is a pointer to a T value. Its zero value is nil.
```
var p *int
```
>The & operator generates a pointer to its operand.

```
i := 42
p = &i
```
>The * operator denotes the pointer's underlying value.

```
fmt.Println(*p) // read i through the pointer p
*p = 21         // set i through the pointer p
```
>This is known as "dereferencing" or "indirecting".

>Unlike C, Go has no pointer arithmetic.

* sprintf is string formatting

* Format use for time.Time parsing RFC3339     = "2006-01-02T15:04:05Z07:00"

* For each read we pick a key to access, Lock() the mutex to ensure exclusive access to the state, read the value at the chosen key, Unlock() the mutex, and increment the readOps count.
Wait a bit between reads.