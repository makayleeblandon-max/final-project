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

class Customer:
    def __init__(self, name):
        categories = ['Electronics', 'Books', 'Home & Garden', 'Fashion', 'Toys']
        
        self.name = name
        # Initialize budget (random int between 50 and 500)
        self.budget = random.randint(50, 500)
        # Initialize preference (random choice from categories)
        self.preference = random.choice(categories)
        # Initialize loyalty_score (start at 1.0)
        self.loyalty_score = 1.0 

names = ['Alex', 'Jade', 'Hunter', 'Levi', 'Rose']
customers = [Customer(name) for name in names]def process_transaction(customer, item_name, proposed_price, inventory_df):
    if item_name not in inventory_df.index or inventory_df.at[item_name, 'quantity'] <= 0:
        customer.loyalty_score -= 1
        return "Out of stock"

    if proposed_price <= customer.max_bid:
        inventory_df.at[item_name, 'quantity'] -= 1
        customer.loyalty_score += 5
        return True
    
    customer.loyalty_score -= 2
    return False
