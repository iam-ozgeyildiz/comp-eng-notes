# PHYTON TEMELLERİ
> 💡 **Bilgilendirme (WIP 🚧):** Bu doküman, *Bro Code* kanalının eğitim serisi referans alınarak oluşturulmuştur.
>  Öğrenme hızını ve pratikliği kesmemek adına notlar şu aşamada İngilizce ve Türkçe terimlerin bir karışımı halindedir,ilerleyen süreçte içerik düzenlenecektir.

---
 
### **VARIABLES**

**Strings**
```Python
first_name="özge"
food='pizza'
```
->String için tek tırnak veya çift tırnak kullanılabilir


```Python
print(first_name) #  özge
print("first_name") # first_name
print( f"Hello {first_name}" ) # -> Hello özge
```


**Integer ,float**

```Python
Age= 25
Gpa=3.2
print(f"You are {Age} years old") #  You are 25 years old
print(f"gpa: {Gpa}") # gpa: 3.2
```
**Boolean**

` is_Student= True # / False `
->First letter is capital for True and False

```Python
if is_Student:
    print("u r a student")
else:
    print("u r not  student") 
```

-> if yazıp 2. Satıra geçtiğinde em az bir kere space e basmayı unutma, yoksa istediğin işlem yapılmaz.
Standart 4 kez basmakmış(ide kendisi de yapıyo olabilir diye tahmin ediyorum bunu)
use (#) hashtag for comment lines

### TYPE CASTING

str() ,int(),float(),bool()
you can get the type of a variable or value with the type() function.

```Python
name="özge"
age=20
gpa=3.2
print(type(name)) #  <class ‘str’>
gpa=int(gpa)   
print(gpa) #  3
age=float(age)
print(age) #  20.0
age=str(age)
print(type(age)) #  <class ‘str’> (artık variable türü değişti)
# age += 1 -> hata verir string e integer ekleyemez
age +="1" #  age= "251" şeklinde bir string oluştu
name=bool(name) # -> String  in içi dolu ise True, içi boş “” ya da’’ şeklinde ise False verir.
```

### USER INPUT

We use input function to get data from the user.

`name=input("What is your name? :") `
Terminalde what is your name? : yazar ve yanınsa ismi gireriz. Otomatik olarak string alınır, eğer int kullanmak istersek type casting yapmalıyız.
Ancak bunu ayrı ayrı yapmak yerine ;


`age=int(input("type your age:  ")) # şeklinde yapabiliriz`

###ARITHMETIC & MATH

```Python
friends=5
friends=friends + 1 # friends +=1
friends=friends - 1 # friends  -=1
friends=friends * 2 # friends  *= 2
friends=friends / 5 # friends /= 5
friends=friends **2 # friends **=2
friends%2 # 1 kalanını verir.

X= 3.14521
Y=-4
Z=5
result =round(x,2) # print(result) --> 3,14 
```
girdiğimiz ikinci rakam virgülden sonra kaçıncı basamağa kadar yuvarlayacağımız söyledi. 
Hiçbir şey girmese idik otomatik olarak en yakın olan sayıya yuvarlardı. Bu durumda 3 e yuvarlandı

```Python
result=abs(y) # print(result) #  --> 4
result=pow(3,2) # print(result)#  --> 9 
max(x,y,z,) # print(result)# --> 5
min(x,y,z) # print(result)# --> 4
```
import math
math.pi , math.e ,    math.sqrt(x) # (karekök alma)   ,   math.ceil(x)  ,  math.floor(x)

### IF STATEMENTS

if kosul1  :
     # kosul1 doğru ise yapılacak(başta boşluk bırakmayı unutma)
elif kosul2:
     # koşul 2 doğru ise yapılacak olan
else:
     # hiçbiri doğru değil ise yapılacak ( yine boşluk olmalı)
String için de == sorgusu kullanılabiliyor.Java dan daha farklı, nesne tabanlı olmaması ile alakalı olabilir

### LOGICAL OPERATORS
  * OR

  ```Python
  temp= 25
  is_raining=False 
  if temp>35 or temp<0 or is_raining :
      print("The outdoor event is cancelled")
  else:
      print ("The outdoor event is still scehduled")
  ```
  Output and explanation:
  -The outdoor event is still scheduled
  -The or logical operator means for the condition to be count true(1), at least one of the multiple conditions must be true.
  If is_raining equaled to true, output would be “the outdoor even is cancelled”

  * AND

  ```Python
  temp= 30
  is_sunny=True 
  if temp>=28 and  is_sunny :
      print("It is HOT outside")
      print("It is sunny")
  elif temp <=0 and is_sunny :
      print("ıt is cold outside")
  ```
    
  Output and explanation:

  -It is HOT outside
  -It is sunny
  ->With the and logical operator all conditions must be true in order to execute to code block of interest.

  To see if a value is in a certain range ve can check it this way:

  ```Python
  if temp<28 and temp> 0 :
  # Or this way:    
  if 28 > temp > 0 : # (we cant do this in java)
  ```

  * NOT

  ```Python
  temp= 25
  is_raining=False 
  if temp>23  and not   is_raining :
      print ("The outdoor event is still scehduled")
  ```
  Output and explanation:
  -The outdoor event is still scheduled
  ->The not logical operator means we take the opposite of whats given
  is_raining is False
  So not is_raining is true and the code is excecuted

*NOT:  Notlar çalışma sırasında word üzerinden alınıp,daha sonrasında mevcut dökümana eklenmektedir.*

### CONDITIONAL EXPRESSIONS
A one line shortcort for the if else statement, used to print or assign one of the two values based on a condition
Syntax is -> X if condition else Y

```Python
num=5
print(“Positive” if num>0 else “Negative”)

result=”EVEN” if num%2==0 else “ODD”
print(result)

a=6 
b=7
max_num=a if a>b else b
print(max_num)

```
Output and explanation:
-Positive (5 is greater than 0 so it prints "5")
-ODD ( 5 is an odd number)
-7 (a isnt greater than b so it prints b)

### STRING METHODS

`name= “aziz sancar”`
`len(name)`-> 11'  (string uzunluğunu verir boşluğu da alır)
`name.find(“z”)` -> 1 ( string deki ilk z nin indexini döndürür,indexler 0 dan başlar)
`name.rfind(“a”)` -> 9 (last accurance of a)
for both methods(find() and rfind()), if phyton isnt able to find the given character, it will return -1

`name= name.capitalize()` ->Aziz sancar
`name=name.upper()` -> AZİZ SANCAR
`name=name.lower()` -> aziz sancar

`name.isdigit()` -> result is a boolean if the string consists of only digits(numbers) it turns True, otherwise returns false

`name.isalpha()` if String consists of only alphabetical characters, it will return True.In this stiuation it will return False since space “   “ isnt an alphabetical character
name.count(a) -> 3 (returns the number of the said character)
name.replace(“a” ,  “o” ) -> oziz soncor
name.replace(“a” , “”) ->  ziz sncr

### STRING INDEXING

Indexing is Accessing elements of a sequence using []
[] is indexing operator
[start : end : step ]
```Python
credit_number=1234-5678-9012-3456
print( credit_number[0] ) # 1
print( credit_number[4] ) # -
```
If you have just one field listed without any columns ( : ) its assummed you are filling in the starting position.
For first four digits:
```Python
Print ( credit_number[0:4] ) # 1234( ending index is not included, if you write 0:4 it takes indexes 0,1,2,3)
Print(credit_number[:4] # 1234 , phyton asuumes the starting position will be the beginning of the string
```

```Python
Print(credit_number[5:] # output: 5678-9012-3456
#if you need everything from the starting index  down to the end of a string, you dont need to #specify the ending index, just leave a column : after the starting index.
#You can also use negative indexes last char of the string is index -1
#Using the step field we can count by twos, threes and so on
Credit_number[: : 2] ->13_6891-46
Credit_number[:: -1] if you set the step to -1 it will reverse the string
```


### FORMAT SPECIFIERS {value: flags}

Format a value based on what flags are inserted
.(number)f       ->  round to that many decimal places (fixed point)
:(number)        ->  allocate that many spaces
:03	             ->  allocate and zero pad that many spaces
:<	              ->  left justify (sola dayalı)
:>             	 ->  right justify (sağa dayalı metin)
:^             	 ->  center align (ortaya hizalı)
:+             	 ->  use a plus sign to indicate positive value
:=             	 ->  place sign to leftmost position
:	               ->  insert a space before positive numbers
:,             	 ->  comma seperator


EXAMPLES AND EXPLANATIONS
____________________________________________________________________________________________________

```Python
Price1= 3.14159
Price2 = -987,65
Price3= 12.34
Print(f”Price 1 is {price1:.2f}”)
Print(f”Price 2 is {price2:.3f}”)
Print(f”Price 3 is {price1:.2f}”)
```
Output and explanation
  * 3.14
  * -987.650 
  * Added zeros so its three decimals after the point
  *12.34
---

```Python
Price1= 3.14159
Price2 = -987,6
Price3= 12.34
Print(f”Price 1 is {price1:10}”)
Print(f”Price 2 is {price2:10}”)
Print(f”Price 3 is {price1:10}”)

```
Output and explanation
  * Each value now has a total of 10 spaces
  *   3.14159
  *    -987,6
  *     12.34

---

```Python
Price1= 3.14159
Price2 = -987,65
Price3= 12.34
Print(f”Price 1 is {price1:010}”)
Print(f”Price 2 is {price2:010}”)
Print(f”Price 3 is {price1:010”)

```
Output and explanation
  * The spaces are replaced with zeroes
  * 0003.14159
  * -0000987.65
  * 0000012.34

---

```Python
Price1= 3.14159
Price2 = -987,65
Price3= 12.34
Print(f”Price 1 is {price1:<10}”)
Print(f”Price 2 is {price2:>10}”)
Print(f”Price 3 is {price1:^10}”)

```
Output and explanation
  * 3.14159___  
  * ___-987.65
  * __12.34___
 **!!**_ is used to indicate the spaces, normally it would look like:  12.34    sso it wouldnt be really obvious.


---

```Python

Price1= 3.14159
Price2 = -987,65
Price3= 12.34
Print(f”Price 1 is {price1:+}”)
Print(f”Price 2 is {price2:+}”)
Print(f”Price 3 is {price1:+}”)

```
Output and explanation
  *  +3.14159
  *  -987,65
  *  +12.34

---

```Python
Price1= 3000.14159
Price2 = -9870,65
Price3= 1200.34
Print(f”Price 1 is {price1: , }”)
Print(f”Price 2 is {price2: ,}”)
Print(f”Price 3 is {price1: ,}”)

```
Output and explanation
Each thousand brake is seperated with a comma
  * price 1 is  3,000.14159
  * price 2 is -9,870.65
  * price 3 is  1,200.34

You can use them combined too:  print({price1:+, .2f}) -> +3,000.14
---


  


