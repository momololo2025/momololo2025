## Hi there 👋

<!--
**momololo2025/momololo2025** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on crypto.com...
- 🌱 I’m currently learning memecoin...
- 👯 I’m looking to collaborate on web3...
- 🤔 I’m looking for help with creating nft...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
import pandas as pd

# Load the dataset
file_path = 'path/to/crypto_market_cap.csv'
df = pd.read_csv(file_path)

# Display the first few rows of the dataset
print("First few rows of the dataset:")
print(df.head())

# Display basic information about the dataset
print("\nBasic information about the dataset:")
print(df.info())

# Display summary statistics of the dataset
print("\nSummary statistics of the dataset:")
print(df.describe())

# Check for missing values
print("\nMissing values in the dataset:")
print(df.isnull().sum())

# Display the number of unique cryptocurrencies in the dataset
print("\nNumber of unique cryptocurrencies in the dataset:")
print(df['Cryptocurrency'].nunique())

# Display the total market capitalization over time
total_market_cap = df.groupby('Date')['Market_Cap'].sum()
print("\nTotal market capitalization over time:")
print(total_market_cap)

# Plotting (optional, requires matplotlib)
import matplotlib.pyplot as plt

# Plot total market capitalization over time
plt.figure(figsize=(12, 6))
total_market_cap.plot()
plt.title('Total Market Capitalization Over Time')
plt.xlabel('Date')
plt.ylabel('Market Capitalization')
plt.show()

# Additional analysis - Example: Average market cap per cryptocurrency
average_market_cap = df.groupby('Cryptocurrency')['Market_Cap'].mean()
print("\nAverage market capitalization per cryptocurrency:")
print(average_market_cap)

# Save the cleaned and analyzed dataset to a new CSV file
output_file_path = 'path/to/cleaned_crypto_market_cap.csv'
df.to_csv(output_file_path, index=False)
print(f"\nCleaned dataset saved to {output_file_path}")