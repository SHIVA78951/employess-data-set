# Calculate attrition rate
attrition_rate = data['Attrition'].value_counts(normalize=True)['Yes'] * 100
print(f"Attrition Rate: {attrition_rate:.2f}%")

# Visualize attrition count
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=data, x='Attrition', palette='Set2')
plt.title('Employee Attrition Count')
plt.ylabel('Number of Employees')
plt.show()
# Boxplot: Age vs Attrition
sns.boxplot(data=data, x='Attrition', y='Age', palette='Set3')
plt.title('Age vs Attrition')
plt.show()

# Histogram
sns.histplot(data=data, x='Age', hue='Attrition', multiple='stack', kde=True, palette='Set1')
plt.title('Age Distribution by Attrition')
plt.show()
# Boxplot: YearsAtCompany vs Attrition
sns.boxplot(data=data, x='Attrition', y='YearsAtCompany', palette='Set1')
plt.title('Years at Company vs Attrition')
plt.show()

# Boxplot: Monthly Income vs Attrition
sns.boxplot(data=data, x='Attrition', y='MonthlyIncome', palette='Set2')
plt.title('Monthly Income vs Attrition')
plt.show()

# Histogram
sns.histplot(data=data, x='MonthlyIncome', hue='Attrition', multiple='stack', kde=True, palette='Set2')
plt.title('Monthly Income Distribution by Attrition')
plt.show()

# Correlation heatmap for numeric features
import numpy as np

numeric_cols = data.select_dtypes(include=np.number).columns
plt.figure(figsize=(14, 10))
corr = data[numeric_cols].corr()

sns.heatmap(corr, annot=True, fmt=".2f", cmap='coolwarm', linewidths=0.5)
plt.title("Correlation Heatmap of Numeric Features")
plt.show()





