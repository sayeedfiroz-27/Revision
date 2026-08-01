# Python Data Science Revision Notes

## Topics Covered

for Loop, break, continue, pass, Lambda Functions, String Basics, String Operations, Lists, Tuples, Dictionaries, Sets, Seaborn Basics, Line Charts, Bar Charts, Histograms, Scatter Plots, Correlation Matrix, Exploratory Data Analysis, Data Insights, Linear Regression, Model Prediction, MAE, MSE, and R2 Score.

Teacher speaking flow: "Students, ye revision notes aise banaye gaye hain ki aap directly read karke samjha sako. Har topic me pehle concept samjhenge, phir real use case dekhenge, phir practical code run karenge, phir har line ko detail me decode karenge."

## Practice Data Used

Is revision class me hum simple classroom examples and Titanic dataset use karenge. Python basics ke liye marks, names, cities, products jaise small examples use honge, taaki student pehle syntax aur logic easily samajh paaye. Visualization, EDA, correlation, regression, prediction, and model evaluation ke liye local `data/titanic.csv` dataset use hoga. Titanic dataset me passenger survival, class, gender, age, family count, fare, and embarked port jaise columns hote hain. Isse students ko ek hi dataset ke through complete data science flow samajh aayega.

Classroom flow simple rahega: pehle topic ka meaning samjhenge, phir real-world use case dekhenge, phir step-by-step classroom explanation padhenge, phir practical code likhenge, phir expected output/graph reading samjhenge, aur last me code ke har important line ko detail me explain karenge. Is format ka goal ye hai ki first-time learner bhi sirf code copy na kare, balki code ka reason samjhe.

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
| 2 | `-m pip` | Ye part Python ko bolta hai ki `pip` module ko run karo. `pip` Python ka package installer hota hai, jisse external libraries download and install hoti hain. `-m` ka benefit ye hai ki pip same Python environment ke andar run hota hai. Isse version mismatch ka issue kam hota hai. |
| 3 | `install` | Ye command pip ko instruction deti hai ki packages install karne hain. Sirf `pip` run karne se package install nahi hota, `install` action specify karna zaroori hai. Iske baad jo package name ya requirements file aati hai, pip uske according libraries setup karta hai. |
| 4 | `-r requirements.txt` | Ye requirements file se module list read karta hai. Is project me `numpy`, `pandas`, `matplotlib`, `seaborn`, aur `scikit-learn` install honge. |

---

# 1. for Loop

`for loop` ka use tab hota hai jab hume kisi collection ke har item par same kaam repeat karna hota hai. Collection list, tuple, string, dictionary, range, ya dataset rows ho sakti hain. Real world me for loop marks list total karne, names print karne, files process karne, products ka bill calculate karne, aur dataset columns check karne me use hota hai. Jab hume pata ho ki kitni baar loop chalana hai ya hume kisi sequence par one by one jana hai, tab `for loop` best choice hota hai.

Real-world use case: School teacher ke paas 60 students ke marks hain. Teacher ko total aur average marks nikalne hain. Agar teacher manually har mark add karega to time lagega aur mistakes ho sakti hain. `for loop` automatically har mark ko one by one process karta hai aur total calculate karne me help karta hai.

## Step-by-Step Classroom Explanation

For loop ko beginner ko aise samjhao: maan lo aapke paas students ke marks ki list hai. Agar list me 5 marks hain to aap manually 5 baar addition kar sakte ho, lekin agar 500 students hain to manual kaam impossible ho jayega. Yahi problem solve karne ke liye loop use hota hai. Loop ek automatic repeat machine ki tarah kaam karta hai. Hum Python ko bolte hain: "Is list ke har item ko one by one uthao aur same kaam repeat karo."

For loop ka real power ye hai ki code short, clean, aur scalable ho jata hai. Agar list me 5 values hain to loop 5 baar chalega. Agar kal list me 500 values ho gayi, same loop 500 baar chalega, code change nahi karna padega. Data science me for loop columns par operation karne, missing values check karne, files read karne, reports generate karne, aur model outputs process karne me baar-baar use hota hai.

Teacher speaking flow: "Students, for loop ka matlab hai collection ke andar jaana aur har item par same kaam karna. Jaise attendance register me har student ka naam padhna, marksheet me har mark add karna, ya shopping cart me har item ka price total karna."

## Practical Code

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
| 1 | `marks = [78, 85, 90, 66, 92]` | Ye line `marks` naam ki list create karti hai. List me multiple student marks ek hi variable ke andar store ho rahe hain. Square brackets `[ ]` Python ko batate hain ki ye list hai. Real classroom me marks, prices, ages, sales values jaise repeated data ko list me store karna common hota hai. |
| 3 | `total = 0` | Total marks calculate karne ke liye starting value zero set karte hain. Loop ke andar har mark is total me add hoga. |
| 5 | `for mark in marks:` | Ye loop `marks` list ke har item ko one by one `mark` variable me laata hai. Pehli baar `mark = 78`, second time `85`, aur aise continue hota hai. |
| 6 | `total = total + mark` | Ye line current `mark` ko existing `total` me add karti hai. Pehle loop me total 0 hota hai, phir marks one by one add hote jate hain. Is process ko accumulation bolte hain. Real-world me total sales, total marks, total expense calculate karne ke liye yahi pattern use hota hai. |
| 8 | `average = total / len(marks)` | Ye line average marks calculate karti hai. `total` me sab marks ka sum hai, aur `len(marks)` list me total marks count karta hai. Average ka formula hota hai total divided by count. Data analysis me average ek basic summary metric hota hai. |
| 10 | `print("Total Marks:", total)` | Ye line final total marks screen par print karti hai. `"Total Marks:"` ek label hai jo output ko readable banata hai. `total` variable actual calculated value show karta hai. Print statement debugging and result display dono me helpful hota hai. |
| 11 | `print("Average Marks:", average)` | Ye line calculated average print karti hai. `"Average Marks:"` label se student ko samajh aata hai ki output kis value ka hai. `average` variable calculation ka result hold kar raha hai. Is output se teacher quickly class performance explain kar sakta hai. |

## Classroom Teaching Flow After Code

Line 1 me list create hoti hai. Is list ko aap marks register samjho. Line 3 me `total = 0` isliye hai kyunki addition hamesha starting value se start hota hai. Agar starting value set nahi karenge to Python ko pata nahi hoga ki marks kis variable me add karne hain.

Line 5 me `for mark in marks:` ka matlab hai marks list se ek-ek value nikaalo. Har round me current value `mark` variable ke andar aati hai. Line 6 me current mark total me add hota hai. Is line ko loop baar-baar repeat karta hai, isliye final total complete list ka sum ban jata hai.

Line 8 me average nikalta hai. Average ka formula total divided by number of values hota hai. `len(marks)` list me total marks count karta hai. Last two print lines output ko readable format me show karti hain. Beginner ko samjhao ki calculation memory me hoti hai, lekin `print()` se hi user ko result visible hota hai.

---

# 2. break, continue, pass

`break`, `continue`, aur `pass` loop control statements hain. `break` loop ko completely stop karta hai. `continue` current iteration skip karke next iteration par chala jata hai. `pass` kuch nahi karta, bas placeholder ke form me use hota hai. Real use case me `break` tab use hota hai jab target item mil gaya ho, jaise roll number search. `continue` tab use hota hai jab invalid data skip karna ho. `pass` tab use hota hai jab logic baad me likhna hai but code structure abhi ready rakhna hai.

Real-world use case: Data cleaning me kabhi invalid values skip karni hoti hain, kabhi special value milte hi process stop karna hota hai, aur kabhi future code ke liye empty block rakhna hota hai. Example: negative marks skip karo, zero milte hi processing stop karo, aur future validation ke liye `pass` placeholder rakho.

## Step-by-Step Classroom Explanation

