# PHYTON TEMELLERİ
> 💡 **Bilgilendirme (WIP 🚧):** Bu doküman, *Bro Code* kanalının eğitim serisi referans alınarak oluşturulmuştur.
>  Öğrenme hızını ve pratikliği kesmemek adına notlar şu aşamada İngilizce ve Türkçe terimlerin bir karışımı halindedir,ilerleyen süreçte içerik düzenlenecektir.


__________________________________________________________________________________________________________________________________________________________________
 
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
print(f"You are {Age} years old") #  You are 25 years old
print(f"gpa: {Gpa}") # gpa: 3.2
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
print(type(name)) #  <class ‘str’>
gpa=int(gpa)   
print(gpa) #  3
age=float(age)
print(age) #  20.0
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





  


