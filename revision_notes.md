# Python Data Science Revision Notes

## Topics Covered

for Loop, break, continue, pass, Lambda Functions, String Basics, String Operations, Lists, Tuples, Dictionaries, Sets, Seaborn Basics, Line Charts, Bar Charts, Histograms, Scatter Plots, Correlation Matrix, Exploratory Data Analysis, Data Insights, Linear Regression, Model Prediction, MAE, MSE, and R2 Score.

Teacher speaking flow: "Students, ye revision notes aise banaye gaye hain ki aap directly read karke samjha sako. Har topic me pehle concept samjhenge, phir real use case dekhenge, phir practical code run karenge, phir har line ko detail me decode karenge."

---

# 0. Module Installation Setup

Data science aur machine learning topics ke liye hume kuch modules install karne padte hain. Python basic language hume loops, strings, lists, dictionaries deta hai, lekin charts, EDA, datasets, linear regression, MAE, MSE, R2 score ke liye extra libraries chahiye hoti hain.

```bash
python3 -m pip install -r requirements.txt
```

## Detailed Command Explanation

| Part | Code | Explanation |
|---|---|---|
| 1 | `python3` | Ye Python 3 interpreter use karta hai. Mac/Linux me mostly `python3` command hoti hai. Agar Windows me `python` Python 3 open karta hai to `python -m pip install -r requirements.txt` use kar sakte ho. |
| 2 | `-m pip` | Ye Python ke package installer pip ko run karta hai. Pip modules ko download/install karta hai. |
| 3 | `install` | Ye pip ko batata hai ki package install karna hai. |
| 4 | `-r requirements.txt` | Ye requirements file se module list read karta hai. Is project me `numpy`, `pandas`, `matplotlib`, `seaborn`, aur `scikit-learn` install honge. |

---

# 1. for Loop

`for loop` ka use tab hota hai jab hume kisi collection ke har item par same kaam repeat karna hota hai. Collection list, tuple, string, dictionary, range, ya dataset rows ho sakti hain. Real world me for loop marks list total karne, names print karne, files process karne, products ka bill calculate karne, aur dataset columns check karne me use hota hai. Jab hume pata ho ki kitni baar loop chalana hai ya hume kisi sequence par one by one jana hai, tab `for loop` best choice hota hai.

## Practice Code

```python
marks = [78, 85, 90, 66, 92]

total = 0

for mark in marks:
    total = total + mark

average = total / len(marks)

print("Total Marks:", total)
print("Average Marks:", average)
```

## Expected Output

```text
Total Marks: 411
Average Marks: 82.2
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `marks = [78, 85, 90, 66, 92]` | Ye list banata hai jisme student ke marks store hain. List multiple values ko ek variable me rakhti hai. |
| 3 | `total = 0` | Total marks calculate karne ke liye starting value zero set karte hain. Loop ke andar har mark is total me add hoga. |
| 5 | `for mark in marks:` | Ye loop `marks` list ke har item ko one by one `mark` variable me laata hai. Pehli baar `mark = 78`, second time `85`, aur aise continue hota hai. |
| 6 | `total = total + mark` | Current mark ko total me add karta hai. Ye line har loop cycle me total ko update karti hai. |
| 8 | `average = total / len(marks)` | Average calculate karta hai. `len(marks)` list me total items count karta hai. |
| 10 | `print("Total Marks:", total)` | Total marks screen par print karta hai. |
| 11 | `print("Average Marks:", average)` | Average marks screen par print karta hai. |

---

# 2. break, continue, pass

`break`, `continue`, aur `pass` loop control statements hain. `break` loop ko completely stop karta hai. `continue` current iteration skip karke next iteration par chala jata hai. `pass` kuch nahi karta, bas placeholder ke form me use hota hai. Real use case me `break` tab use hota hai jab target item mil gaya ho, jaise roll number search. `continue` tab use hota hai jab invalid data skip karna ho. `pass` tab use hota hai jab logic baad me likhna hai but code structure abhi ready rakhna hai.

## break Individually

`break` ka use tab hota hai jab hume loop ko immediately stop karna ho. Example: agar product list me target product mil gaya, to loop ko aage chalane ki need nahi. Search operations, login attempts, validation checks, and emergency stop conditions me `break` useful hota hai.

## continue Individually

`continue` current item ko skip karke next item par chala jata hai. Example: marks list me negative marks invalid hain, to unko skip karke baaki marks process kar sakte hain. Data cleaning me invalid rows skip karne ke liye `continue` ka use hota hai.

## pass Individually

`pass` kuch nahi karta. Ye placeholder hota hai. Jab hume function, loop, ya condition ka structure banana ho but logic baad me likhna ho, tab `pass` use hota hai. Ye syntax error avoid karta hai.

## Practice Code

```python
numbers = [5, 10, -1, 20, 0, 30]

