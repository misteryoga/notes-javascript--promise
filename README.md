# Promise
(Janji) Object yg mempresentasikan state di bawah ini:
- Pending (sedang proses)
- Fulfilled (berhasil)
- Rejected (gagal)

## Perbedaan Promise dan Object
- Callback == function || Promise == object
- Callback dikirim via parameter || promise mengembalikan object
- Callback digunakan untuk beberapa event sekaligus || promise hanya untuk 1 event

## Create Promise
```
let janjian = new Promise();
console.log(janjian)

// output = Promise{<pending>}
```
### bagaimana mengatur state fulfilled / rejected ?
```
let janjian = new Promise((resolve, reject) => {
  if(true){
    resolve('berhasil);
  }else {
    reject(new Error('batal janji))
  }
  
});

janjian
  .then((result) => {
    console.log(result)
  })
  .catch((error) => {
    console.log(error)
  })
```

## Request Ajax dgn Fetch (request Chaining)
```
  fetch("https://jsonplaceholder.typicode.com/users/1")
    .then(function(response){
      return response.json();
    })
    .then(function(user) {
      console.log(user)
    })
```
## Promise Chainig
```
var a = new Promise(function(resolve, reject){
  setTimeout(function(){
      if(false) {
        resolve('resolve a')
      }else{
        reject(new Error('reject a'))
      }
  }, 2000)
})

a.then(function(value){
  return value +" is true" 
}).then(function(value){
  console.log(value)
})
```
## promise all
Menggabungkan lebih dari 1 Promise ke dalam bentruk array
```
  var a = new Promise(function(resolve, reject){
    setTimeout(function(){
        if(true) {
          resolve('resolve a')
        }else{
          reject('reject a')
        }
    }, 2000)
  })

  var b = new Promise(function(resolve, reject){
    setTimeout(function(){
        if(true) {
          resolve('resolve b')
        }else{
          reject('reject b')
        }
    }, 5000)
  })

  Promise.all([a, b]).then(value => {
    console.log(value)
  })
```