# final-project

import pandas as pd

inventory_data = {
    'item_name': [
        'Iron Sword', 'Steel Longsword', 'Mithril Dagger', 'Dragonbone Greatsword', 'Rusty Mace', 
        'Gleaming Rapier', 'Shadow Assassin Blade', 'Holy Avenger', 'Oak Shortbow', 'Yew Longbow',
        'Elven Recurve', 'Crystal Staff', 'Apprentice Wand', 'Archmage Staff', 'Heavy Crossbow',
        'Bronze Spear', 'Halberd of the Guard', 'War Hammer', 'Battle Axe', 'Twin Hatchets',
        'Leather Tunic', 'Studded Leather Armor', 'Chainmail Shirt', 'Steel Plate Armor', 'Mithril Mail',
        'Iron Shield', 'Wooden buckler', 'Tower Shield', 'Dragonscale Vest', 'Enchanted Robes',
        'Steel Helmet', 'Great Helm', 'Leather Boots', 'Gauntlets of Strength', 'Greaves of Speed',
        'Cloak of Invisibility', 'Heavy Pickaxe', 'Masterwork Hammer', 'Silver Chisel', 'Iron Shovel',
        'Telescope', 'Compass', 'Lockpick Set', 'Blacksmith Tongs', 'Fishing Rod', 'Small Health Potion',
        'Greater Mana potion', 'Antidote', 'Elixir of Strength', 'Flask of Fire Resistance',
        'Loaf of Bread', 'Wheel of Cheese', 'Roasted Venison', 'Dried Rations', 'Sweet Apple',
        # ... (Truncated for display, see pattern below for the full list of 200)
    ] * 4, # Multiplying to reach 220 items total
    'category': [
        'weapon', 'weapon', 'weapon', 'weapon', 'weapon', 
        'weapon', 'weapon', 'weapon', 'weapon', 'weapon',
        'weapon', 'weapon', 'weapon', 'weapon', 'weapon',
        'weapon', 'weapon', 'weapon', 'weapon', 'weapon',
        'armor', 'armor', 'armor', 'armor', 'armor', 
        'armor', 'armor', 'armor', 'armor', 'armor',
        'armor', 'armor', 'armor', 'armor', 'armor',
        'armor', 'tool', 'tool', 'tool', 'tool',
        'tool', 'tool', 'tool', 'tool', 'tool',
        'consumable', 'consumable', 'consumable', 'consumable', 'consumable',
        'food', 'food', 'food', 'food', 'food'
    ] * 4,
    'base_cost': [
        150.0, 250.0, 400.0, 1200.0, 45.0, 300.0, 850.0, 2500.0, 120.0, 280.0,
        550.0, 900.0, 150.0, 3000.0, 200.0, 90.0, 180.0, 220.0, 210.0, 140.0,
        50.0, 120.0, 350.0, 800.0, 1500.0, 60.0, 20.0, 250.0, 2200.0, 450.0,
        80.0, 150.0, 40.0, 110.0, 130.0, 5000.0, 80.0, 150.0, 60.0, 25.0,
        100.0, 50.0, 75.0, 30.0, 15.0, 50.0, 75.0, 40.0, 150.0, 100.0,
        5.0, 10.0, 25.0, 15.0, 2.0
    ] * 4,
    'quantity': [random.randint(1, 50) for _ in range(220)],
    'attack_power': [
        15, 22, 18, 55, 12, 20, 40, 65, 18, 25,
        35, 30, 10, 50, 28, 16, 24, 30, 28, 20,
        0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
        0, 0, 0, 0, 0, 0, 5, 8, 2, 4,
        0, 0, 1, 3, 2, 0, 0, 0, 5, 0,
        0, 0, 2, 0, 0
    ] * 4,
    'defense_power': [
        0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
        0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
        10, 15, 25, 50, 65, 20, 8, 45, 75, 15,
        12, 18, 5, 10, 12, 30, 0, 0, 0, 0,
        0, 0, 0, 0, 0, 0, 0, 0, 0, 10,
        0, 0, 0, 0, 0
    ] * 4
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
