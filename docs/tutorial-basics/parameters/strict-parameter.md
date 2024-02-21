# Strict Parameter

The strict parameter is used for when you have the exact name match of one or more cards.

Syntax: `strict=name1;name2;name3;etc`

## Usage

Using the strict parameter is simple, all you have to do is provide a semicolon-seperated list of the names of the cards you want to fetch. It should look something like this:
```javascript
strict=dragon gem;elsa - snow queen;freeze
```
[See how this looks](https://api.lorcana-api.com/cards/fetch?strict=dragon%20gem;elsa%20-%20snow%20queen;freeze)

Remember that for characters, their name and subtitle are seperated by a " - ", so make sure to format that correctly. Admittedly, that system is a little silly, and is subject to change.
