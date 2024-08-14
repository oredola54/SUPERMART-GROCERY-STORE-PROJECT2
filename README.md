
# GROCERY SUPERMART PROJECT2

# PROBLEM STATEMENT

This will help to Identify trends,patterns and insights that can optimize inventory management,sales strategies and customer behaviour with a focus on optimizing revenue and improving customer satisfaction.

The Dataset contains the following columns:

- Customer Name
- Category  
- Sales  
- Profit  
- Order Date etc.  

RECOMMENDATIONS:

- Getting the total sales per day 
- Knowing the Top5 city by sales using seaborn Library  
- Showing the Top10 customer with the highest Profit  
- Showing Category by year
- Showing Category by Sales  
- Showing Discount by Region  
 

# LIBRARY USED
1. import pandas as pd
2. import numpy as np
3. import matplotlib.pyplot as plt
4. import seaborn as sns  

# STEPS

- Loading in the Dataset and using the first
  column as my index column
- Changing the "ORDER DATE" Colunmn to a date 
- GrocerySuperMart["Order Date"]=pd.to_datetime(GrocerySuperMart  ["Order Date"])

1. TOTAL SALES PER DAY:

-  GrocerySuperMart["Day_Name"]=GrocerySuperMart["Order Date"].dt. day_name() 
-  DaySales=GrocerySuperMart.groupby("Day_Name")["Sales"].sum()
-  DaySales
-  Name=DaySales.index
-  Number=DaySales.values
-  plt.bar(Name,Number,color="orange")
-  plt.title("SALES PER DAY",fontsize=16,fontweight="bold",     fontstyle="italic")
-  plt.xlabel("Days")
-  plt.ylabel("Sales per day")
-  plt.savefig("SALES PER DAY.png")
-  plt.show() 

![SALES PER DAY (1)](https://github.com/user-attachments/assets/9577a8dd-37fe-46bb-954e-1e012d92f23a)



2. TOP 5 CITY BY SALES:

- Top5=GrocerySuperMart.sort_values("Sales",ascending=False).head(5)
- Top5
- sns.barplot(y=Top5["City"],x=Top5["Sales"], data=Top5, palette="Paired")
- plt.title(" TOP 5 CITY BY SALES")
- plt.xlabel("CITY") #Violin Plot
- plt.ylabel("SALES")
- plt.savefig("TOP 5 CITY BY SALES.png")
- plt.show()

![TOP 5 CITY BY SALES](https://github.com/user-attachments/assets/98bcf7d7-154a-4a6f-8dc7-b5101cfe76c5)



3. SHOWING T0P 10 CUSTOMER WITH THE HIGHEST PROFIT:

- CustomerSales=Top10.groupby("Customer Name")["Profit"].sum()
- CustomerSales
- Name1=CustomerSales.index
- Number1=CustomerSales.values
- plt.barh(Name1,Number1,color="Red")
- plt.title("TOP 10 CUSTOMERS WITH HIGHEST PROFIT",fontsize=16, fontweight="bold",c="Black")
- plt.savefig("TOP 10 CUSTOMERS WITH THE HIGHEST PROFIT.png")
- plt.show()

![TOP 10 CUSTOMERS WITH THE HIGHEST PROFIT](https://github.com/user-attachments/assets/31bd7325-dcab-4824-8ee7-a30b7a84056d)


4. SHOWING CATEGORY BY YEAR:  
- GrocerySuperMart["Year"]=GrocerySuperMart["Order Date"].dt.year
- Year=GrocerySuperMart.groupby("Year")["Sales"].sum()
- Year
- Name3=Year.index
- Number3=Year.values
- plt.pie(Number3,labels=Name3,autopct="%1.0f%%",shadow=True,explode=[0,0.1,0,0.1])
- plt.title("CATEGORY BY YEAR",fontsize=15,fontweight="bold",- c="Red")
- plt.savefig("CATEGORY BY YEAR.png")
- plt.show()

![CATEGORY BY YEAR](https://github.com/user-attachments/assets/c59b177b-19e6-4e68-bf53-5c2de0f4f632)


5. SHOWING CATEGORY BY SALES:
- sns.boxplot(x=GrocerySuperMart["Category"],y=GrocerySuperMart["Sales"], data=GrocerySuperMart,palette="husl",color="Green")
- plt.title("CATEGORY BY SALES")
- plt.xlabel("CATEGORY NAME")
- plt.ylabel("TOTAL SALES")
- plt.savefig("CATEGORY BY SALES.png")
- plt.show()

![CATEGORY BY SALES](https://github.com/user-attachments/assets/585336f8-0df0-4817-b298-fba3acc6aa7f)


6. SHOWING DISCOUNT BY REGION  
- Region=GrocerySuperMart.groupby("Region")["Discount"].sum()
- Region
- Name4=Region.index
- Number4=Region.values
- plt.plot(Name4,Number4,marker="+")
- plt.title("DISCOUNT BY REGION",fontsize=15,fontweight="bold",c="violet")
- plt.xlabel("REGION")
- plt.ylabel("Discount")
- plt.savefig("DisReg.png")
- plt.show()

![DisReg](https://github.com/user-attachments/assets/309126fb-bf54-4bd3-9c7d-40228c548846)




# SCREENSHOTS OF SUBPLOTS
- fig,GrocerySuperMart1=plt.subplots(nrows=3,ncols=2,figsize=(12,12))
- fig.suptitle("GROCERY SUPERMART REPORT",fontweight="bold",c="#800080",fontsize=30)
- GrocerySuperMart1[0,0].bar(Name,Number,color="lime")
- sns.barplot(x=Top5["City"],y=Top5["Sales"],data=Top5,palette="summer",ax=GrocerySuperMart1[0,1])
- GrocerySuperMart1[1,0].barh(Name1,Number1,color="Red")
- GrocerySuperMart1[1,1].pie(Number3,labels=Name3,autopct="%1.0f%%",shadow=True,explode=[0,0.1,0,0.1])
- sns.boxplot(x=GrocerySuperMart["Category"],y=GrocerySuperMart["Sales"],data=GrocerySuperMart,palette="husl",ax=GrocerySuperMart1[2,0])
- GrocerySuperMart1[2,1].plot(Name4,Number4,marker="+")
- GrocerySuperMart1[0,0].set(title="SALES PER DAY")
- GrocerySuperMart1[0,1].set(title="TOP 5 CITY BY SALES")
- GrocerySuperMart1[1,0].set(title="TOP 10 CUSTOMER WITH THE HIGHEST PROFIT")
- GrocerySuperMart1[1,1].set(title="CATEGORY BY YEAR")
- GrocerySuperMart1[2,0].set(title="CATEGORY BY SALES")
- GrocerySuperMart1[2,1].set(title="DISCOUNT BY REGION")
- plt.tight_layout()
- plt.savefig("CATEGORY SUPERMART REPORT.png")
- plt.show()

![CATEGORY SUPERMART REPORT](https://github.com/user-attachments/assets/3771eeb7-3a86-460c-b109-96355e5b79fd)




















