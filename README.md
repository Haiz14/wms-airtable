Inventory management and visualisations via airtable and discord. 

The bot has followimg cmds:

- /negative: returns excel file with **msku** whose quantity is negative. 

- /inventory : Updates the inventory. 

When you run this cmd; attach an excel file with columns **msku**, **qty**.

- /sales: Update sales records and reduce inventory. 

When you run this cmd;  attach an excel file with  columns **sku**, **msku**, **sold_on_platform**, **qty**, returns an excel file containing **msku** whose **qty** is negative after this update.

- /paired-sales: Update paired sales record and inventory. 

When you rin this cmd, attach an excel file with columns **sku1**, **sku2**, **msku1**, **msku2**, **qty**, **sold_on_platform**, returns **msku** whose qty is negative after this update.

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

Used to check if invetory is full and `popualar products` chart.

2. SKU_SOLD_ON (a new row for same sku but different platform)
  - sku1
  - sku2: can be none
  - msku1
  - msku2: can be none
  - sold_on_platform
  - qty
  - monthly_sales

Charts made with this record tells you which products are popular in which platforms. Maybe also add a zip code, for zip code based analysis.
