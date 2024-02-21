# Search Parameter

The search parameter is the most complex and most powerful parameter avaliable; It allows for very specific and precise filtering of cards based off one or many of thier given traits. It also allows for searching for numbers within a range, OR & AND expressions, and order of operations using parerthesis.

Syntax: `search=key1=value1;key2=value2;key3=value3...`

### Basic Fetching

The most basic method of fetching card using the search parameters is getting all cards with one value equal to a specific value, like having an ink cost equal to 3. To do so, you put the name of the column (or 'key') you want to compare, followed by an equal sign, followered by the value you want it to be. 

Kind of like this: `search?cost=3`
Or in a full URL, it might look like this: `api.lorcana-api.com/cards/fetch?search=cost=3`

This will return a list of all of the cards that have a ink cost of 3! [See for yourself!](https://api.lorcana-api.com/cards/fetch?serch=cost=3)

#### Number comparison

Building off the previous example, lets say you instead wanted to get all the cards that have an ink cost greater than or equal to 3, lets learn how to do that.

For comparing numbers, you can use many inequality signs to further narrow down your search. You can use things like `>`, `<`, `>=`, or `<=`.

Now the parameter is going to look something like this: `search=cost>=3`

### Multiple Column Comparison

The search parameter allows you to do more than just comparing one value to one other value, you can do several at the same time! To do so, seperate each clase with a semicolon, these will act as your AND operators. 
It could look something like this: 
```javascript
search=cost>=3;color=ruby
```
[See how this looks](https://api.lorcana-api.com/cards/fetch?search=cost%3E%3D3%3Bcolor%3Druby)

Now we get all of the cards which are ruby have an ink cost greater than 3!

#### OR operators

We've already learned how to combine multiple conditions together and get cards that meet all of the criteria, but what about those that only follow some? This is where our OR operators come in. To denote an OR operation instead of an AND, use a `;|` instead of a `;`. This will tell the system to return a card if it meets atleast of those criteria. 
Our URL should now look something like this:
```javascript
search=cost>=3;|color=ruby
```
[See how this looks](https://api.lorcana-api.com/cards/fetch?search=%3Dcost%3E%3D3%3B%7Ccolor%3Druby)

#### Using parenthesis for order of operation

The final thing to learn about the search parameter is how to use parenthesis to further specify in which order clauses should be evaluted in. Any expressions inside of group of parenthesis will be evaluted before clauses outside of parenthesis, as like in mathmatics. To insert a left parenthesis in a statement, **you put a left parathesis before the column name and after the semicolon** It should look something like this: 
```js
search=cost>=3;(color=ruby;|color=amber
```

This on it's own will throw an error however, as every left paranthesis must be grouped with a sistering right parenthsis. 

Right paranthesis are a little different however, instead of putting them next to a column name, you instead may put them anywhere you like. The only caviot however is that **each right parenthesis must be accompanied by it's own personal semicolon beforehand**
Now it will turn looking kind of like this: 
```ts
search=cost>=3;(color=ruby;|color=amber;)
```
[See how this looks](https://api.lorcana-api.com/cards/fetch?search=%3Dcost%3E%3D3%3B%28color%3Druby%3B%7Ccolor%3Damber%3B%29)

Please be aware that if you have another clause coming after a right parenthesis, it will need it's own semicolon, it can't borrow off the one being used by the right parenthesis. 
Kind of like this: 
```js
search=cost>=3;(color=ruby;|color=amber;);set_num=2
```
[See how this looks](https://api.lorcana-api.com/cards/fetch?search=%3Dcost%3E%3D3%3B%28color%3Druby%3B%7Ccolor%3Damber%3B%29%3Bset_num%3D2)

### Final reminders

You have now learned how to become a master of using the search parameter. here's a couple quick things before I leave off.

 - Please make sure to encode your URLs before making search requets. Many characters need for this parameter are not in standard ASCII.
 - Remember that the left are right parameters are declared differently from eachother because I don't know how to code.
 - Regardless of parameter or clause, you will only get the top 1000 matches at a time, so you will need to utilize [pagnation](pagnation-parameters) see more than only the top 1000.

