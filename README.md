# Checkout Order Total Kata

You have been contracted to write part of a grocery point-of-sale system. Your job is to implement the business logic to calculate the pre-tax total price as items are scanned or entered at checkout.

Many items are sold at a per-unit price. For example, a can of soup sells for $1.89 each.

Some items are sold by weight. For example, 80% lean ground beef currently sells for $5.99 per pound. Bananas are currently $2.38 per pound.

Each week, some items are marked down. For example, the soup could be marked down 20 cents. In this case, it would sell for $1.69 during the week. Markdown prices must always be used in favor of the per-unit price during the sale. There are laws protecting the customer from false advertising.

Along with the markdowns, a set of specials are advertised each week. For example, the soup could be advertised as "buy one, get one free" or "buy two, get one half off" or "three cans for $5.00." Sometimes limits are placed on these specials. For example, "Buy two, get one free. Limit 6." Purchases not fitting the description of the special are sold at the per-unit price unless a markdown price has also been advertised.
## Requirements
* Your solution should have an API to configure the above kinds of prices, specials and markdowns. Instead of UPC or SKU codes, you may simply use strings such as "ground beef" or "soup" to describe what has been scanned or entered. **NOTE:** The term "API" simply refers to a collection of logical function calls exposed by your application. It does not necessarily imply something like a REST API.
* It should repeatedly accept a scanned item or item and weight through an API call. It must keep an accurate current total through the process.
* Clerks make mistakes. They need to be able to remove items from an order, immediately correcting the current total.
* You are not responsible for the display system or printing a receipt; only calculating the pre-tax total. The display system or receipt may query your code for the total.
* Your solution must not use a database. Everything will fit in memory.
## Use Cases
1. Accept a scanned item. The total should reflect an increase by the per-unit price after the scan. You will need a way to configure the prices of scannable items prior to being scanned.
2. Accept a scanned item and a weight. The total should reflect an increase of the price of the item for the given weight.
3. Support a markdown. A marked-down item will reflect the per-unit cost less the markdown when scanned. A weighted item with a markdown will reflect that reduction in cost per unit.
4. Support a special in the form of "Buy N items get M at %X off." For example, "Buy 1 get 1 free" or "Buy 2 get 1 half off."
5. Support a special in the form of "N for $X." For example, "3 for $5.00"
6. Support a limit on specials, for example, "buy 2 get 1 free, limit 6" would prevent getting a third free item.
7. Support removing a scanned item, keeping the total correct after possibly invalidating a special.
8. Support "Buy N, get M of equal or lesser value for %X off" on weighted items.

