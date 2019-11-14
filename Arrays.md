# Filter

Filter items with specific price range

```
const items = [
{ name: 'PMD',		price:100 },
{ name: 'Bysycle',	price:100 },
{ name: 'Roller Skate',	price:100 },
{ name: 'Roller Blade',	price:100 },
{ name: 'Shoe',		price:100 }
]

const filteredItems = items.filter(() => {
  return item.price <=100
})
```