Loop normally start se end tak saare items process karta hai, lekin real world me hamesha saare items process karna zaroori nahi hota. Kabhi hume loop stop karna hota hai, kabhi invalid item skip karna hota hai, aur kabhi code block future ke liye empty rakhna hota hai. Yaha `break`, `continue`, aur `pass` help karte hain.

`break` ko "stop button" samjho. Jaise aap list me ek student ka roll number search kar rahe ho. Roll number milte hi search stop ho sakti hai. `continue` ko "skip button" samjho. Jaise marks list me negative marks invalid hain, to negative value skip karke next mark check karna hai. `pass` ko "blank placeholder" samjho. Jab aap structure bana rahe ho but logic baad me likhna hai, tab `pass` code ko error se bachata hai.

## break Individually

`break` ka use tab hota hai jab hume loop ko immediately stop karna ho. Example: agar product list me target product mil gaya, to loop ko aage chalane ki need nahi. Search operations, login attempts, validation checks, and emergency stop conditions me `break` useful hota hai.

## continue Individually

`continue` current item ko skip karke next item par chala jata hai. Example: marks list me negative marks invalid hain, to unko skip karke baaki marks process kar sakte hain. Data cleaning me invalid rows skip karne ke liye `continue` ka use hota hai.

## pass Individually

`pass` kuch nahi karta. Ye placeholder hota hai. Jab hume function, loop, ya condition ka structure banana ho but logic baad me likhna ho, tab `pass` use hota hai. Ye syntax error avoid karta hai.

## Practical Code

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
| 1 | `numbers = [5, 10, -1, 20, 0, 30]` | Ye line sample numbers list create karti hai. Is list me positive number, negative number, zero, and large number mix hain. Aisa mixed data real datasets me common hota hai. Example ka purpose loop control statements ko practical way me samjhana hai. |
| 3 | `for number in numbers:` | Ye line list ke har item par loop chalati hai. Har round me current item `number` variable me store hota hai. Pehle round me `number` 5 hoga, next me 10, next me -1. Loop repetitive checking ke liye use hota hai. |
| 4 | `if number < 0:` | Ye line check karti hai ki current number negative hai ya nahi. `< 0` condition true hogi jab value zero se chhoti hogi. Real data cleaning me negative values kabhi invalid ho sakti hain, jaise negative age ya negative marks. Isliye condition lagakar unwanted values detect karte hain. |
| 5 | `continue` | Ye line current loop round ko skip kar deti hai. Agar number negative hai, to neeche ka code run nahi hoga aur loop next number par chala jayega. Is example me `-1` print nahi hoga. `continue` tab use hota hai jab kuch records ignore karne hote hain but loop stop nahi karna hota. |
| 6 | `if number == 0:` | Ye line check karti hai ki current number exactly zero hai ya nahi. `==` comparison operator hai, assignment nahi. Yaha zero ko stopping point maana gaya hai. Real-world me zero kabhi signal value ho sakti hai, jaise “processing stop”. |
| 7 | `break` | Ye line loop ko completely stop kar deti hai. Agar `number` zero ho gaya, loop aage ke items process nahi karega. Isliye list me zero ke baad jo `30` hai, woh print nahi hoga. `break` tab use hota hai jab required condition mil jaye aur further processing unnecessary ho. |
| 8 | `if number > 25:` | Ye line check karti hai ki current number 25 se bada hai ya nahi. Yaha ye large number condition ka example hai. Is condition ke andar hum future me koi logic add kar sakte hain. Example me ye `pass` ke saath placeholder purpose ke liye use hua hai. |
| 9 | `pass` | `pass` ka matlab hai “abhi kuch mat karo”. Python empty block allow nahi karta, isliye jab future me code add karna ho but abhi block empty rakhna ho, tab `pass` use hota hai. Ye error avoid karta hai. Beginner ko samjhana hai ki `pass` loop ko skip/stop nahi karta, sirf placeholder hai. |
| 10 | `print("Valid Number:", number)` | Ye line valid number print karti hai. Jo number negative nahi hai aur zero se pehle aata hai, woh output me show hota hai. `"Valid Number:"` label output ko readable banata hai. Isse student clearly dekh paata hai ki `continue` aur `break` ka effect kya hua. |

## Classroom Teaching Flow After Code

Line 1 me numbers list hai jisme positive, negative, zero values mix hain. Ye real data jaisa hai jisme valid aur invalid values dono ho sakti hain. Line 3 me loop start hota hai aur har number one by one `number` variable me aata hai.

Line 4 aur 5 invalid data handling dikhate hain. Agar number negative hai to `continue` us number ko skip kar deta hai. Iska matlab negative number ke liye neeche ka print run nahi hoga. Line 6 aur 7 stop condition dikhate hain. Zero milte hi `break` loop ko completely stop kar deta hai. Isliye zero ke baad wali value `30` process nahi hoti.

Line 8 aur 9 `pass` ka use dikhate hain. Ye code ko syntactically valid rakhta hai, lekin kuch action perform nahi karta. Line 10 sirf wahi numbers print karta hai jo skip ya break condition me nahi aaye.

---

# 3. Lambda Functions

Lambda function ek short one-line anonymous function hota hai. Anonymous ka matlab function ka proper name required nahi hota. Lambda tab useful hota hai jab hume chhota calculation quick way me karna ho, jaise square, discount, sorting key, ya DataFrame column transformation. Large logic ke liye normal `def` function better hota hai, but small quick logic ke liye lambda clean hota hai.

Real-world use case: E-commerce website me har product par 10 percent discount calculate karna hai. Agar calculation chhota hai, to lambda se quick discount function bana sakte hain. Pandas me bhi lambda use hota hai jab hume column values ko small rule ke according transform karna hota hai.

## Step-by-Step Classroom Explanation

Lambda function ko beginner ko "one-line shortcut function" bol sakte hain. Normal function banane ke liye `def`, function name, return statement sab likhna padta hai. Lambda me hum chhota logic ek line me likh dete hain. Lekin lambda ka use sirf simple logic ke liye karna chahiye. Agar logic long hai, multiple conditions hain, ya readability important hai, to normal function better hai.

Real world me lambda ka use discount calculate karne, salary tax nikalne, list sorting me custom key dene, aur Pandas DataFrame me column transformation karne ke liye hota hai. Example: product price par 10 percent discount, marks ko grade points me convert karna, ya names ko uppercase karna.

## Practical Code

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
| 1 | `prices = [100, 200, 300]` | Ye line product prices ki list create karti hai. List me teen numeric prices store hain. Real-world shop, billing system, ya e-commerce data me prices list form me aa sakte hain. Lambda function ko test karne ke liye ye simple input data hai. |
| 3 | `discount = lambda price: price * 0.10` | Ye lambda function banata hai jo price ka 10 percent discount calculate karta hai. `price` input hai aur `price * 0.10` output expression hai. |
| 5 | `for price in prices:` | Ye line prices list ke har value par loop chalati hai. Har round me current price `price` variable me aata hai. Isse same discount logic baar-baar manually likhne ki zaroorat nahi padti. Loops and functions saath me repetitive calculation ko easy banate hain. |
| 6 | `print("Discount:", discount(price))` | Ye line current price ko `discount()` lambda function me pass karti hai. Function price ka 10 percent calculate karke return karta hai. `print()` returned discount value screen par show karta hai. Real billing system me har product ka discount isi tarah calculate ho sakta hai. |

## Classroom Teaching Flow After Code

Line 1 me prices list hai. Is list ko shopping cart ke product prices samjho. Line 3 me lambda function ban raha hai. `price` ek input parameter hai. Colon ke baad expression hai jo output return karega. Yaha output price ka 10 percent hai.

