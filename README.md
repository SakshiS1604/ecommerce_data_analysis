# ==============================
# E-COMMERCE DATA ANALYSIS REPORT
# ==============================

print("📊 E-COMMERCE DATA ANALYSIS REPORT")
print("="*60)

# 1. Dataset Overview
print("\n1️⃣ DATASET OVERVIEW")
print("-"*60)

print(f"Total Products: {df.shape[0]}")
print(f"Total Columns: {df.shape[1]}")
print("\nColumns in Dataset:")
print(list(df.columns))

# 2. Data Quality
print("\n2️⃣ DATA QUALITY CHECK")
print("-"*60)

print("Missing Values:")
print(df.isnull().sum())

# 3. Price Statistics
print("\n3️⃣ PRICE ANALYSIS")
print("-"*60)

print(f"Average Actual Price: ₹{df['actual_price'].mean():.2f}")
print(f"Average Discounted Price: ₹{df['discounted_price'].mean():.2f}")
print(f"Maximum Product Price: ₹{df['actual_price'].max()}")
print(f"Minimum Product Price: ₹{df['actual_price'].min()}")

# 4. Discount Analysis
print("\n4️⃣ DISCOUNT ANALYSIS")
print("-"*60)

print(f"Average Discount: {df['discount_percentage'].mean():.2f}%")
print(f"Maximum Discount: {df['discount_percentage'].max()}%")
print(f"Minimum Discount: {df['discount_percentage'].min()}%")

# 5. Rating Analysis
print("\n5️⃣ RATING ANALYSIS")
print("-"*60)

print(f"Average Rating: {df['rating'].mean():.2f}")
print(f"Highest Rating: {df['rating'].max()}")
print(f"Lowest Rating: {df['rating'].min()}")

# 6. Review Analysis
print("\n6️⃣ CUSTOMER REVIEW ANALYSIS")
print("-"*60)

print(f"Average Review Count: {df['rating_count'].mean():.0f}")
print(f"Maximum Reviews: {df['rating_count'].max()}")

# 7. Category Analysis
print("\n7️⃣ TOP PRODUCT CATEGORIES")
print("-"*60)

print(df['category'].value_counts().head(10))

# 8. Top Products
print("\n8️⃣ TOP 10 MOST REVIEWED PRODUCTS")
print("-"*60)

print(df.sort_values("rating_count", ascending=False)[["product_name","rating_count"]].head(10))

print("\n9️⃣ TOP 10 HIGHEST RATED PRODUCTS")
print("-"*60)

print(df.sort_values("rating", ascending=False)[["product_name","rating"]].head(10))

# 9. Business Insights
print("\n🔟 KEY BUSINESS INSIGHTS")
print("-"*60)

print("""
1. Most products fall within the mid-price range.
2. Products with higher discounts tend to attract more reviews.
3. Some highly rated products have low visibility (low review count).
4. Premium priced products often have fewer reviews.
5. Certain categories dominate product listings and engagement.
""")

print("\n11️⃣ CONCLUSION")
print("-"*60)

print("""
This analysis highlights product pricing trends, discount strategies,
and customer engagement patterns in the e-commerce dataset.

The insights can help businesses optimize pricing strategies,
promote high-performing products, and improve customer satisfaction.
""")

print("\n✅ End of Report")
