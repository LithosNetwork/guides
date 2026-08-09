# Creating and managing a company

In order to create your own shops in survival.rocks, you will need to own or create a company:

- Create a company with `/create company` (run it in-game).
- Go to the link provided in chat.
- Choose a name and color for your company.
- And then sign the "contract" with a fictional signature.

Creating a company costs 500 coins.

## Private shares

Every company has so-called "private shares" that determine who own(s) the company. The creator of the company owns all 10,080 private shares in the beginning. You can give these private shares to anyone. Private shareholders own every aspect of the company: from accessing chest shops, to receiving profit from sales. Please note that shares that are transferred to another player cannot be taken back. To give company shares, you must use `/company <company_name> give-ownership <player> <amount>`.

Fun fact: The company starts out with an odd number of private shares (ten thousand and _eighty_), because that number is dividable by 1, 2, 3, 4, 5, 6, 7, 8, and 9. That way it is easy to give shareholders the same amount of shares. If you want the company to be equally owned by 3 players, each player could have 3,360 shares.

## Cash register
Coins from a sale or transaction are always queued to be paid out. This payout is done once every hour. So don't worry if you haven't received the coins from a sale within a few minutes!

It is possible to make these coins go into the balance of the company. The balance can be viewed with `/company <company_name> balance`. You can adjust what percentage of sale income will stay in the company balance with `/company <company_name> savings-rate <rate>` You can deposit and withdraw coins from the register with the following commands:

- `/company <company_name> deposit <amount>`
- `/company <company_name> withdraw <amount>`

Coins from either sales or a withdraw that are being paid out will always be equally spread across all private shareholders. If you own 50% of the shares of a company, you will receive 50% of the payout. You can also view sale transactions with `/company <company_name> transactions`.

## Customization

There are a couple ways you can customize your company!

### Color

You can change your company color using `/company <company_name> set-color <hex_code>`. To get a hex code for the color you want, search in your browser for a color picker. A hex code is a 6-digit combination that will be provided with the color you choose.

Once you have your hex color code, you can copy it into the command `/company <company_name> set-color #123456` (replace #123456 with your color code), and your company name will show up in your chosen color on shop signs and on the website.

### Logo

It is recommended to set a logo for your company. You can do this by either creating a banner in-game or creating map art. Then hold the banner or map art in your hand, and use `/company <company_name> set-logo`. The logo (banner or map art) will then be displayed on the website next to your company name.

You can view your logo, along with other company details directly with `/company <company_name> website-url`.

## Employees

You can hire other players to help run your shops or do tasks for you, and pay them a daily wage for that. Employees only really have access to open shop chests; they don't have access to any settings. However, they will be added to the company Discord thread. You will need to make sure there is enough coins in your company balance to pay them. Use the following comands to hire or fire an employee:

- `/company <company_name> hire <player> <wage>`
- `/company <company_name> fire <player>`
- And then to make sure you have enough coins to pay them: `/company <company_name> deposit <amount>`

Payout of coins stops when there is not enough coins in the company balance anymore. A good way to keep coins in the balance, is to set the savings rate of the company, so that coins from sales go directly into the company balance.

## Company thread

Every company gets its own private thread on Discord. Anyone involved in the company will be added to this thread: the private shareholders and employees. This thread is a way to communicate with everyone involved, and you will also receive the following messages about the company in the thread:
- When a shop chest goes out of stock
- Weekly profits made by the company
- Changes in private shareholders or employees
- When a deposit or withdraw took place

## Website pages

More about companies can be found in 3 places through the website:
- All companies that exist, you can click the name to go to the company's page: https://survival.rocks/companies
- View public information about your company: `/company <company_name> website-url`
- View some more detailed info and statistics about your company, you need to /login for this: `/company <company_name> website-details`