for number in numbers:
    if number < 0:
        continue
    if number == 0:
        break
    if number > 25:
        pass
    print("Valid Number:", number)
```

## Expected Output

```text
Valid Number: 5
Valid Number: 10
Valid Number: 20
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `numbers = [5, 10, -1, 20, 0, 30]` | Ye sample numbers list hai. Isme positive, negative, zero values mix hain. |
| 3 | `for number in numbers:` | Loop har number ko one by one process karta hai. |
| 4 | `if number < 0:` | Check karta hai kya number negative hai. |
| 5 | `continue` | Negative number skip karta hai aur loop next number par chala jata hai. Isliye `-1` print nahi hota. |
| 6 | `if number == 0:` | Check karta hai kya number zero hai. |
| 7 | `break` | Zero milte hi loop completely stop kar deta hai. Isliye zero ke baad `30` process nahi hota. |
| 8 | `if number > 25:` | Ye condition large number ke liye placeholder example hai. |
| 9 | `pass` | `pass` kuch nahi karta. Ye future logic ke liye placeholder hota hai. |
| 10 | `print("Valid Number:", number)` | Valid number print karta hai. |

---

# 3. Lambda Functions

Lambda function ek short one-line anonymous function hota hai. Anonymous ka matlab function ka proper name required nahi hota. Lambda tab useful hota hai jab hume chhota calculation quick way me karna ho, jaise square, discount, sorting key, ya DataFrame column transformation. Large logic ke liye normal `def` function better hota hai, but small quick logic ke liye lambda clean hota hai.

## Practice Code

```python
prices = [100, 200, 300]

discount = lambda price: price * 0.10

for price in prices:
    print("Discount:", discount(price))
```

## Expected Output

```text
Discount: 10.0
Discount: 20.0
Discount: 30.0
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `prices = [100, 200, 300]` | Ye product prices ki list hai. |
| 3 | `discount = lambda price: price * 0.10` | Ye lambda function banata hai jo price ka 10 percent discount calculate karta hai. `price` input hai aur `price * 0.10` output expression hai. |
| 5 | `for price in prices:` | Har price par loop chalata hai. |
| 6 | `print("Discount:", discount(price))` | Current price ko lambda function me pass karta hai aur discount print karta hai. |

---

# 4. String Basics and String Operations

String text data hota hai. Name, email, address, product category, city, review, message, file name sab strings hote hain. Data science me string cleaning bahut important hoti hai because raw data me extra spaces, wrong case, missing symbols, ya inconsistent formatting hoti hai. String operations se hum text ko clean, search, split, join, uppercase/lowercase, replace, and length check kar sakte hain.

## String Basics Individually

String quotes ke andar text hota hai. Single quotes `'Rahul'`, double quotes `"Rahul"`, dono valid hain. String immutable hoti hai, matlab original string direct change nahi hoti; operations mostly new string return karte hain. Real world me names, emails, cities, and comments strings hote hain.

## String Operations Individually

String operations text cleaning aur formatting ke tools hain. `strip()` spaces remove karta hai, `upper()` uppercase banata hai, `lower()` lowercase banata hai, `title()` proper title case banata hai, `replace()` text replace karta hai, `split()` text todta hai, aur `len()` length count karta hai. Data cleaning me ye daily use hota hai.

## Practice Code

```python
name = "  rahul sharma  "

clean_name = name.strip()
title_name = clean_name.title()
upper_name = clean_name.upper()

