# PRODIGY_DS_04
Analyze and visualize social media data to understand public opinion and attitudes towards specific topics or brands.


import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Step 1: Load the dataset
url = r'daaset\twitter_training.csv\twitter_training.csv'
df = pd.read_csv(url)

# Step 2: Explore the dataset
print(df.head())
print(df['Sentiment'].value_counts())

# Step 3: Visualize sentiment patterns
plt.figure(figsize=(8, 6))
sns.countplot(x='Sentiment', data=df, palette='viridis')
plt.title('Sentiment Distribution')
plt.xlabel('Sentiment')
plt.ylabel('Count')
plt.show()

# Step 4: Explore sentiment by game
plt.figure(figsize=(12, 8))
sns.countplot(x='Sentiment', hue='Game', data=df, palette='muted')
plt.title('Sentiment Distribution by Game')
plt.xlabel('Sentiment')
plt.ylabel('Count')
plt.legend(title='Game', loc='upper right')
plt.show()
