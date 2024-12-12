# Basic Python

<details>

<summary><strong>Naučite hakovanje AWS-a od nule do heroja sa</strong> <a href="https://training.hacktricks.xyz/courses/arte"><strong>htARTE (HackTricks AWS Red Team Expert)</strong></a><strong>!</strong></summary>

Drugi načini podrške HackTricks-u:

* Ako želite videti **oglašavanje vaše kompanije na HackTricks-u** ili **preuzeti HackTricks u PDF formatu** proverite [**SUBSCRIPTION PLANS**](https://github.com/sponsors/carlospolop)!
* Nabavite [**zvanični PEASS & HackTricks swag**](https://peass.creator-spring.com)
* Otkrijte [**The PEASS Family**](https://opensea.io/collection/the-peass-family), našu kolekciju ekskluzivnih [**NFT-ova**](https://opensea.io/collection/the-peass-family)
* **Pridružite se** 💬 [**Discord grupi**](https://discord.gg/hRep4RUj7f) ili [**telegram grupi**](https://t.me/peass) ili nas **pratite** na **Twitter-u** 🐦 [**@hacktricks\_live**](https://twitter.com/hacktricks\_live)**.**
* **Podelite svoje hakovanje trikove slanjem PR-ova na** [**HackTricks**](https://github.com/carlospolop/hacktricks) i [**HackTricks Cloud**](https://github.com/carlospolop/hacktricks-cloud) github repozitorijume.

</details>

## Osnove Pythona

### Korisne informacije

list(xrange()) == range() --> U python3 range je xrange iz python2 (nije lista već generator)\
Razlika između Tuple i Liste je da pozicija vrednosti u tuple-u ima značenje, dok su liste samo uređene vrednosti. Tuple imaju strukturu, dok liste imaju redosled.

### Glavne operacije

Za stepenovanje broja koristite: 3\*\*2 (ne 3^2)\
Ako podelite 2/3, vraća 1 jer delite dva cela broja (integers). Ako želite decimalne vrednosti, trebate deliti float-ove (2.0/3.0).\
i >= j\
i <= j\
i == j\
i != j\
a and b\
a or b\
not a\
float(a)\
int(a)\
str(d)\
ord("A") = 65\
chr(65) = 'A'\
hex(100) = '0x64'\
hex(100)\[2:] = '64'\
isinstance(1, int) = True\
"a b".split(" ") = \['a', 'b']\
" ".join(\['a', 'b']) = "a b"\
"abcdef".startswith("ab") = True\
"abcdef".contains("abc") = True\
"abc\n".strip() = "abc"\
"apbc".replace("p","") = "abc"\
dir(str) = Lista svih dostupnih metoda\
help(str) = Definicija klase str\
"a".upper() = "A"\
"A".lower() = "a"\
"abc".capitalize() = "Abc"\
sum(\[1,2,3]) = 6\
sorted(\[1,43,5,3,21,4])

**Spajanje karaktera**\
3 \* ’a’ = ‘aaa’\
‘a’ + ‘b’ = ‘ab’\
‘a’ + str(3) = ‘a3’\
\[1,2,3]+\[4,5]=\[1,2,3,4,5]

**Delovi liste**\
‘abc’\[0] = ‘a’\
'abc’\[-1] = ‘c’\
'abc’\[1:3] = ‘bc’ od \[1] do \[2]\
"qwertyuiop"\[:-1] = 'qwertyuio'

**Komentari**\
\# Komentar u jednom redu\
"""\
Komentar u više redova\
Još jedan\
"""

**Petlje**

```
if a:
#somethig
elif b:
#something
else:
#something

while(a):
#comething

for i in range(0,100):
#something from 0 to 99

for letter in "hola":
#something with a letter in "hola"
```

### Tuple (n-torka)

t1 = (1, '2', 'tri')\
t2 = (5, 6)\
t3 = t1 + t2 = (1, '2', 'tri', 5, 6)\
(4,) = Singlton (jednočlana n-torka)\
d = () prazna n-torka\
d += (4,) --> Dodavanje u n-torku\
NE MOŽE! --> t1\[1] == 'Nova vrednost'\
list(t2) = \[5, 6] --> Od n-torke u listu

### Lista (niz)

d = \[] prazna\
a = \[1, 2, 3]\
b = \[4, 5]\
a + b = \[1, 2, 3, 4, 5]\
b.append(6) = \[4, 5, 6]\
tuple(a) = (1, 2, 3) --> Od liste u n-torku

### Rečnik (dictionary)

d = {} prazan\
monthNumbers = {1: 'Jan', 2: 'feb', 'feb': 2} --> monthNumbers -> {1: 'Jan', 2: 'feb', 'feb': 2}\
monthNumbers\[1] = 'Jan'\
monthNumbers\[‘feb’] = 2\
list(monthNumbers) = \[1, 2, 'feb']\
monthNumbers.values() = \['Jan', 'feb', 2]\
keys = \[k for k in monthNumbers]\
a = {'9': 9}\
monthNumbers.update(a) = {'9': 9, 1: 'Jan', 2: 'feb', 'feb': 2}\
mN = monthNumbers.copy() #Nezavisna kopija\
monthNumbers.get('ključ', 0) #Provera da li ključ postoji, vraća vrednost monthNumbers\["ključ"] ili 0 ako ne postoji

### Skup (set)

U skupu nema ponavljanja elemenata\
myset = set(\['a', 'b']) = {'a', 'b'}\
myset.add('c') = {'a', 'b', 'c'}\
myset.add('a') = {'a', 'b', 'c'} #Nema ponavljanja\
myset.update(\[1, 2, 3]) = set(\['a', 1, 2, 'b', 'c', 3])\
myset.discard(10) #Ako postoji, ukloni ga, ako ne, ništa\
myset.remove(10) #Ako postoji, ukloni ga, ako ne, izazovi izuzetak\
myset2 = set(\[1, 2, 3, 4])\
myset.union(myset2) #Vrednosti iz myset ILI myset2\
myset.intersection(myset2) #Vrednosti koje se nalaze i u myset i myset2\
myset.difference(myset2) #Vrednosti koje se nalaze u myset ali ne i u myset2\
myset.symmetric\_difference(myset2) #Vrednosti koje se ne nalaze ni u myset ni u myset2 (nisu u oba)\
myset.pop() #Dobij prvi element iz skupa i ukloni ga\
myset.intersection\_update(myset2) #myset = Elementi koji se nalaze i u myset i myset2\
myset.difference\_update(myset2) #myset = Elementi koji se nalaze u myset ali ne i u myset2\
myset.symmetric\_difference\_update(myset2) #myset = Elementi koji se ne nalaze ni u jednom od njih

### Klase

Metoda u \_\_It\_\_ će biti korišćena za poređenje objekata ove klase da li je veći od drugog

```python
class Person(name):
def __init__(self,name):
self.name= name
self.lastName = name.split(‘ ‘)[-1]
self.birthday = None
def __It__(self, other):
if self.lastName == other.lastName:
return self.name < other.name
return self.lastName < other.lastName #Return True if the lastname is smaller

def setBirthday(self, month, day. year):
self.birthday = date tame.date(year,month,day)
def getAge(self):
return (date time.date.today() - self.birthday).days


class MITPerson(Person):
nextIdNum = 0	# Attribute of the Class
def __init__(self, name):
Person.__init__(self,name)
self.idNum = MITPerson.nextIdNum  —> Accedemos al atributo de la clase
MITPerson.nextIdNum += 1 #Attribute of the class +1

def __it__(self, other):
return self.idNum < other.idNum
```

### map, zip, filter, lambda, sorted i jednolinijski kodovi

**Map** je kao: \[f(x) za x u iterabilnom] --> map(tutple,\[a,b]) = \[(1,2,3),(4,5)]\
m = map(lambda x: x % 3 == 0, \[1, 2, 3, 4, 5, 6, 7, 8, 9]) --> \[False, False, True, False, False, True, False, False, True]

**zip** se zaustavlja kada se zaustavi kraći od foo ili bar:

```
for f, b in zip(foo, bar):
print(f, b)
```

**Lambda** se koristi za definisanje funkcije\
(lambda x,y: x+y)(5,3) = 8 --> Koristite lambda kao jednostavnu **funkciju**\
**sorted**(range(-5,6), key=lambda x: x\*\* 2) = \[0, -1, 1, -2, 2, -3, 3, -4, 4, -5, 5] --> Koristite lambda za sortiranje liste\
m = **filter**(lambda x: x % 3 == 0, \[1, 2, 3, 4, 5, 6, 7, 8, 9]) = \[3, 6, 9] --> Koristite lambda za filtriranje\
**reduce** (lambda x,y: x\*y, \[1,2,3,4]) = 24

```
def make_adder(n):
return lambda x: x+n
plus3 = make_adder(3)
plus3(4) = 7 # 3 + 4 = 7

class Car:
crash = lambda self: print('Boom!')
my_car = Car(); my_car.crash() = 'Boom!'
```

mult1 = \[x for x in \[1, 2, 3, 4, 5, 6, 7, 8, 9] if x%3 == 0 ]

### Izuzeci

```
def divide(x,y):
try:
result = x/y
except ZeroDivisionError, e:
print “division by zero!” + str(e)
except TypeError:
divide(int(x),int(y))
else:
print “result i”, result
finally
print “executing finally clause in any case”
```

### Assert()

Ako je uslov netačan, string će biti prikazan na ekranu.

```
def avg(grades, weights):
assert not len(grades) == 0, 'no grades data'
assert len(grades) == 'wrong number grades'
```

### Generatori, yield

Generator umesto da nešto vrati, "yielduje" nešto. Kada mu pristupite, on će "vratiti" prvu generisanu vrednost, a zatim možete ponovo pristupiti i on će vratiti sledeću generisanu vrednost. Dakle, sve vrednosti nisu generisane istovremeno i moguće je uštedeti puno memorije koristeći ovo umesto liste sa svim vrednostima.

```
def myGen(n):
yield n
yield n + 1
```

g = myGen(6) --> 6\
next(g) --> 7\
next(g) --> Greška

### Regularni izrazi

import re\
re.search("\w","hola").group() = "h"\
re.findall("\w","hola") = \['h', 'o', 'l', 'a']\
re.findall("\w+(la)","hola caracola") = \['la', 'la']

**Posebna značenja:**\
. --> Sve\
\w --> \[a-zA-Z0-9\_]\
\d --> Broj\
\s --> Beli prostor karakter\[ \n\r\t\f]\
\S --> Karakter koji nije beli prostor\
^ --> Počinje sa\
$ --> Završava sa\
\+ --> Jedan ili više\
\* --> 0 ili više\
? --> 0 ili 1 pojavljivanje

**Opcije:**\
re.search(pat,str,re.IGNORECASE)\
IGNORECASE\
DOTALL --> Dozvoljava tačku da se poklapa sa novim redom\
MULTILINE --> Dozvoljava ^ i $ da se poklapaju u različitim linijama

re.findall("<.\*>", "\<b>foo\</b>and\<i>so on\</i>") = \['\<b>foo\</b>and\<i>so on\</i>']\
re.findall("<.\*?>", "\<b>foo\</b>and\<i>so on\</i>") = \['\<b>', '\</b>', '\<i>', '\</i>']

IterTools\
**product**\
from **itertools** import product --> Generiše kombinacije između 1 ili više lista, može se ponavljati vrednosti, kartezijanski proizvod (svojstvo distribucije)\
print list(**product**(\[1,2,3],\[3,4])) = \[(1, 3), (1, 4), (2, 3), (2, 4), (3, 3), (3, 4)]\
print list(**product**(\[1,2,3],repeat = 2)) = \[(1, 1), (1, 2), (1, 3), (2, 1), (2, 2), (2, 3), (3, 1), (3, 2), (3, 3)]

**permutations**\
from **itertools** import **permutations** --> Generiše kombinacije svih karaktera na svakoj poziciji\
print list(permutations(\['1','2','3'])) = \[('1', '2', '3'), ('1', '3', '2'), ('2', '1', '3'),... Svaka moguća kombinacija\
print(list(permutations('123',2))) = \[('1', '2'), ('1', '3'), ('2', '1'), ('2', '3'), ('3', '1'), ('3', '2')] Svaka moguća kombinacija dužine 2

**combinations**\
from itertools import **combinations** --> Generiše sve moguće kombinacije bez ponavljanja karaktera (ako postoji "ab", ne generiše "ba")\
print(list(**combinations**('123',2))) --> \[('1', '2'), ('1', '3'), ('2', '3')]

**combinations\_with\_replacement**\
from itertools import **combinations\_with\_replacement** --> Generiše sve moguće kombinacije od karaktera nadalje (na primer, treći se meša od trećeg nadalje, ali ne sa drugim ili prvim)\
print(list(**combinations\_with\_replacement**('1133',2))) = \[('1', '1'), ('1', '1'), ('1', '3'), ('1', '3'), ('1', '1'), ('1', '3'), ('1', '3'), ('3', '3'), ('3', '3'), ('3', '3')]

### Dekoratori

Dekorator koji meri vreme koje je potrebno za izvršavanje funkcije (od [ovde](https://towardsdatascience.com/decorating-functions-in-python-619cbbe82c74)):

```python
from functools import wraps
import time
def timeme(func):
@wraps(func)
def wrapper(*args, **kwargs):
print("Let's call our decorated function")
start = time.time()
result = func(*args, **kwargs)
print('Execution time: {} seconds'.format(time.time() - start))
return result
return wrapper

@timeme
def decorated_func():
print("Decorated func!")
```

Ako ga pokrenete, videćete nešto slično sledećem:

```
Let's call our decorated function
Decorated func!
Execution time: 4.792213439941406e-05 seconds
```

<details>

<summary><strong>Naučite hakovanje AWS-a od nule do heroja sa</strong> <a href="https://training.hacktricks.xyz/courses/arte"><strong>htARTE (HackTricks AWS Red Team Expert)</strong></a><strong>!</strong></summary>

Drugi načini podrške HackTricks-u:

* Ako želite da vidite **vašu kompaniju reklamiranu na HackTricks-u** ili **preuzmete HackTricks u PDF formatu** proverite [**PLANOVE ZA PRETPLATU**](https://github.com/sponsors/carlospolop)!
* Nabavite [**zvanični PEASS & HackTricks swag**](https://peass.creator-spring.com)
* Otkrijte [**The PEASS Family**](https://opensea.io/collection/the-peass-family), našu kolekciju ekskluzivnih [**NFT-ova**](https://opensea.io/collection/the-peass-family)
* **Pridružite se** 💬 [**Discord grupi**](https://discord.gg/hRep4RUj7f) ili [**telegram grupi**](https://t.me/peass) ili nas **pratite** na **Twitter-u** 🐦 [**@hacktricks\_live**](https://twitter.com/hacktricks\_live)**.**
* **Podelite svoje hakovanje trikove slanjem PR-ova na** [**HackTricks**](https://github.com/carlospolop/hacktricks) i [**HackTricks Cloud**](https://github.com/carlospolop/hacktricks-cloud) github repozitorijume.

</details>
