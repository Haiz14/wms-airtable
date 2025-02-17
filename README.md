Inventory management and visualisations via airtable and discord. 

The bot has followimg cmds:

- /negative: returns **msku** whose quantity is negative.

- /inventory : Updates the inventory. Attach an excel file with columns **msku**, **qty**.

- /sales: Update sales records and reduce inventory, Add sales Attach excel file with  columns **sku**, **msku**, **sold_on_platform**, **qty**, returns an excel file containing **msku** whose **qty** is negative after this update.

- /paired-sales: Update paired sales record and inventory. Attach excel file with columns **sku1**, **sku2**, **msku1**, **msku2**, **qty**, **sold_on_platform**, returns **msku** whose qty is negative after this update.

# Starting-Up

1. Fill in a .env or environment with vars:
  - AIRTABLE_BASE_ID
  - AIRTABLE_API_KEY
  - DISCORD_BOT_TOKEN
  - DISCORD_GUILD_ID

2. `pip install -r requirements.txt`

3. `python3 main.py`

# Airtable Design

Only 2 records

1.  MSKU INVENTORY
  - msku
  - qty 
  - monthly_sales

2. SKU_SOLD_ON (a new row for same sku but different platform)
  - sku
  - msku
  - sold_on_platform
  - qty
  - monthly_sales