Line 5 me loop har price ko one by one process karta hai. Line 6 me current price lambda function ko diya jata hai. Function calculation karta hai aur result print hota hai. Is code se student samjhega ki lambda ek small reusable calculator jaisa kaam kar sakta hai.

---

# 4. String Basics and String Operations

String text data hota hai. Name, email, address, product category, city, review, message, file name sab strings hote hain. Data science me string cleaning bahut important hoti hai because raw data me extra spaces, wrong case, missing symbols, ya inconsistent formatting hoti hai. String operations se hum text ko clean, search, split, join, uppercase/lowercase, replace, and length check kar sakte hain.

Real-world use case: Student registration form me kisi ne name `" rahul sharma "` likha, kisi ne `"RAHUL SHARMA"`, aur kisi ne `"Rahul Sharma"`. Analysis se pehle names ko clean aur standard format me lana zaroori hai. String operations isi cleaning me help karte hain.

## Step-by-Step Classroom Explanation

String ko simple language me "text data" bolte hain. Programming me text bhi data hota hai, aur real world datasets me text data bahut hota hai. Student names, email IDs, city names, product names, customer reviews, gender, category, feedback, address sab strings hote hain. Agar string data dirty hai to analysis galat ho sakta hai. Example: `"Delhi"`, `" delhi "`, `"DELHI"` teenon human ko same lagte hain, lekin Python ke liye ye different strings hain.

Isliye string operations data cleaning ka foundation hain. Jab aap EDA karoge, tab text columns ko clean karna padega. Extra spaces remove karna, text ko lowercase/uppercase me lana, names title case me convert karna, email domain extract karna, product codes split karna, missing text handle karna, ye sab string operations se hota hai.

## String Basics Individually

String quotes ke andar text hota hai. Single quotes `'Rahul'`, double quotes `"Rahul"`, dono valid hain. String immutable hoti hai, matlab original string direct change nahi hoti; operations mostly new string return karte hain. Real world me names, emails, cities, and comments strings hote hain.

## String Operations Individually

String operations text cleaning aur formatting ke tools hain. `strip()` spaces remove karta hai, `upper()` uppercase banata hai, `lower()` lowercase banata hai, `title()` proper title case banata hai, `replace()` text replace karta hai, `split()` text todta hai, aur `len()` length count karta hai. Data cleaning me ye daily use hota hai.

## Practical Code

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
| 1 | `name = "  rahul sharma  "` | Ye line `name` variable me text/string store karti hai. String quotes ke andar likha hua text hota hai. Yaha name ke start and end me extra spaces hain, jo real datasets me form filling ke time common issue hota hai. Is example ka purpose text cleaning samjhana hai. |
| 3 | `clean_name = name.strip()` | Ye line `strip()` method use karke start aur end ke extra spaces remove karti hai. Original `name` variable change nahi hota, cleaned result `clean_name` me store hota hai. Data cleaning me `strip()` very useful hai because spaces ki wajah se matching/searching wrong ho sakti hai. |
| 4 | `title_name = clean_name.title()` | Ye line cleaned name ko title case me convert karti hai. `title()` har word ka first letter capital karta hai, jaise `rahul sharma` ko `Rahul Sharma`. Names, city names, and product names ko presentable banane ke liye ye useful hai. Result `title_name` variable me store hota hai. |
| 5 | `upper_name = clean_name.upper()` | Ye line complete text uppercase me convert karti hai. `upper()` reporting, codes, labels, ya comparison ke time useful ho sakta hai. Example ke liye `rahul sharma` output me `RAHUL SHARMA` ban jayega. Original string direct modify nahi hoti; converted value new variable me store hoti hai. |
| 7 | `print("Clean Name:", clean_name)` | Ye line cleaned name print karti hai. `"Clean Name:"` label output ko understandable banata hai. Student easily compare kar sakta hai ki original string me extra spaces the aur cleaned version me remove ho gaye. |
| 8 | `print("Title Name:", title_name)` | Ye line title case formatted name print karti hai. Output teacher ko dikhata hai ki `.title()` method ka effect kya hai. Reporting ya certificates me names ko properly formatted dikhana important hota hai. |
| 9 | `print("Upper Name:", upper_name)` | Ye line uppercase version print karti hai. Isse `.upper()` method ka output clearly visible hota hai. Data standardization me kabhi-kabhi text ko same case me convert karna zaroori hota hai. |
| 10 | `print("Total Characters:", len(clean_name))` | Ye line cleaned name ke total characters count karti hai. `len(clean_name)` string ki length return karta hai. Start/end spaces remove hone ke baad count accurate hota hai. Character count validation, username length, and form checks me useful hota hai. |

## Classroom Teaching Flow After Code

Line 1 me string ke starting aur ending me spaces intentionally diye gaye hain. Ye beginner ko real dirty data samjhane ke liye hai. Line 3 me `strip()` use hota hai jo string ke dono side ke extra spaces remove karta hai. Isse `"  rahul sharma  "` clean hoke `"rahul sharma"` ban jata hai.

Line 4 me `title()` name formatting ke liye use hota hai. Ye every word ka first letter capital karta hai. Line 5 me `upper()` complete text uppercase me convert karta hai. Ye tab useful hota hai jab hume comparison standard format me karna ho. Lines 7 to 10 results print karti hain. `len(clean_name)` length count karta hai, jisse hum text ka size samajh sakte hain.

---

# 5. Lists

List ordered, changeable collection hoti hai. Ordered ka matlab values ka sequence maintain hota hai. Changeable ka matlab hum add, remove, update kar sakte hain. Lists student marks, product prices, names, columns, model predictions, and chart values store karne me use hoti hain.

Real-world use case: Classroom app me students ke names ek list me store ho sakte hain. Agar new student join karta hai to list me add kar sakte hain. Agar name correction hai to update kar sakte hain. Agar report banana hai to loop se list print kar sakte hain.

## Step-by-Step Classroom Explanation

List ko beginner ko "multiple values ka box" samjhao. Agar aapke paas ek student ka naam hai to simple variable enough hai. Lekin agar class ke 50 student names store karne hain to 50 variables banana bad practice hoga. List ek hi variable me multiple values store karne ka clean way hai.

List ordered hoti hai, isliye items ka sequence important hai. Index zero se start hota hai. First item index 0, second item index 1, third item index 2. List mutable hoti hai, matlab hum item add, remove, replace kar sakte hain. Data science me lists temporary data store karne, loop ke results collect karne, column names store karne, and predictions save karne me use hoti hain.

## Practical Code

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
| 1 | `students = ["Rahul", "Priya", "Aman"]` | Ye line `students` naam ki list create karti hai. List ordered collection hoti hai, matlab values ka order maintain hota hai. Yaha three student names ek hi variable me store hain. Real classroom app me student names, marks, attendance records list me store kiye ja sakte hain. |
| 3 | `students.append("Neha")` | Ye line list ke end me `"Neha"` add karti hai. `append()` method existing list ko update karta hai. Jab new student admission le ya new item add karna ho, append useful hota hai. Output list me Neha last position par aayegi. |
| 4 | `students[1] = "Pooja"` | Ye line index 1 par existing value replace karti hai. Python indexing zero se start hoti hai, isliye index 1 second item ko point karta hai. Pehle second item `"Priya"` tha, ab `"Pooja"` ho jayega. Lists mutable hoti hain, matlab unki values update ki ja sakti hain. |
| 6 | `for student in students:` | Ye line list ke har student name par loop chalati hai. Har round me current name `student` variable me store hota hai. Isse hum sab names ko one by one process kar sakte hain. Attendance printing, certificate generation, ya message sending me yahi pattern use hota hai. |
| 7 | `print(student)` | Ye line current student name print karti hai. Loop ke har round me alag student print hoga. Isse final updated list ka content output me visible ho jata hai. Beginner ko loop ka flow samjhane ke liye ye simple and clear line hai. |

