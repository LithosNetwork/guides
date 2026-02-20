# Tax System
The economy of survival.rocks currently has the following tax systems.
### Shop Income Tax
In short: No tax is paid when 20 shop chests or less are owned. The guide for this tax explains what happens when you go over 20 shop chests.
<!-- ### Dividend Tax -->

## Definitions
Here are some definitions for terms used in the guides.
- **Private shareholder** — Simply put, an owner of a company, or private ownership. Private shareholders can create shop chests for the company.
- **Tax identifier** — An identifier for in-game items, used for taxing. Every (category of) items has a different tax identifier, which can be found by using _/meta_ on an item in your hand. Example: For 'Enchanted Book' with 'Fortune III', it is `enchanted-book-fortune`, and for 'Red Concrete', it is `concrete`. 
- **Company count** — The percentage of a company that a private shareholder owns, a value from 0.00 to 1.00. This value makes it possible to pay less tax when you don't fully own a company.

## Shop Income Tax
**Shop Income Tax** was introduced in mid-2020 for the following reasons:
- Many companies sold almost all possible items in their shop, fighting prices to rock-bottom with other companies.
- Items were dirt cheap for this reason; starting companies couldn’t compete with the prices of bigger companies.

This tax forces companies—or their private shareholders—to specialize into a specific group of items to sell. They pay higher tax if they sell a broader amount of items. This results in higher prices for bigger companies to sell their items at.

The tax percentage is determined by:
- The amount of distinct tax identifiers that are sold, through the companies one is a private shareholder of.
- The percentage of private ownership one has in a company selling items.

We have to calculate the total 'amount' of shop chests a private shareholder owns, shared between companies. This is done by counting distinct tax identifiers a company holds. Example: When a company sells Red Concrete, Blue Concrete, and Bow (3 items), the number is 2, because Red Concrete and Blue Concrete share the same tax identifier (`concrete`). Here is an example with two companies:

|Company|Items selling|Distinct tax identifiers|
|-|-|-|
|Company A|17|17|
|Company B|28|21|

Next, we have to calculate the company count: How much the tax identifiers weigh for private shareholders. This value is different for every company you are a private shareholder of. It is always 1.00 when you own the entire company. Here is an example with two companies:

|Company|Percentage ownership|Company count|
|-|-|-|
|Company A|100%|1.00|
|Company B|25%|0.25|

After this, we multiply the distinct tax identifiers of a company with the private shareholder's company count. Here is an example for one private shareholder with two companies:

|Company|Distinct tax identifiers|Company count|Multiplied|
|-|-|-|-|
|Company A|17|1.00|17.00|
|Company B|21|0.25|5.25|
|**Total**|||22.25|

This total amount is the 'real' amount of items the private shareholder is selling (**_r_**), and it will be used to calculate tax. The next step would then be to calculate the tax percentage. For this we use a formula: **_t_ = (25 × log(_r_ - 6.817) - 28)**. In this formula, **_r_** is the real calculated amount of items a private shareholder is selling. In the previous example **_r_** is 22.25. This results in **_t_**, the tax percentage for the private shareholder. The tax percentage cannot be negative, so any negative number is adjusted to 0. This is the case for the first 20 shop chests. See this image for a graph of the formula:
![image](https://github.com/user-attachments/assets/0377b864-402c-43d7-aa8b-7798fdb9855b)

Here is an overview of the tax percentage for a few points:

|Calculated items selling (**_r_**)|Tax percentage|
|-|-|
|0|0.00%|
|20|0.00%|
|20.5|0.40%|
|21|0.79%|
|22|1.53%|
|23|2.23%|
|24|2.88%|
|25|3.49%|
|30|6.13%|
|40|10.02%|
|50|12.88%|
|100|21.23%|

## Real examples
- **You fully own only one company.** — No tax is levied when this company has 20 shop chests or less. The company count is 1.00, so the distinct amount of tax identifiers can directly be used as **_r_** in the formula.
- **You own only one company for 20%.** — Your company count is 0.20. This means you can have 100 distinct tax identifiers tax free, by dividing 20 by 0.20. Keep in mind that you only receive 20% of the profit from the company.
- **You fully own only two companies.** — No tax is levied when the total of both companies is 20 shop chests or less. The company count is 1.00 for both companies. The distinct amount of tax identifiers from both companies combined can directly be used as **_r_** in the formula.
- **You own one company fully, and one company for 25%.** — See the example of the explanation.
- **You own one company for 50%, and one for 25%.** — This is where it gets a little more difficult. When you look at the example of the explanation, and we replace the 100% percentage ownership for Company A with 50%, the 'real' amount of items will be 13.75, instead of 22.25 in the example. This 13.75 can be used as **_r_** in the formula.

<!--
## Dividend Tax (Work in Progress)
This tax is specific to the *public* shares you own of a company you are also a *private* shareholder of. 
The tax percentage for a specific share is the percentage of private ownership in that company.

Example: if you are a private shareholder of company A for 90%, your dividend tax for your public shares in company A is 90%.
-->