print("Clean Name:", clean_name)
print("Title Name:", title_name)
print("Upper Name:", upper_name)
print("Total Characters:", len(clean_name))
```

## Expected Output

```text
Clean Name: rahul sharma
Title Name: Rahul Sharma
Upper Name: RAHUL SHARMA
Total Characters: 12
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `name = "  rahul sharma  "` | Ye string variable hai jisme extra spaces hain. Real datasets me aise dirty text common hota hai. |
| 3 | `clean_name = name.strip()` | `strip()` starting aur ending spaces remove karta hai. |
| 4 | `title_name = clean_name.title()` | `title()` har word ka first letter capital karta hai. Name formatting ke liye useful hai. |
| 5 | `upper_name = clean_name.upper()` | `upper()` complete text uppercase me convert karta hai. |
| 7 | `print("Clean Name:", clean_name)` | Cleaned name print karta hai. |
| 8 | `print("Title Name:", title_name)` | Proper title format name print karta hai. |
| 9 | `print("Upper Name:", upper_name)` | Uppercase version print karta hai. |
| 10 | `print("Total Characters:", len(clean_name))` | `len()` string ke total characters count karta hai, spaces inside words included hote hain. |

---

# 5. Lists

List ordered, changeable collection hoti hai. Ordered ka matlab values ka sequence maintain hota hai. Changeable ka matlab hum add, remove, update kar sakte hain. Lists student marks, product prices, names, columns, model predictions, and chart values store karne me use hoti hain.

## Practice Code

```python
students = ["Rahul", "Priya", "Aman"]

students.append("Neha")
students[1] = "Pooja"

for student in students:
    print(student)
```

## Expected Output

```text
Rahul
Pooja
Aman
Neha
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `students = ["Rahul", "Priya", "Aman"]` | Ye list banata hai jisme student names ordered form me store hain. |
| 3 | `students.append("Neha")` | `append()` list ke end me new item add karta hai. |
| 4 | `students[1] = "Pooja"` | Index 1 par value update karta hai. List indexing zero se start hoti hai, so index 1 second item hai. |
| 6 | `for student in students:` | Har student name par loop chalata hai. |
| 7 | `print(student)` | Current student name print karta hai. |

---

# 6. Tuples

Tuple ordered but unchangeable collection hoti hai. Iska matlab values ka order fixed hota hai aur create hone ke baad direct update nahi kar sakte. Tuples fixed data ke liye useful hain, jaise coordinates, RGB color, database record, month names, constant settings. Jab data change nahi hona chahiye, tuple use karna safe hota hai.

## Practice Code

```python
point = (10, 20)

x = point[0]
y = point[1]

print("X Coordinate:", x)
print("Y Coordinate:", y)
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `point = (10, 20)` | Ye tuple hai jo x and y coordinates store karta hai. |
| 3 | `x = point[0]` | Tuple ka first item read karta hai. Index 0 x-coordinate hai. |
| 4 | `y = point[1]` | Tuple ka second item read karta hai. Index 1 y-coordinate hai. |
| 6 | `print("X Coordinate:", x)` | X coordinate print karta hai. |
| 7 | `print("Y Coordinate:", y)` | Y coordinate print karta hai. |

---

# 7. Dictionaries

Dictionary key-value pairs store karti hai. Key unique hoti hai aur value us key ka data hota hai. Real world me dictionary student profile, product details, API response, configuration, and mapping ke liye use hoti hai. Data science me dictionary se column mapping, label mapping, and summary metrics store karte hain.

## Practice Code

```python
student = {
    "name": "Rahul",
    "age": 21,
    "course": "Python"
}

student["city"] = "Delhi"

print("Name:", student["name"])
print("Course:", student.get("course"))
print("Full Data:", student)
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `student = { ... }` | Ye dictionary create karta hai jisme student ka data key-value format me hai. |
| 2 | `"name": "Rahul"` | `name` key ka value `Rahul` hai. |
| 3 | `"age": 21` | `age` key student age store kar rahi hai. |
| 4 | `"course": "Python"` | `course` key student course store kar rahi hai. |
| 7 | `student["city"] = "Delhi"` | Dictionary me new key `city` add karta hai. |
| 9 | `student["name"]` | Direct key access karta hai. Agar key missing ho to error aa sakta hai. |
| 10 | `student.get("course")` | Safe key access karta hai. Missing key par error nahi deta. |
| 11 | `print("Full Data:", student)` | Complete dictionary print karta hai. |

---

# 8. Sets

Set unordered collection hota hai jisme duplicate values allowed nahi hoti. Sets unique values find karne, duplicate remove karne, membership check karne, and common values compare karne me use hote hain. Data cleaning me unique cities, unique categories, unique customer IDs find karne ke liye sets useful hote hain.

## Practice Code

```python
cities = ["Delhi", "Mumbai", "Delhi", "Pune", "Mumbai"]

unique_cities = set(cities)