## Classroom Teaching Flow After Code

Line 1 me students list create hoti hai. Is list me 3 names hain aur order fixed hai. Line 3 me `append()` list ke end me new student add karta hai. Ye real class me new admission add karne jaisa hai.

Line 4 me index 1 par value update hoti hai. Since indexing zero se start hoti hai, index 1 second item hai. Yaha `"Priya"` replace hoke `"Pooja"` ban jata hai. Line 6 loop list ke har student par chalta hai. Line 7 current student print karta hai. Isse students ko list iteration clear hoti hai.

---

# 6. Tuples

Tuple ordered but unchangeable collection hoti hai. Iska matlab values ka order fixed hota hai aur create hone ke baad direct update nahi kar sakte. Tuples fixed data ke liye useful hain, jaise coordinates, RGB color, database record, month names, constant settings. Jab data change nahi hona chahiye, tuple use karna safe hota hai.

Real-world use case: Image processing me point coordinate `(x, y)` fixed pair hota hai. Color code `(255, 0, 0)` fixed BGR/RGB values ka group hota hai. Aise values ko accidentally change nahi karna chahiye, isliye tuple safe option hai.

## Step-by-Step Classroom Explanation

Tuple list jaisa dikhta hai, lekin main difference immutability hai. List change ho sakti hai, tuple change nahi hota. Agar data fixed hai aur accidental update avoid karna hai, tuple best hai. Example: image coordinate `(x, y)`, color `(B, G, R)`, latitude-longitude, date parts, fixed settings. OpenCV me coordinates and colors mostly tuple form me diye jate hain.

Beginner ko yaad rakhna chahiye: square brackets `[]` list ke liye, round brackets `()` tuple ke liye. Tuple ka use code ko safer banata hai jab data constant ho.

## Practical Code

```python
point = (10, 20)

x = point[0]
y = point[1]

print("X Coordinate:", x)
print("Y Coordinate:", y)
```

## Expected Output

```text
X Coordinate: 10
Y Coordinate: 20
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `point = (10, 20)` | Ye line `point` naam ka tuple create karti hai. Tuple round brackets `( )` se banta hai. Yaha `10` x-coordinate hai aur `20` y-coordinate hai. Coordinates usually fixed values hote hain, isliye tuple ka use suitable hai. |
| 3 | `x = point[0]` | Ye line tuple ka first item read karti hai. Python indexing zero se start hoti hai, so `point[0]` value `10` return karega. Is value ko `x` variable me store kiya gaya hai. Tuple immutable hota hai, matlab hum value read kar sakte hain but direct change nahi kar sakte. |
| 4 | `y = point[1]` | Ye line tuple ka second item read karti hai. `point[1]` value `20` return karega. Is value ko `y` variable me store kiya gaya hai. Coordinates, RGB colors, fixed config values jaisi cheeze tuple me store karna common hai. |
| 6 | `print("X Coordinate:", x)` | Ye line x-coordinate print karti hai. `"X Coordinate:"` label output ko readable banata hai. `x` variable actual coordinate value show karta hai. |
| 7 | `print("Y Coordinate:", y)` | Ye line y-coordinate print karti hai. `"Y Coordinate:"` label se user ko clearly pata chalta hai ki printed value y-axis ki hai. Is output se tuple indexing ka result verify hota hai. |

## Classroom Teaching Flow After Code

Line 1 me point tuple hai. Isko image coordinate samjho. Point `(10, 20)` ka matlab x coordinate 10 aur y coordinate 20. Line 3 me tuple ka first value read hota hai aur `x` variable me store hota hai. Line 4 me second value `y` variable me store hoti hai.

Lines 6 and 7 coordinates print karti hain. Is example se student indexing and tuple unpacking ka concept samajh sakta hai. Tuple change nahi karna hai, bas read karna hai.

---

# 7. Dictionaries

Dictionary key-value pairs store karti hai. Key unique hoti hai aur value us key ka data hota hai. Real world me dictionary student profile, product details, API response, configuration, and mapping ke liye use hoti hai. Data science me dictionary se column mapping, label mapping, and summary metrics store karte hain.

Real-world use case: Student profile me name, age, course, city alag-alag fields hote hain. Dictionary me ye data readable key-value format me store hota hai. API response aur JSON data bhi mostly dictionary jaisa hota hai.

## Step-by-Step Classroom Explanation

Dictionary ko student ID card ya profile form jaisa samjho. Har field ka naam hota hai aur us field ki value hoti hai. Example: name = Rahul, age = 21, course = Python. List me values sirf order ke basis par milti hain, lekin dictionary me values key ke basis par milti hain. Isse code readable hota hai.

Real world me JSON data mostly dictionary jaisa hota hai. APIs se jo data aata hai wo key-value format me hota hai. Machine learning projects me label mapping, configuration, metrics result, and column rename mapping dictionaries se manage kiye jate hain.

## Practical Code

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

## Expected Output

```text
Name: Rahul
Course: Python
Full Data: {'name': 'Rahul', 'age': 21, 'course': 'Python', 'city': 'Delhi'}
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `student = {` | Ye line `student` naam ka dictionary start karti hai. Dictionary me data key-value pair ke form me store hota hai, matlab har value ka ek naam hota hai. Yaha hum ek student ki details ek hi variable ke andar organize kar rahe hain. Opening curly brace `{` Python ko batata hai ki dictionary data start ho raha hai. |
| 2 | `"name": "Rahul",` | Is line me `"name"` key hai aur `"Rahul"` us key ki value hai. Simple words me, key label jaisa kaam karti hai aur value actual data hota hai. Jab hume student ka naam chahiye hoga, hum `"name"` key se access kar sakte hain. Comma `,` batata hai ki dictionary me next key-value pair bhi aayega. |
| 3 | `"age": 21,` | Yaha `"age"` key student ki age store kar rahi hai. Value `21` integer number hai, isliye quotes nahi lagaye gaye. Real-world dataset me age, marks, salary, price jaise numeric values numbers ke form me store karte hain taaki calculation possible ho. |
| 4 | `"course": "Python"` | Is line me `"course"` key ke andar `"Python"` value store hai. Ye batata hai ki student ka course kya hai. Last key-value pair ke baad comma optional hota hai, isliye yaha comma nahi diya gaya. |
| 5 | `}` | Ye closing curly brace dictionary ko close karta hai. Is line ke baad `student` variable ke andar complete dictionary ready ho jati hai. Beginner ke liye yaad rakhna important hai ki dictionary open `{` se hoti hai aur close `}` se hoti hai. |
| 7 | `student["city"] = "Delhi"` | Ye line existing dictionary me new key add karti hai. `student["city"]` ka matlab hai dictionary ke andar `"city"` naam ka box banana, aur `"Delhi"` us box ki value rakhna. Dictionary flexible hoti hai, isliye baad me bhi new data add kar sakte hain. Real projects me jab extra information milti hai, hum isi tarah new column/key add karte hain. |
| 9 | `print("Name:", student["name"])` | Ye line student ka name print karti hai. `"Name:"` ek normal text label hai jo output ko readable banata hai. `student["name"]` dictionary ke andar se `"name"` key ki value nikalta hai, jo `"Rahul"` hai. Direct key access tab use karo jab sure ho ki key exist karti hai. |
| 10 | `print("Course:", student.get("course"))` | Ye line course print karti hai, lekin yaha `.get()` method use hua hai. `.get("course")` dictionary se `"course"` key ki value safely nikalta hai. Agar key missing hoti, to direct access error de sakta tha, lekin `.get()` generally safer hota hai. Beginner ko batana hai ki real datasets me missing keys/columns aa sakte hain, isliye safe access ka concept important hai. |
| 11 | `print("Full Data:", student)` | Ye line complete dictionary print karti hai. `"Full Data:"` output me label show karega, aur `student` variable poora key-value data show karega. Isse hum verify kar sakte hain ki `"city"` successfully add hui ya nahi. Debugging ke time complete data print karna bahut useful hota hai. |

