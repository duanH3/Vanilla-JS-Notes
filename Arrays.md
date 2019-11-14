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

Get the name/price only in the array
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
```

# Find

Returns true and/or the very first item it find in the array 

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