print("Unique Cities:", unique_cities)
print("Total Unique Cities:", len(unique_cities))
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `cities = [...]` | Ye list hai jisme duplicate city names hain. |
| 3 | `unique_cities = set(cities)` | List ko set me convert karta hai. Set duplicates automatically remove kar deta hai. |
| 5 | `print("Unique Cities:", unique_cities)` | Unique city names print karta hai. Order fixed nahi hota because set unordered hota hai. |
| 6 | `len(unique_cities)` | Unique values ki count nikalta hai. |

---

# 9. Seaborn Basics

Seaborn Python ki data visualization library hai jo Matplotlib ke upar built hai. Ye statistical charts ko simple aur attractive banata hai. Data science me Seaborn EDA ke time useful hota hai because hum trends, comparison, distribution, relationship, and correlation quickly visualize kar sakte hain.

## Practice Code

```python
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")

print(tips.head())
print(tips.info())
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import seaborn as sns` | Seaborn import karta hai. `sns` short alias hai jo common convention hai. |
| 2 | `import matplotlib.pyplot as plt` | Matplotlib pyplot import karta hai. Seaborn charts display/customize karne ke liye Matplotlib use hota hai. |
| 4 | `tips = sns.load_dataset("tips")` | Seaborn ka built-in tips dataset load karta hai. Ye restaurant bills and tips ka sample dataset hai. |
| 6 | `print(tips.head())` | Dataset ke first 5 rows show karta hai. |
| 7 | `print(tips.info())` | Columns, data types, and missing values ka summary show karta hai. |

---

# 10. Line Charts, Bar Charts, Histograms, Scatter Plots

Charts data ko visual form me samjhate hain. Line chart trend show karta hai, bar chart category comparison show karta hai, histogram distribution show karta hai, scatter plot relationship show karta hai. Real projects me charts se business insights nikalte hain.

## Line Charts Individually

Line chart continuous trend show karta hai. Time series data me iska use hota hai, jaise month-wise sales, day-wise temperature, year-wise population. Jab x-axis ka order meaningful ho aur trend dekhna ho, line chart best hota hai.

## Bar Charts Individually

Bar chart categories compare karta hai. Example: day-wise sales, city-wise customers, product-wise revenue. Jab hume categories ke average/total values compare karni ho, bar chart use karte hain.

## Histograms Individually

Histogram numeric column ki distribution show karta hai. Example: house prices kis range me zyada hain, salary distribution kaisi hai, total bills mostly low hain ya high. Histogram data spread and skewness samjhne me help karta hai.

## Scatter Plots Individually

Scatter plot two numeric columns ke relation ko show karta hai. Example: bill badhne par tip badhti hai ya nahi, area badhne par price badhta hai ya nahi. Scatter plot relationship, clusters, and outliers identify karne ke liye useful hai.

## Practice Code

```python
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")

sns.lineplot(data=tips, x="size", y="total_bill")
plt.title("Line Chart - Size vs Total Bill")
plt.show()

sns.barplot(data=tips, x="day", y="total_bill")
plt.title("Bar Chart - Day wise Average Bill")
plt.show()

sns.histplot(data=tips, x="total_bill", bins=10)
plt.title("Histogram - Total Bill Distribution")
plt.show()

sns.scatterplot(data=tips, x="total_bill", y="tip")
plt.title("Scatter Plot - Bill vs Tip")
plt.show()
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import seaborn as sns` | Seaborn charts banane ke liye import hota hai. |
| 2 | `import matplotlib.pyplot as plt` | Chart title aur display ke liye Matplotlib import hota hai. |
| 4 | `tips = sns.load_dataset("tips")` | Sample dataset load karta hai. |
| 6 | `sns.lineplot(...)` | Line chart banata hai. Yaha table size aur total bill ka trend show hota hai. |
| 7 | `plt.title(...)` | Chart ka title set karta hai. |
| 8 | `plt.show()` | Chart screen par display karta hai. |
| 10 | `sns.barplot(...)` | Day wise average total bill compare karta hai. Bar chart categories compare karne ke liye best hai. |
| 14 | `sns.histplot(...)` | Total bill distribution show karta hai. Histogram se pata chalta hai bills mostly kis range me hain. |
| 18 | `sns.scatterplot(...)` | Total bill aur tip ke beech relationship show karta hai. Scatter plot relation/outliers identify karne me useful hai. |

---

# 11. Correlation Matrix