## Classroom Teaching Flow After Code

Line 1 to 5 dictionary create karte hain. Curly braces `{}` dictionary ke liye use hote hain. Har item me left side key hai aur right side value hai. Key string ho sakti hai, jaise `"name"`, `"age"`, `"course"`.

Line 7 dictionary me new key add karta hai. Iska matlab dictionary flexible hai. Line 9 direct key access dikhata hai. Agar key exist karti hai to value milti hai. Line 10 `.get()` use karta hai, jo safer hai because missing key par error nahi deta. Line 11 complete dictionary print karta hai.

---

# 8. Sets

Set unordered collection hota hai jisme duplicate values allowed nahi hoti. Sets unique values find karne, duplicate remove karne, membership check karne, and common values compare karne me use hote hain. Data cleaning me unique cities, unique categories, unique customer IDs find karne ke liye sets useful hote hain.

Real-world use case: Sales dataset me city names repeated ho sakte hain. Agar manager ko sirf unique cities ki list chahiye jahan sales hui hain, to set use karke duplicates remove kar sakte hain.

## Step-by-Step Classroom Explanation

Set ka sabse important rule hai: duplicates allowed nahi. Agar list me same city 10 baar hai aur hume sirf unique cities chahiye, set instantly duplicates remove kar deta hai. Data cleaning me ye bahut common requirement hai.

Set unordered hota hai, matlab output ka order fixed nahi hota. Isliye set ko order-sensitive data ke liye use nahi karna chahiye. Lekin unique values, membership checking, common/different values compare karne ke liye set fast and useful hota hai.

## Practical Code

```python
cities = ["Delhi", "Mumbai", "Delhi", "Pune", "Mumbai"]

unique_cities = set(cities)

print("Unique Cities:", unique_cities)
print("Total Unique Cities:", len(unique_cities))
```

## Expected Output

```text
Unique Cities: {'Delhi', 'Mumbai', 'Pune'}
Total Unique Cities: 3
```

Note: Set unordered hota hai, isliye cities ka order output me change ho sakta hai.

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `cities = ["Delhi", "Mumbai", "Delhi", "Pune", "Mumbai"]` | Ye line `cities` naam ki list create karti hai. Is list me kuch city names repeat ho rahe hain, jaise `"Delhi"` aur `"Mumbai"` do-do baar aaye hain. Real-world data me duplicates common hote hain, jaise same city, same customer, ya same category repeated ho sakti hai. Is example ka purpose duplicate values ko handle karna samjhana hai. |
| 3 | `unique_cities = set(cities)` | Ye line list ko set me convert karti hai. `set()` ka main kaam unique values rakhna hota hai, isliye duplicate cities automatically remove ho jati hain. `unique_cities` variable me ab sirf unique city names rahenge. Data cleaning me ye technique tab useful hoti hai jab hume unique categories ya unique locations find karni hoti hain. |
| 5 | `print("Unique Cities:", unique_cities)` | Ye line unique cities ko output me print karti hai. `"Unique Cities:"` ek readable label hai, aur `unique_cities` actual set value show karta hai. Set unordered hota hai, isliye output me cities ka order change ho sakta hai. Beginner ko samjhana hai ki set ka focus order par nahi, uniqueness par hota hai. |
| 6 | `print("Total Unique Cities:", len(unique_cities))` | Ye line total unique city count print karti hai. `len(unique_cities)` set ke andar kitni unique values hain, ye count karta hai. Agar output `3` hai, iska matlab raw list me repeated values thi lekin unique cities sirf 3 hain. Data analysis me unique count report, dashboard, aur summary banane me bahut use hota hai. |

## Classroom Teaching Flow After Code

Line 1 me cities list hai jisme duplicate cities repeated hain. Ye raw dataset jaisa hai. Line 3 me `set(cities)` duplicates remove karta hai. Output me Delhi and Mumbai sirf ek-ek baar aayenge.

Line 5 unique cities print karta hai. Student ko batana hai ki set ka order fixed nahi hota, isliye output order change ho sakta hai. Line 6 unique city count print karta hai, jo analysis me useful metric hai.

---

# 9. Seaborn Basics

Seaborn Python ki ek powerful data visualization library hai. Is revision me hum Titanic dataset use karenge. Titanic dataset ek real-world style dataset hai jisme passengers ki information hoti hai, jaise `survived`, `pclass`, `sex`, `age`, `sibsp`, `parch`, `fare`, aur `embarked`. Is dataset ka use karke students visualization, EDA, correlation, regression, prediction, and model evaluation ko ek connected story ke through samjhenge.

Seaborn ka main kaam data ko chart/graph ke form me dikhana hota hai. Jab Titanic dataset table ke form me hota hai, to rows dekhkar pattern samajhna mushkil hota hai. Lekin chart se quickly samajh aata hai ki passenger class ka fare se relation kya hai, age distribution kaisi hai, survival rate male/female me different hai ya nahi, aur fare age ke saath kaise spread ho raha hai.

Is document me Titanic dataset local file `data/titanic.csv` se load hoga. Local CSV ka benefit ye hai ki class me internet ki dependency nahi rahegi. Students same dataset use karenge, same columns dekhenge, aur same code run kar paayenge. Ye teaching ke liye stable and safe approach hai.

## Kab Use Hota Hai

Seaborn tab use hota hai jab hume dataset ke pattern visually samajhne hote hain. Titanic example me agar hume survival rate compare karna hai, age distribution dekhni hai, passenger class wise fare compare karna hai, ya age vs fare relation samajhna hai, Seaborn helpful hota hai.

Seaborn EDA phase me sabse zyada use hota hai. Model train karne se pehle hume data ka behavior samajhna hota hai. Agar chart se pata chale ki `fare` kuch passengers ke liye bahut high hai, to hum outliers ke baare me discuss kar sakte hain. Agar chart se pata chale ki first class passengers ka fare high hai, to hum feature relationship samajh sakte hain.

## Practical Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

titanic = pd.read_csv("data/titanic.csv")

print(titanic.head())
print(titanic.info())
```

## Expected Output

```text
Titanic dataset ke first 5 rows print honge.
Dataset columns, non-null count, and data types ka summary print hoga.
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Ye line Pandas import karti hai. Titanic CSV file ko read karne ke liye Pandas use hoga. `pd` short alias hai, jisse `pd.read_csv()` likhna easy hota hai. |
| 2 | `import seaborn as sns` | Ye line Seaborn import karti hai. Seaborn Titanic dataset par charts banane ke liye use hoga. `sns` industry standard alias hai. |
| 3 | `import matplotlib.pyplot as plt` | Ye line Matplotlib pyplot import karti hai. Seaborn chart banayega, aur `plt.title()` / `plt.show()` chart ko title and display denge. |
| 5 | `titanic = pd.read_csv("data/titanic.csv")` | Ye line local Titanic CSV file load karti hai. `pd.read_csv()` CSV ko DataFrame me convert karta hai. `titanic` variable me complete passenger dataset store hota hai. |
| 7 | `print(titanic.head())` | Ye first 5 rows print karta hai. Isse students columns aur sample values quickly dekh sakte hain. Data analysis start karne se pehle preview zaroor dekhna chahiye. |
| 8 | `print(titanic.info())` | Ye dataset structure print karta hai. `info()` columns, data types, and missing values ka idea deta hai. Titanic dataset me ye step batata hai ki `age` numeric hai, `sex` categorical hai, aur `fare` numeric hai. |

## Classroom Teaching Flow After Code

Teacher speaking flow: "Students, ab hum random example nahi, Titanic dataset use kar rahe hain. Pehle Pandas se CSV load karenge, phir Seaborn se charts banayenge. `head()` se first rows dekhenge aur `info()` se columns ka health check karenge. Ye real data science ka first step hota hai."

