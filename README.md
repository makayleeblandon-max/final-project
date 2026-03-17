# final-project

import pandas as pd

inventory_data = {
    'item_name': ['Iron Sword', 'Health Potion', 'Steel Pickaxe', 'Loaf of Bread', 'Wooden Shield'],
    'category': ['Weapon', 'Consumable', 'Tool', 'Consumable', 'Weapon'],
    'price': [50, 10, 35, 5, 20],
    'quantity': [5, 20, 10, 15, 8]
}
df_inventory = pd.DataFrame(inventory_data)
categories = df_inventory['category'].unique().tolist()

class Customer:
    def __init__(self, name):
        self.name = name
        # Budget between 20 and 100 gold
        self.budget = random.randint(20, 100) 
        # Pick a favorite category from our inventory
        self.preference = random.choice(categories)
        # Everyone starts neutral
        self.loyalty_score = 1.0

    def __repr__(self):
        return f"[{self.name} | Budget: {self.budget}g | Pref: {self.preference} | Loyalty: {self.loyalty_score}]"

names = ["Aric", "Bera", "Cid", "Dara", "Elowen"]
customers = [Customer(name) for name in names]

print("--- Active Customers ---")
for c in customers:
    print(c)

    # TODO: Use results_df and inventory_df to calculate the 10 metrics
# Example: total_revenue = results_df[results_df['success'] == True]['price'].sum()
# --- PRINT YOUR FINAL REPORT ---