Correlation do numeric columns ke relationship strength ko measure karta hai. Value +1 ke close hai to positive relation strong hai, -1 ke close hai to negative relation strong hai, 0 ke close hai to relation weak hai. Correlation matrix multiple numeric columns ke relation ko table form me show karti hai. Feature selection me correlation useful hota hai.

## Practice Code

```python
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")

numeric_data = tips[["total_bill", "tip", "size"]]

correlation = numeric_data.corr()

print(correlation)

sns.heatmap(correlation, annot=True, cmap="coolwarm")
plt.title("Correlation Matrix")
plt.show()
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 6 | `numeric_data = tips[[...]]` | Sirf numeric columns select karta hai because correlation numeric data par calculate hoti hai. |
| 8 | `correlation = numeric_data.corr()` | Correlation matrix calculate karta hai. Har column ka har column ke saath relation score milta hai. |
| 10 | `print(correlation)` | Correlation values table form me print karta hai. |
| 12 | `sns.heatmap(correlation, annot=True, cmap="coolwarm")` | Correlation matrix ko heatmap me show karta hai. `annot=True` cells ke andar values display karta hai. |
| 13 | `plt.title("Correlation Matrix")` | Chart title set karta hai. |
| 14 | `plt.show()` | Heatmap display karta hai. |

---

# 12. Exploratory Data Analysis and Data Insights

EDA ka matlab dataset ko deeply samajhna. Model banane se pehle hume data shape, columns, data types, missing values, duplicates, summary statistics, outliers, distributions, and relationships check karne hote hain. Data Insights ka matlab EDA ke results ko useful observation me convert karna. Example: "Large bill par tip usually high hoti hai."

## Exploratory Data Analysis Individually

EDA project ka investigation phase hota hai. Is phase me hum dataset ko samajhte hain: rows kitni hain, columns kya hain, missing values kaha hain, numeric summary kya hai, categories ka distribution kaisa hai. EDA ke bina model banana risky hota hai because bad data se bad model ban sakta hai.

## Data Insights Individually

Data Insights EDA ke observations ko meaningful business/student-friendly statements me convert karta hai. Example: "Higher total bill generally gives higher tip." Insight sirf number nahi hota, balki decision-making point hota hai. Dashboard, report, and presentation me insights ka use hota hai.

## Practice Code

```python
import seaborn as sns

tips = sns.load_dataset("tips")

print("Rows and Columns:", tips.shape)
print("Columns:", tips.columns)
print("Missing Values:")
print(tips.isnull().sum())
print("Summary:")
print(tips.describe())

average_tip = tips["tip"].mean()
highest_bill = tips["total_bill"].max()

print("Average Tip:", average_tip)
print("Highest Bill:", highest_bill)
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 3 | `tips = sns.load_dataset("tips")` | Dataset load karta hai jiske upar EDA perform hoga. |
| 5 | `tips.shape` | Dataset me total rows and columns batata hai. |
| 6 | `tips.columns` | Column names show karta hai. |
| 8 | `tips.isnull().sum()` | Har column me missing values count karta hai. |
| 10 | `tips.describe()` | Numeric columns ka summary statistics deta hai, jaise mean, min, max, quartiles. |
| 12 | `average_tip = tips["tip"].mean()` | Tip column ka average calculate karta hai. Ye ek insight point ban sakta hai. |
| 13 | `highest_bill = tips["total_bill"].max()` | Highest bill value find karta hai. |
| 15 | `print("Average Tip:", average_tip)` | Average tip print karta hai. |
| 16 | `print("Highest Bill:", highest_bill)` | Highest bill print karta hai. |

## Example Insights

1. Total bill badhne par tip bhi usually badhti hai.
2. Dinner time par bills lunch se zyada ho sakte hain.
3. Party size badhne par total bill generally increase hota hai.
4. Histogram se bill distribution samajh aata hai.
5. Scatter plot se outliers identify ho sakte hain.

---

# 13. Linear Regression

Linear Regression supervised machine learning algorithm hai. Iska use numeric value predict karne ke liye hota hai. Example: experience se salary predict karna, area se house price predict karna, study hours se marks predict karna. Linear Regression ek straight line fit karta hai jo input feature aur target label ke relationship ko represent karti hai.

Features input columns hote hain. Label/target woh value hoti hai jo predict karni hai. Agar `Hours` input hai aur `Marks` output hai, to model hours ke basis par marks predict karega.

## Practice Code

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

data = {
    "Hours": [1, 2, 3, 4, 5, 6, 7, 8],
    "Marks": [35, 40, 50, 55, 65, 70, 80, 85]
}