---

# 10. Line Charts, Bar Charts, Histograms, Scatter Plots

Charts Titanic dataset ko visual form me samjhane me help karte hain. Line chart trend ya ordered comparison dikhata hai, bar chart categories compare karta hai, histogram numeric distribution dikhata hai, aur scatter plot two numeric columns ke relation ko show karta hai. Titanic dataset me hum `pclass`, `sex`, `age`, `fare`, and `survived` columns ke through charts samjhenge.

## Kab Use Hota Hai

Line chart tab use hota hai jab X-axis ka order meaningful ho. Titanic me passenger class `1`, `2`, `3` ordered category hai, jahan class 1 usually higher class hoti hai. Average fare by passenger class line chart se show kar sakte hain ki class change hone par fare ka trend kaise change hota hai.

Bar chart tab use hota hai jab categories compare karni ho. Titanic me `sex` ke basis par survival rate compare karna useful hai. Bar chart se students quickly dekh sakte hain ki male and female passengers ke survival rates me difference hai ya nahi.

Histogram tab use hota hai jab ek numeric column ka distribution dekhna ho. Titanic me `age` distribution dekhkar samajh aata hai ki passengers mostly kis age group ke the. Histogram missing/dirty data discussion ke liye bhi useful hota hai.

Scatter plot tab use hota hai jab two numeric columns ka relationship dekhna ho. Titanic me `age` aur `fare` ka scatter plot dikhata hai ki different age passengers ne kitna fare pay kiya. Points ka spread outliers and fare variation samjhata hai.

## Practical Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

titanic = pd.read_csv("data/titanic.csv")

average_fare_by_class = titanic.groupby("pclass")["fare"].mean().reset_index()
sns.lineplot(data=average_fare_by_class, x="pclass", y="fare", marker="o")
plt.title("Line Chart - Average Fare by Passenger Class")
plt.show()

sns.barplot(data=titanic, x="sex", y="survived")
plt.title("Bar Chart - Survival Rate by Gender")
plt.show()

sns.histplot(data=titanic, x="age", bins=8)
plt.title("Histogram - Age Distribution")
plt.show()

sns.scatterplot(data=titanic, x="age", y="fare", hue="survived")
plt.title("Scatter Plot - Age vs Fare")
plt.show()
```

## Expected Output

```text
Passenger class wise average fare line chart open hoga.
Gender wise survival rate bar chart open hoga.
Age distribution histogram open hoga.
Age vs fare scatter plot open hoga.
```

## Output / Graph Reading

Line chart me agar class 1 ka fare class 2 and 3 se high dikhe, to insight hoga ki first class passengers generally higher fare pay karte the. Bar chart me survival rate compare hota hai. Histogram me age distribution dikhti hai. Scatter plot me fare outliers and age-fare spread dikhta hai.

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas Titanic CSV load karne aur groupby calculation ke liye use hota hai. |
| 2 | `import seaborn as sns` | Seaborn charts banane ke liye use hota hai. Titanic dataset ke patterns visual form me dikhane ke liye ye main library hai. |
| 3 | `import matplotlib.pyplot as plt` | Matplotlib chart title set karne and chart display karne ke liye use hota hai. |
| 5 | `titanic = pd.read_csv("data/titanic.csv")` | Local Titanic dataset DataFrame me load hota hai. Is DataFrame me passenger records available hain. |
| 7 | `average_fare_by_class = titanic.groupby("pclass")["fare"].mean().reset_index()` | Ye passenger class ke basis par average fare calculate karta hai. `groupby("pclass")` rows ko class wise groups me divide karta hai, `mean()` average fare nikalta hai, aur `reset_index()` result ko clean DataFrame banata hai. |
| 8 | `sns.lineplot(data=average_fare_by_class, x="pclass", y="fare", marker="o")` | Ye average fare by passenger class ka line chart banata hai. `marker="o"` points ko visible banata hai. Isse class wise fare trend clearly dikhta hai. |
| 9 | `plt.title("Line Chart - Average Fare by Passenger Class")` | Ye line chart ka title set karta hai. Title chart ka purpose explain karta hai. |
| 10 | `plt.show()` | Ye line chart screen par display karta hai. |
| 12 | `sns.barplot(data=titanic, x="sex", y="survived")` | Ye gender wise average survival rate bar chart banata hai. `survived` me 0 means not survived and 1 means survived, average survival rate represent karta hai. |
| 13 | `plt.title("Bar Chart - Survival Rate by Gender")` | Ye bar chart ka title set karta hai. |
| 14 | `plt.show()` | Ye bar chart display karta hai. |
| 16 | `sns.histplot(data=titanic, x="age", bins=8)` | Ye age distribution histogram banata hai. `bins=8` age values ko 8 ranges me divide karta hai. |
| 17 | `plt.title("Histogram - Age Distribution")` | Ye histogram ka title set karta hai. |
| 18 | `plt.show()` | Ye histogram display karta hai. |
| 20 | `sns.scatterplot(data=titanic, x="age", y="fare", hue="survived")` | Ye age and fare ka relationship scatter plot me show karta hai. `hue="survived"` survived/not survived points ko different colors me dikhata hai. |
| 21 | `plt.title("Scatter Plot - Age vs Fare")` | Ye scatter plot ka title set karta hai. |
| 22 | `plt.show()` | Ye scatter plot display karta hai. |

---

# 11. Correlation Matrix

Correlation matrix Titanic dataset ke numeric columns ke relationship ko measure karti hai. Titanic me useful numeric columns hain `survived`, `pclass`, `age`, `sibsp`, `parch`, and `fare`. Correlation batati hai ki do numeric columns saath-saath move karte hain ya nahi. Example: `fare` aur `pclass` me negative relation aa sakta hai because lower class number means higher class and usually higher fare.

## Kab Use Hota Hai

Correlation matrix tab use hoti hai jab Titanic jaise dataset me multiple numeric columns hon aur hume quickly relation strength dekhni ho. Survival analysis me hum check kar sakte hain ki `survived` ka `pclass`, `age`, `fare`, ya family size columns se relation kaisa hai.

Feature selection ke time correlation helpful hoti hai. Agar `fare` ka `survived` se positive relation dikhta hai, to model ke liye fare useful feature ho sakta hai. Agar `age` ka relation weak hai, iska matlab ye nahi ki age useless hai, but relation simple linear form me weak ho sakta hai.

## Practical Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

titanic = pd.read_csv("data/titanic.csv")

numeric_data = titanic[["survived", "pclass", "age", "sibsp", "parch", "fare"]]

correlation = numeric_data.corr()

print(correlation)

sns.heatmap(correlation, annot=True, cmap="coolwarm")
plt.title("Titanic Correlation Matrix")
plt.show()
```

## Expected Output

