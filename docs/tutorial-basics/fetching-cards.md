---
sidebar_position: 7
---

# Fetching cards

Using the /cards/ endpoint, you can fetch up to 1000 cards at once of any shape or size, using various filters or restrictions.

The syntax of the URL looks something like this: `api.lorcana-api.com/cards/<fetch/all>?parameter1key=parameter1value`

To begin, you'll have to choose what path to use, currently there are 2 options: `fetch`, and `all`. Heres a brief description of both:
 - **fetch:** used for when you want only cards that meet a certain criteria, like only fetching amber cards.
 - **all:** used for when you want all the cards in the game to be returned to you. 

 :::note

 For both of these paths, you'll only get a max of 1000 cards at a time, so you will need to utilize **pagnation** to get more than just the top 1000 hits.
 :::

 Now your URL should look something like this: `api.lorcana-api.com/cards/fetch`, or this `api.lorcana-api.com/cards/all`

 Next up, it's time for the fun part: parameters! 
 Parameters are the way that that you can customize your response to get exactly what you looking for. So far, there are 5 parameters options to choose from. They are explained in full details in the [Parameters Documentation](/docs/category/parameters) , but here is a brief description of each.
  - **pagesize:** The amount of cards to display per page. Default 100. Avaliable for all paths
  - **page:** What page to display. e.g. if pagesize=20 and page=2, then cards 20-40 will be displayed. Avaliable for all paths
  - **displayonly:** What columns of data to return. e.g. you only want the `name` and `cost` rows returned. Avaliable for all paths
  - **strict:** Used for fetching cards when you have the exact name of the card. Avaliable for /fetch path
  - **search:** Used for gettings cards that meet certain parameters, like having a cost less than 3. Avaliable for /fetch path