df = pd.DataFrame(data)

X = df[["Hours"]]
y = df["Marks"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.25,
    random_state=42
)

model = LinearRegression()
model.fit(X_train, y_train)

print("Model training completed")
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas import karta hai. Dataset table/DataFrame create karne ke liye use hoga. |
| 2 | `from sklearn.model_selection import train_test_split` | Dataset ko training and testing parts me split karne ke liye function import karta hai. |
| 3 | `from sklearn.linear_model import LinearRegression` | Linear Regression model import karta hai. |
| 5 | `data = {...}` | Dictionary form me small dataset create karta hai. |
| 6 | `"Hours": [...]` | Study hours input feature hai. |
| 7 | `"Marks": [...]` | Marks target label hai jo predict karna hai. |
| 10 | `df = pd.DataFrame(data)` | Dictionary ko table/DataFrame me convert karta hai. |
| 12 | `X = df[["Hours"]]` | Feature data select karta hai. Double brackets DataFrame format maintain karte hain, jo sklearn expect karta hai. |
| 13 | `y = df["Marks"]` | Target column select karta hai. Ye actual answers hain. |
| 15 | `train_test_split(...)` | Data ko training aur testing parts me divide karta hai. Model training data se learn karega aur testing data par evaluate hoga. |
| 18 | `test_size=0.25` | 25 percent data testing ke liye rakhta hai aur 75 percent training ke liye. |
| 19 | `random_state=42` | Split ko repeatable banata hai. Same random state se same split milega. |
| 22 | `model = LinearRegression()` | Linear Regression model object create karta hai. |
| 23 | `model.fit(X_train, y_train)` | Model training karta hai. Model hours aur marks ke relationship ko learn karta hai. |

---

# 14. Model Prediction

Model prediction ka matlab trained model se new input ke liye output estimate karwana. Training ke baad model ko new data diya jata hai, aur model learned relationship ke basis par prediction karta hai. Example: agar student 9 hours study karta hai, to marks kitne aa sakte hain?

## Practice Code

```python
predictions = model.predict(X_test)

new_student = pd.DataFrame({"Hours": [9]})
predicted_marks = model.predict(new_student)

print("Test Predictions:", predictions)
print("Predicted Marks for 9 Hours:", predicted_marks[0])
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `predictions = model.predict(X_test)` | Testing features ke liye predicted marks calculate karta hai. Model actual answers nahi dekhta, sirf features se predict karta hai. |
| 3 | `new_student = pd.DataFrame({"Hours": [9]})` | New student ka input DataFrame banata hai. Format training feature ke same hona chahiye. |
| 4 | `predicted_marks = model.predict(new_student)` | New input ke liye marks predict karta hai. Output array form me aata hai. |
| 6 | `print("Test Predictions:", predictions)` | Test dataset ke predictions print karta hai. |
| 7 | `print("Predicted Marks for 9 Hours:", predicted_marks[0])` | New student ke predicted marks print karta hai. `[0]` first prediction value nikalta hai. |

---

# 15. MAE, MSE, and R2 Score

Model evaluation ka matlab model ki performance check karna. Regression me common metrics hain MAE, MSE, and R2 Score.

MAE ka full form Mean Absolute Error hai. Ye average absolute difference batata hai between actual and predicted values. Small MAE better hota hai.

MSE ka full form Mean Squared Error hai. Ye errors ko square karta hai, isliye large errors ko zyada punish karta hai. Small MSE better hota hai.

R2 Score batata hai model target variation ko kitna explain kar pa raha hai. R2 1 ke close ho to model good hota hai. 0 ka matlab model weak hai. Negative bhi aa sakta hai agar model very poor ho.

## MAE Individually

MAE simple average error batata hai. Agar MAE 5 hai, iska rough meaning hai model average 5 marks/units ka error kar raha hai. MAE easy to explain metric hai because unit target jaisi hi hoti hai.

## MSE Individually

MSE errors ko square karta hai. Iska benefit hai ki large errors ko zyada importance milti hai. Agar model kabhi-kabhi bahut wrong prediction karta hai, MSE quickly badh jata hai. MSE model comparison me useful hai, but value target unit squared me hoti hai, isliye beginner ko thodi abstract lag sakti hai.

## R² Score Individually

R² score model ki goodness batata hai. R² 1 ke close ho to model strong relation explain kar raha hai. R² 0 ke close ho to model average guess jaisa perform kar raha hai. Negative R² ka matlab model very poor hai. Reports me R² commonly use hota hai.

## Practice Code

```python
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score