```text
Titanic numeric columns ki correlation values print hongi.
Heatmap open hoga jisme relationship values visible hongi.
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas CSV load karne ke liye import hota hai. |
| 2 | `import seaborn as sns` | Seaborn heatmap banane ke liye use hota hai. |
| 3 | `import matplotlib.pyplot as plt` | Matplotlib title and display ke liye use hota hai. |
| 5 | `titanic = pd.read_csv("data/titanic.csv")` | Titanic CSV local data folder se load hoti hai. |
| 7 | `numeric_data = titanic[["survived", "pclass", "age", "sibsp", "parch", "fare"]]` | Ye only numeric columns select karta hai. Correlation text columns like `sex` and `embarked` par directly calculate nahi hoti. |
| 9 | `correlation = numeric_data.corr()` | `.corr()` selected numeric columns ke beech correlation matrix calculate karta hai. Values -1 se +1 ke beech hoti hain. |
| 11 | `print(correlation)` | Ye exact correlation values table form me print karta hai. |
| 13 | `sns.heatmap(correlation, annot=True, cmap="coolwarm")` | Ye correlation table ko heatmap chart me convert karta hai. `annot=True` values ko cells ke andar show karta hai. |
| 14 | `plt.title("Titanic Correlation Matrix")` | Ye heatmap ka title set karta hai. |
| 15 | `plt.show()` | Ye heatmap display karta hai. |

---

# 12. Exploratory Data Analysis and Data Insights

EDA ka matlab Titanic dataset ko deeply samajhna before model building. Titanic data me passenger class, gender, age, fare, family count, embarked port, and survival information hoti hai. EDA se hum data quality, missing values, average age, highest fare, survival rate, and class-wise behavior samajh sakte hain.

Data Insights ka matlab EDA output ko meaningful statements me convert karna. Example: "First class passengers ne generally higher fare pay kiya", "Female passengers ka survival rate male passengers se high ho sakta hai", ya "Fare me kuch high-value outliers present hain."

## Kab Use Hota Hai

EDA har Titanic analysis project ke start me use hota hai. Model train karne se pehle hume check karna hota hai ki data me missing values hain kya, columns ka type sahi hai kya, and target column `survived` ka distribution kaisa hai.

Data insights tab use hote hain jab hume technical output ko classroom/report language me explain karna ho. Principal, manager, ya beginner student ko code nahi chahiye; unhe clear observation chahiye hoti hai.

## Practical Code

```python
import pandas as pd

titanic = pd.read_csv("data/titanic.csv")

print("Rows and Columns:", titanic.shape)
print("Columns:", titanic.columns)
print("Missing Values:")
print(titanic.isnull().sum())
print("Summary:")
print(titanic.describe())

average_age = titanic["age"].mean()
highest_fare = titanic["fare"].max()
survival_rate = titanic["survived"].mean()

print("Average Age:", average_age)
print("Highest Fare:", highest_fare)
print("Survival Rate:", survival_rate)
```

## Expected Output

```text
Rows and columns print honge.
Columns list print hogi.
Missing value count print hoga.
Summary statistics print hogi.
Average age, highest fare, and survival rate print honge.
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas EDA ke liye import hota hai because CSV load and summary calculations Pandas se karenge. |
| 3 | `titanic = pd.read_csv("data/titanic.csv")` | Titanic dataset local CSV se DataFrame me load hota hai. |
| 5 | `print("Rows and Columns:", titanic.shape)` | `shape` dataset size batata hai: kitni rows and kitne columns. |
| 6 | `print("Columns:", titanic.columns)` | Ye available column names print karta hai. |
| 7 | `print("Missing Values:")` | Ye missing value output ke liye heading print karta hai. |
| 8 | `print(titanic.isnull().sum())` | Har column me missing values count karta hai. Titanic me age ya embarked missing ho sakta hai in larger datasets. |
| 9 | `print("Summary:")` | Summary output ke liye heading print karta hai. |
| 10 | `print(titanic.describe())` | Numeric columns ka count, mean, min, max, and quartiles show karta hai. |
| 12 | `average_age = titanic["age"].mean()` | Passengers ki average age calculate hoti hai. |
| 13 | `highest_fare = titanic["fare"].max()` | Sabse highest fare find hota hai. |
| 14 | `survival_rate = titanic["survived"].mean()` | Survival rate calculate hota hai because survived column me 0 and 1 values hain. Average 1 ka proportion survival rate ban jata hai. |
| 16 | `print("Average Age:", average_age)` | Average age readable label ke saath print hoti hai. |
| 17 | `print("Highest Fare:", highest_fare)` | Highest fare print hota hai. |
| 18 | `print("Survival Rate:", survival_rate)` | Overall survival rate print hota hai. |

## Example Insights

1. First class passengers generally higher fare pay karte hain.
2. Female passengers ka survival rate male passengers se high ho sakta hai.
3. Fare column me high-value outliers ho sakte hain.
4. Age distribution se passenger population ka age range samajh aata hai.
5. Passenger class, fare, and gender survival analysis me useful features ho sakte hain.

---

# 13. Linear Regression

Linear Regression yaha Titanic dataset par numeric prediction ke liye use hoga. Titanic dataset me hum `age` ke basis par `fare` predict karne ka simple regression example lenge. Real Titanic survival prediction normally classification problem hoti hai, lekin Linear Regression samjhane ke liye hume numeric target chahiye. Isliye yaha target `fare` rakha gaya hai.

Feature input column hota hai, target woh numeric value hoti hai jo predict karni hai. Yaha `age` feature hai aur `fare` target hai. Model learn karega ki age ke basis par fare ka pattern kya hai. Ye perfect business model nahi hai, but beginner ko regression workflow samjhane ke liye clear and simple example hai.

## Kab Use Hota Hai

Linear Regression tab use hota hai jab target numeric ho. Titanic dataset me `fare` numeric hai, isliye regression possible hai. Agar target `survived` use karna ho, to woh 0/1 category hai, uske liye Logistic Regression ya classification model better hota hai.

Linear Regression yaha use karne ka purpose algorithm workflow samjhana hai: data load, feature select, target select, train-test split, model train, prediction, and evaluation. Students ko ye bhi batana hai ki model choice target type par depend karti hai.

## Practical Code

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

titanic = pd.read_csv("data/titanic.csv")

titanic = titanic.dropna(subset=["age", "fare"])

X = titanic[["age"]]
y = titanic["fare"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.25,
    random_state=42
)

model = LinearRegression()
model.fit(X_train, y_train)

print("Titanic fare prediction model training completed")
```

## Expected Output

```text
Titanic fare prediction model training completed
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas Titanic CSV load and cleaning ke liye use hota hai. |
| 2 | `from sklearn.model_selection import train_test_split` | Data ko training and testing parts me divide karne ke liye import hota hai. |
| 3 | `from sklearn.linear_model import LinearRegression` | Linear Regression model import hota hai. Ye numeric target predict karta hai. |
| 5 | `titanic = pd.read_csv("data/titanic.csv")` | Titanic dataset local CSV se load hota hai. |
| 7 | `titanic = titanic.dropna(subset=["age", "fare"])` | Ye rows remove karta hai jahan age ya fare missing ho. Regression training ke liye feature and target dono available hone chahiye. |
| 9 | `X = titanic[["age"]]` | Feature data select hota hai. Double brackets DataFrame format maintain karte hain, jo sklearn expect karta hai. |
| 10 | `y = titanic["fare"]` | Target column select hota hai. Model fare predict karna seekhega. |
| 12 | `X_train, X_test, y_train, y_test = train_test_split(` | Train-test split start hota hai. Four outputs milenge: training features, testing features, training target, testing target. |
| 13 | `X,` | Feature data split function ko diya jata hai. |
| 14 | `y,` | Target data split function ko diya jata hai. |
| 15 | `test_size=0.25,` | 25 percent data testing ke liye rakha jata hai. |
| 16 | `random_state=42` | Same split repeat karne ke liye random state fixed hoti hai. |
| 17 | `)` | Train-test split function close hota hai. |
| 19 | `model = LinearRegression()` | Blank Linear Regression model object create hota hai. |
| 20 | `model.fit(X_train, y_train)` | Model training hoti hai. Model age and fare ka relation learn karta hai. |
| 22 | `print("Titanic fare prediction model training completed")` | Training complete hone ka success message print hota hai. |

---

# 14. Model Prediction

Model prediction ka matlab trained Titanic fare model ko new age value dena aur expected fare estimate karwana. Yaha model ko ek new passenger age di jayegi, jaise 30 years, aur model fare estimate karega. Ye estimate exact guarantee nahi hota, bas data pattern ke basis par prediction hota hai.

## Practical Code

