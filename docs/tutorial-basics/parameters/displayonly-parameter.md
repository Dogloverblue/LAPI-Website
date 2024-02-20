# displayonly Parameter

The displayonly parameter is used for when you want only a specific selection of columns to be returned. e.g. only returning the name of each card

Syntax: `displayonly=<column name 1>;<column name 2>;<column name 3>;...`

## Usage

To use the displayonly parameter, put the parameter key `displayonly=` followed by a semi-colon-seperated list of the columns you wish to be returned. It should look something like this:
```javascript
displayonly=name;cost;set_num
```

This clause will change a response that look like this:
```JSON
[
  {
    "Artist": "Nicholas Kole",
    "Set_Name": "The First Chapter",
    "Classifications": "Dreamborn, Hero, Queen, Sorcerer",
    "Set_Num": 1,
    "Color": "Amethyst",
    "Image": "https://lorcana-api.com/images/elsa/snow_queen/elsa-snow_queen-large.png",
    "Cost": 3,
    "Inkable": true,
    "Name": "Elsa - Snow Queen",
    "Type": "Character",
    "Lore": 1,
    "Rarity": "Uncommon",
    "Flavor_Text": "Recreated by magical ink, Elsa found herself in an entirely new world. Fortunately, ice works the same way everywhere.",
    "Card_Num": 41,
    "Body_Text": "Freeze -{e} - Exert chosen opposing character.",
    "Willpower": 3,
    "Strength": 2,
    "Set_ID": "TFC"
  }
]
```
to this:
```JSON
    [
  {
    "Set_Num": 1,
    "Cost": 3,
    "Name": "Elsa - Snow Queen"
  }
]
```