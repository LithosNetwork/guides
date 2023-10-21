# Tax system
The server currently has these taxes:
- Shop Income Tax
- Dividend Tax

### Definitions
First some definitions, used in the guide:
- **Private shareholder** (private ownership) — Simply put, a direct owner of a company. They can create chest shops for a company.
- ***Tax ID*** — Every item in the server has a *Tax ID*, which can be found by either clicking an item on https://survival.rocks/items, or by using /meta on an item in your hand.
    For 'Enchanted Book' with 'Fortune III', it is `enchanted-book-fortune`, and for 'Red Concrete', it is `concrete`, to name two examples. 
- **Tax Count** (*`c`*) — Every *Tax ID* has a 'Tax Count' value of 1. This value can, however, be reduced in certain circumstances.
   This value is to determine the tax percentage a player has to pay for Shop Income Tax.

## Shop Income Tax
Shop income tax was introduced in mid-2020 for the following reasons:
- many (big) companies would sell any item (hundreds) in their shop, and fight the prices to the bottom with other (big) companies;
- because of that, items were dirt cheap, and starting out companies couldn’t keep up with the prices of big companies.

This tax forces companies—or actually their private shareholders—to specialize into a specific group of items to sell. 
And if that does not happen, they pay (higher) tax, which results in higher prices for the company to sell their items at.

The tax percentage is determined by:
- the amount of taxable items (by *Tax ID*) you are selling through the companies you are a private shareholder of;
- the percentage of private ownership you have in the company you sell the items at.

Every different *Tax ID* of items you are selling through companies adds to your 'Tax Count'. However, if you do not own 100% of a company, the value is reduced.
Your 'Tax Count' is the sum of the different Tax IDs you sell an item for, multiplied (or really reduced) by the ownership of the company you sell them at.
Sorry for the confusion, but it is easier than you think, just hard to explain. Here is an example:

|Company|Ownership|*Tax ID*|Tax Count|
|-|-|-|-|
|**Company A**|100%|netherite-ingot|1.00|
|||gold-ingot|1.00|
|||diamond|1.00|
|**Company B**|20%|elytra|0.20|
|||concrete|0.20|
|||saddle|0.20|
|**TOTAL**|||**3.60**|

The next part is calculating the tax percentage with the given Tax Count. 
A formula is used for this: *`t = (25 * log(c - 6.817) - 28)`*, where *`t`* is the tax percentage and *`c`* is the Tax Count.
When *`t`* is negative, the tax percentage is 0%. This is the case for a Tax Count less than or equal to 20.

![image](https://user-images.githubusercontent.com/8517465/158900610-40d63e06-9982-4187-89ab-f0016546c40c.png)

### Some real-game examples
- If you only and fully own one company:
  - with less than or equal to 20 chest shops, you pay 0% tax.
  - with more than 20 chest shops, you pay tax on income from the chest shop sales.
- If you only own one company, and you own 20% of the company, you can have 100 chest shops tax-free.
  - Keep in mind that you only receive 20% of the profit from the company.
  - The 100 is calculated by { 1 / 0.20 (percentage ownership) * 20 (tax-free threshold) }.

## Dividend Tax (Work in Progress)
This tax is specific to the *public* shares you own of a company you are also a *private* shareholder of. 
The tax percentage for a specific share is the percentage of private ownership in that company.

Example: if you are a private shareholder of company A for 90%, your dividend tax for your public shares in company A is 90%.
