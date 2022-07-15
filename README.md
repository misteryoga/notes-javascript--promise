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
## promise all
## promise in looping
## promise race