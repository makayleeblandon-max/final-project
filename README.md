# final-project
import pandas as pd

inventory_data = {
    'item_name': ['Rudy Sword', 'Health Potion', 'Diamond Pickaxe', 'Cake', 'Emerald Shield'],
    'category': ['weapon', 'consumable', 'tool', 'food', 'armor'],
    'base_cost': [150.0, 50.0, 80.0, 5.0, 45.0],
    'quantity': [5, 20, 10, 50, 8]
}

inventory_df = pd.DataFrame(inventory_data)

inventory_df.set_index('item_name', inplace=True)

print(inventory_df)
