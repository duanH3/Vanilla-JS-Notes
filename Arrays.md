# Filter

Filter items with specific price range

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:100 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const filteredItems = items.filter(() => {
  return item.price <=100
})
```

# Map

Returns new array of the name/price only

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:100 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const itemNames = items.map(() => {
  return item.name  // or item.price
})

//expected reuslt [200, 100, 20, 30, 50]
```

# Includes

The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.

```
const items = [1, 2, 3, 4, 5, 6, 7]

const includesNum = items.includes(5)

console.log(includesNum); // true
```

# Find

The find() method returns the value of the first element in the provided array that satisfies the provided testing function.

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:100 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const findItem = items.find((item) => {
  return item.name === 'PMD'
})

// expected result  {name: "PMD", price: 200}
```

# foreach

loop through every items

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:100 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

items.forEach((item) => {
  console.log(item.name)
})
```

# Some

Similar to any(), Return true or false if conditions are met

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:110 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const hasExpensiveItems = items.some((item) => {
    return item.price >= 100   //returns true
})
```

# Every

Similar to some(), but it checks every item. Return true or false if conditions are met
```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:110 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const hasExpensiveItems = items.every((item) => {
    return item.price >= 1000   //returns false
})
```
# Reduce

The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value

```
const items = [
{ name: 'PMD',		price:200 },
{ name: 'Bysycle',	price:110 },
{ name: 'Roller Skate',	price:20 },
{ name: 'Roller Blade',	price:30 },
{ name: 'Shoe',		price:50 }
]

const total= items.reduce((currentTotal, item) => {
  return item.price + currentTotal
}, 0)   //initial value for currentTotal set to 0

console.log(total)  //410
```