mae = mean_absolute_error(y_test, predictions)
mse = mean_squared_error(y_test, predictions)
r2 = r2_score(y_test, predictions)

print("MAE:", mae)
print("MSE:", mse)
print("R2 Score:", r2)
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `from sklearn.metrics import mean_absolute_error` | MAE calculate karne ka function import karta hai. |
| 2 | `from sklearn.metrics import mean_squared_error` | MSE calculate karne ka function import karta hai. |
| 3 | `from sklearn.metrics import r2_score` | R2 score calculate karne ka function import karta hai. |
| 5 | `mae = mean_absolute_error(y_test, predictions)` | Actual test values aur predicted values ke beech average absolute error calculate karta hai. |
| 6 | `mse = mean_squared_error(y_test, predictions)` | Actual aur predicted values ke beech squared error ka average calculate karta hai. |
| 7 | `r2 = r2_score(y_test, predictions)` | Model ka R2 score calculate karta hai. Ye model ki explanation power batata hai. |
| 9 | `print("MAE:", mae)` | MAE value print karta hai. |
| 10 | `print("MSE:", mse)` | MSE value print karta hai. |
| 11 | `print("R2 Score:", r2)` | R2 score print karta hai. |

---

# 16. Complete Mini Project - Marks Prediction with EDA

Is mini project me Python basics, EDA, Seaborn charts, Linear Regression, prediction, MAE, MSE, and R2 score combine honge. Ye final revision practical hai.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

data = {
    "Hours": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    "Marks": [32, 38, 45, 52, 60, 67, 75, 83, 88, 95]
}

df = pd.DataFrame(data)

print(df.head())
print(df.describe())

sns.scatterplot(data=df, x="Hours", y="Marks")
plt.title("Study Hours vs Marks")
plt.show()

X = df[["Hours"]]
y = df["Marks"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

model = LinearRegression()
model.fit(X_train, y_train)

predictions = model.predict(X_test)

mae = mean_absolute_error(y_test, predictions)
mse = mean_squared_error(y_test, predictions)
r2 = r2_score(y_test, predictions)

new_data = pd.DataFrame({"Hours": [11]})
new_prediction = model.predict(new_data)

print("Predicted Marks for 11 Hours:", new_prediction[0])
print("MAE:", mae)
print("MSE:", mse)
print("R2 Score:", r2)
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1-6 | `import ...` | Required libraries import hoti hain: Pandas data table ke liye, Seaborn/Matplotlib chart ke liye, sklearn model training/evaluation ke liye. |
| 8-11 | `data = {...}` | Small student marks dataset create hota hai. Hours input feature hai aur Marks target value hai. |
| 13 | `df = pd.DataFrame(data)` | Dictionary ko DataFrame table me convert karta hai. |
| 15 | `print(df.head())` | First rows show karta hai taaki data preview ho sake. |
| 16 | `print(df.describe())` | Summary statistics show karta hai. Ye EDA ka part hai. |
| 18 | `sns.scatterplot(...)` | Hours and marks ke relationship ko visualize karta hai. |
| 22 | `X = df[["Hours"]]` | Feature column select karta hai. |
| 23 | `y = df["Marks"]` | Target column select karta hai. |
| 25-30 | `train_test_split(...)` | Data ko train/test me divide karta hai. |
| 32 | `model = LinearRegression()` | Linear Regression model create karta hai. |
| 33 | `model.fit(X_train, y_train)` | Model training karta hai. |
| 35 | `predictions = model.predict(X_test)` | Test data par predictions nikalta hai. |
| 37-39 | `mae`, `mse`, `r2` | Model performance metrics calculate karte hain. |
| 41 | `new_data = pd.DataFrame({"Hours": [11]})` | New input create karta hai jiske liye marks predict karne hain. |
| 42 | `new_prediction = model.predict(new_data)` | New input ke liye predicted marks calculate karta hai. |
| 44-47 | `print(...)` | Final prediction aur evaluation metrics print karta hai. |

## Final Revision Summary

Is revision me aapne programming flow, collections, string cleaning, charts, EDA, insights, regression, prediction, and evaluation metrics ko connect karke dekha. Ye topics interview, classroom practical, mini projects, and data science workflow me baar-baar use hote hain.
