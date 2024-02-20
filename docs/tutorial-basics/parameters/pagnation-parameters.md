# Pagnation Parameters (`page` and `pagesize`)

The pagnations parameters are used in conjunction with a fetching parameter (search, fuzzy, etc)to break up large responses into smaller portions. e.g. if your search clause returned 2000 cards, you can use pagnation parameters to break it up into 20 requests of 100 cards each.

Syntax: `pagesize=<number of cards per page>&page=<page number>`

## Usage

Response pagnation requires two seperate parameters to be used: `pagesize`, and `page`. `pagesize` determines how many cards will be returned with each response, this number must be less than  or equal to 1000. `page` determines at what spot in a large batch of cards will the the response return cards. That will be explained more later.

Each request made to lorcana-api.com is limited to up to 1000 cards per request, so what if you make a request for more than that? Say you made a request to `/cards/all`, and there are 3000 cards in the game, that request would be too big! You must use pagnation to break it up. 
if you had `/cards/all?pagesize=1000&page=1`, you get cards 1-1000 from the 3000 cards total, If you changed it to`/cards/all?pagesize=1000&page=2`, you would get cards 1001-2000 from the 3000 cards total. Using this, you can get all 3000 unique cards, you just have to break it up into 3 seperate requests.

The formula to determine which card numbers will be returned is `pagesize * (page - 1)` through `pagesize * page`