```python
predictions = model.predict(X_test)

new_passenger = pd.DataFrame({"age": [30]})
predicted_fare = model.predict(new_passenger)

print("Test Fare Predictions:", predictions)
print("Predicted Fare for Age 30:", predicted_fare[0])
```

## Expected Output

```text
Test Fare Predictions: [...]
Predicted Fare for Age 30: numeric fare value
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `predictions = model.predict(X_test)` | Trained model testing data ke ages ke liye fare predictions nikalta hai. |
| 3 | `new_passenger = pd.DataFrame({"age": [30]})` | New passenger ka input DataFrame create hota hai. Column name `age` training feature ke same hona chahiye. |
| 4 | `predicted_fare = model.predict(new_passenger)` | Model age 30 ke passenger ke liye estimated fare predict karta hai. |
| 6 | `print("Test Fare Predictions:", predictions)` | Test predictions print hoti hain. |
| 7 | `print("Predicted Fare for Age 30:", predicted_fare[0])` | New passenger ki first predicted fare value print hoti hai. |

---

# 15. MAE, MSE, and R2 Score

Model evaluation Titanic fare prediction model ki performance check karta hai. Yaha actual `fare` values and predicted `fare` values compare hongi. MAE average fare error batata hai, MSE large fare errors ko highlight karta hai, aur R2 score model ki explanation power batata hai.

## Kab Use Hota Hai

MAE tab use hota hai jab hume simple language me batana ho ki model average kitna fare error kar raha hai. MSE tab use hota hai jab large wrong fare predictions ko zyada seriously dekhna ho. R2 tab use hota hai jab hume overall check karna ho ki age feature fare pattern ko kitna explain kar pa raha hai.

Titanic example me R2 low aa sakta hai because fare sirf age par depend nahi karta. Fare passenger class, cabin, route, family size, and ticket type par bhi depend kar sakta hai. Ye point students ko feature selection ka importance samjhata hai.

## Practical Code

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

## Expected Output

```text
MAE: fare average error value
MSE: squared fare error value
R2 Score: model explanation score
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `from sklearn.metrics import mean_absolute_error` | MAE function import hota hai. Ye actual fare and predicted fare ka average absolute error calculate karega. |
| 2 | `from sklearn.metrics import mean_squared_error` | MSE function import hota hai. Ye large fare errors ko zyada penalty dega. |
| 3 | `from sklearn.metrics import r2_score` | R2 score function import hota hai. Ye model ki overall explanation power batata hai. |
| 5 | `mae = mean_absolute_error(y_test, predictions)` | Actual test fares and predicted fares compare karke MAE calculate hota hai. |
| 6 | `mse = mean_squared_error(y_test, predictions)` | Actual and predicted fares ka squared error average calculate hota hai. |
| 7 | `r2 = r2_score(y_test, predictions)` | R2 score calculate hota hai. |
| 9 | `print("MAE:", mae)` | MAE value print hoti hai. |
| 10 | `print("MSE:", mse)` | MSE value print hoti hai. |
| 11 | `print("R2 Score:", r2)` | R2 score print hota hai. |

---

# 16. Complete Mini Project - Titanic Fare Prediction with EDA

Is mini project me Titanic dataset use hoga. Project ka purpose hai ek complete beginner-friendly data science workflow build karna: CSV load karna, EDA karna, visualization banana, feature-target select karna, train-test split karna, Linear Regression model train karna, fare prediction karna, and MAE/MSE/R2 se evaluate karna.

## Practical Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

titanic = pd.read_csv("data/titanic.csv")

print(titanic.head())
print(titanic.describe())

sns.scatterplot(data=titanic, x="age", y="fare", hue="survived")
plt.title("Titanic Age vs Fare")
plt.show()

titanic = titanic.dropna(subset=["age", "fare"])

X = titanic[["age"]]
y = titanic["fare"]

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

new_data = pd.DataFrame({"age": [30]})
new_prediction = model.predict(new_data)

print("Predicted Fare for Age 30:", new_prediction[0])
print("MAE:", mae)
print("MSE:", mse)
print("R2 Score:", r2)
```

## Expected Output

```text
Titanic dataset preview print hoga.
Summary statistics print hogi.
Age vs fare scatter plot open hoga.
Predicted fare for age 30 print hoga.
MAE, MSE, and R2 Score print honge.
```

## Detailed Code Explanation

| Line | Code | Explanation |
|---|---|---|
| 1 | `import pandas as pd` | Pandas CSV load and DataFrame operations ke liye import hota hai. |
| 2 | `import seaborn as sns` | Seaborn chart banane ke liye import hota hai. |
| 3 | `import matplotlib.pyplot as plt` | Matplotlib chart title and display ke liye use hota hai. |
| 4 | `from sklearn.model_selection import train_test_split` | Train-test split function import hota hai. |
| 5 | `from sklearn.linear_model import LinearRegression` | Linear Regression model import hota hai. |
| 6 | `from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score` | Evaluation metrics import hote hain. |
| 8 | `titanic = pd.read_csv("data/titanic.csv")` | Titanic dataset local CSV se load hota hai. |
| 10 | `print(titanic.head())` | First 5 rows preview hoti hain. |
| 11 | `print(titanic.describe())` | Numeric summary statistics print hoti hain. |
| 13 | `sns.scatterplot(data=titanic, x="age", y="fare", hue="survived")` | Age vs fare relation scatter plot me show hota hai. `hue` survival status ko color se separate karta hai. |
| 14 | `plt.title("Titanic Age vs Fare")` | Chart title set hota hai. |
| 15 | `plt.show()` | Chart display hota hai. |
| 17 | `titanic = titanic.dropna(subset=["age", "fare"])` | Missing age/fare rows remove hoti hain. |
| 19 | `X = titanic[["age"]]` | Feature column age select hota hai. |
| 20 | `y = titanic["fare"]` | Target column fare select hota hai. |
| 22 | `X_train, X_test, y_train, y_test = train_test_split(` | Train-test split start hota hai. |
| 23 | `X,` | Feature data split ke liye pass hota hai. |
| 24 | `y,` | Target data split ke liye pass hota hai. |
| 25 | `test_size=0.2,` | 20 percent data testing ke liye rakha jata hai. |
| 26 | `random_state=42` | Split repeatable ban jata hai. |
| 27 | `)` | Split function close hota hai. |
| 29 | `model = LinearRegression()` | Blank regression model create hota hai. |
| 30 | `model.fit(X_train, y_train)` | Model age se fare relation learn karta hai. |
| 32 | `predictions = model.predict(X_test)` | Test data ke fare predictions nikalte hain. |
| 34 | `mae = mean_absolute_error(y_test, predictions)` | MAE calculate hota hai. |
| 35 | `mse = mean_squared_error(y_test, predictions)` | MSE calculate hota hai. |
| 36 | `r2 = r2_score(y_test, predictions)` | R2 score calculate hota hai. |
| 38 | `new_data = pd.DataFrame({"age": [30]})` | New passenger age input create hota hai. |
| 39 | `new_prediction = model.predict(new_data)` | New passenger ke liye fare prediction hoti hai. |
| 41 | `print("Predicted Fare for Age 30:", new_prediction[0])` | Predicted fare print hota hai. |
| 42 | `print("MAE:", mae)` | MAE value print hoti hai. |
| 43 | `print("MSE:", mse)` | MSE value print hoti hai. |
| 44 | `print("R2 Score:", r2)` | R2 score print hota hai. |

## Step-by-Step Complete Project Teaching Flow

Teacher speaking flow: "Students, ab hum Titanic dataset se complete ML workflow kar rahe hain. Pehle data load hoga, phir preview and summary dekhenge, phir chart se age and fare relation samjhenge, phir missing values clean karenge, phir age ko feature aur fare ko target banayenge, phir model train hoga, prediction hogi, aur finally metrics se model ki quality check hogi."
