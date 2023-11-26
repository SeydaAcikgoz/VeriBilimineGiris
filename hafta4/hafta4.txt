##### KARAR ve KONTROL YAPILARI #####

#True-False Sorgulamaları

sinir = 5000 #bu bir atama işlemidir

sinir == 4000 # == bu ifade mi sorusudur. sinir 4000 mi sorusuna false cevabı döndürülür

sinir == 5000


5 == 4

5 == 5


#if
#eğer bu şart sağlanıyorsa demektir

sinir = 50000
gelir = 60000

gelir < sinir #küçük mü sorusu

if gelir < sinir:
    print("Gelir sinirdan kucuk")
    
if gelir > sinir:
    print("Gelir sinirdan kucuk")
  

#else
#eğer bu şart sağlanmıyorsa demektir

sinir = 50000
gelir = 35000
    
if gelir > sinir:
    print("Gelir sinirdan buyuk")
else:
    print("Gelir sinirdan kucuk")    

#diger ornek
sinir = 50000
gelir = 50000
    
if gelir == sinir:
    print("Gelir sinira esittir")
else:
    print("Gelir sinira esit degildir")  

#elif
#birden fazla koşul kullanmak için kullanılır
sinir = 50000
gelir1 = 60000
gelir2 = 50000
gelir3 = 35000
    
#aşağıdaki örnekte koşul sayısı 3'e çıktı.iki koşul olsaydı if ve else ile işi halledebilirdik
#3 koşulun ilk ikisini if ve elif ile belirttik geriye kalan durumlarda şunu yap diyerek else ile belirttik.
#Birden fazla koşulumuz varsa bunları if ve elif'ler ile belirtiriz. En sonda ise tüm bu koşulları sağlamıyorsayı belirtmek için en sonda else ifadesini kullanırız.
if gelir1 > sinir:
    print("Tebrikler, hediye kazandiniz.")
elif gelir1 < sinir:  #değilse ama eğer böyleyse demektir
    print("Uyari!")
else:
    print("Takibe devam")  


if gelir3 > sinir: #false dönecek
    print("Tebrikler, hediye kazandiniz.")
elif gelir3 < sinir: #tekrar sorgulanacak true döner bunun aşağısındaki ifadeyi çalıştırıp koşuldan çıkar
    print("Uyari!")
else:
    print("Takibe devam")  


if gelir2 > sinir:  #false dönecek
    print("Tebrikler, hediye kazandiniz.") 
elif gelir2 < sinir: #tekrar sorgulanacak yine false dönecek.
    print("Uyari!")
else:                #yukarıdaki şartlar sağlanamadığı için buraya girecek ve else bloğuna ait kodu çalıştıracak.
    print("Takibe devam")  

#mini uygulama
sinir = 50000
magaza_adi = input("Magaza Adi Nedir?") #input ile kullanıcıdan girdi alıyoruz
gelir = int(input("Gelirinizi Giriniz:"))#kullanıcıdan aldığımız girdiyi integera dönüştürüyoruz

if gelir > sinir:
    print("Tebrikler:" + magaza_adi + " promosyon kazandiniz!")
elif gelir < sinir:
    print("Uyari! Cok dusuk gelir:" + str(gelir))
else:
    print("Takibe devam")

#### DONGULER - for ####
#iteratif işlemleri yerine getrimek için kullandığımız yapılardır

ogrenci = ["ali","veli","isik","berk"] #liste oluşturalım

ogrenci[0] #0. indeksteki öğrenciye erişim
ogrenci[1] #1. indeksteki öğrenciye erişim
ogrenci[2] #2. indeksteki öğrenciye erişim
ogrenci[3] #3. indeksteki öğrenciye erişim

#### for döngü yapısı ####
# for değişken_adı in değişken:
#     yapılacak_işlem
##################################


for i in ogrenci: #for yapısı, öğrenci listesi içerisinde i geçici değişken ile gez
    print(i) #ogrenci listesi içerisindeki i indeks değerlerine karşılık gelen liste elemanlarını yazdır
#i herbir gözlemi gezmek ve yakaladığında onu temsil etmek için kullandığımız geçici değişkendir.
#for - devam

maaslar = [1000,2000,3000,4000,5000]

maaslar[0]
maaslar[1]
maaslar[2]
maaslar[3]
maaslar[4]

for maas in maaslar: #maas gecici degiskeni ile maaslar listesi içerisinde geziyoruz. Maas gecici degiskeni her bir elemanın temsilcisidir.
    print(maas)

#dongu ve fonksiyonları birlikte kullanmak
#maaslara yuzde 20 zam yapilacak gerekli kodlari
#yaziniz.

maaslar = [1000,2000,3000,4000,5000]

def yeni_maas(x):
    print(x*20/100 + x)
    
yeni_maas(1000)
yeni_maas(2000)
yeni_maas(3000)


for i in maaslar:
    yeni_maas(i)
    
###############  mini uygulama  ########################
#if, for ve fonksiyonlari birlikte kullanmak    
#maas 3000 Tl ve üzerinde ise %10 zam yap değil ise yani altında ise %20 zam yap
    
maaslar = [1000,2000,3000,4000,5000]

def maas_ust(x):
    print(x*10/100 + x)

def maas_alt(x):
    print(x*20/100 + x)

for i in maaslar:
    if i >= 3000:
        maas_ust(i)
    else:
        maas_alt(i)
        
###########################################################

#break & continue
#döngüler içerisinde bazen belirli şartı sağlayan ifade yakalandığında (iflerlerle) döngü bitirilmek istenebilir veya bu şartı sağlayan eleman göz ardı edilmek istenebilir.
#bu gibi durumlarda break ve continue ifadeleri kullanılır
        
maaslar = [8000,5000,2000,1000,3000, 7000, 1000]

dir(maaslar) #maaslar listesi üzerinde uygulayabileceğimiz metodları gösterir

maaslar.sort() #maaslar listesini küçükten büyüğe sıraladık
maaslar

for i in maaslar:
    if i == 3000:
        print("kesildi")
        break
    print(i) #for içerisinde 3000'e kadar olanları yazar

#for'a dahil olmayan kod yazmak istersek girinti bırakmadan buradan itibaren yazarız

for i in maaslar:
    if i == 3000:
        continue
    print(i)
#sadece 3000 değeri yazdırılmadı continue ile görmezden gelindi




#while
#olduğu sürece, şart sağlandığı sürece demektir.
sayi = 1

while sayi < 9: #sayı 9'dan küçük olduğu sürece
    sayi += 1 #her iterasyonda üzerine 1 değeri ekleyerek yeniden ata.
    print(sayi) #her iterasyonda sayının değerini yazdır
    
    
#Listeler, Tuple (Demetler), Sözlükler ve Setler için for Döngüsü
#Listeler sıralı , değiştirilebilir ve kapsayıcıdırlar. Listeler için yukarıdaki maas örneğinde olduğu gibidir.
 
#Tuple (Demet), sıralı, değiştirilemez ve kapsayıcıdırlar. Tuple için for;
tup = ("ali","veli",1,2,3) 
type(tup)

for i in tup:
    print(i)
    
#for döngüsü Sözlük(dictionary) için:
    #sözlükler, değiştirilebilir, kapsayıcıdırlar, sırasızdırlar

friends={"Muhsin Mert Karagöz" : 1,
         "Ali Kazankaya" : 2,
         "Burak Alperen Ayaz" : 3,
         "Ali Kanadlı" : 4,
         }

type(friends)

for key, value in friends.items():
    print(key + ":" + str(value))
#karışık verebileceğini unutmamak lazım
 
#for döngüsü Küme(set) için:
    #setler, değiştirilebilir, sırasız+eşsizdir, kapsayıcıdırlar
kume=set([1,2,1,2,3,4,1,2])
type(kume)

for i in kume:
    print(i)
    
#İndeks sırası ile öğelere ulaşım
fruits = ['banana', 'apple',  'mango']

for index in range(len(fruits)):        
   print('Geçerli meyve:', fruits[index]) #index ile ulaşım
   
#range hiçbir değer verilmediğinde 0’dan başlar ve belirli bir sayıya kadar teker teker gider. 
#len komutu nesnenin uzunluğu hakkında bilgi verir. Burada 3 oluncuya kadar index değeri 0’dan başlayıp artar.
#range([start], stop[, step])
#Burada start (başlangıç değeri) ve step (adım değeri) seçimlik parametrelerdir. 
#Eğer sadece 3 değerini verirsek stop (durma değeri) aktive olur ve start otomatik olarak 0 değerini alırken step’te 1 değerini alır. 
#Örneğin range(2, 10, 2) şeklinde bir tanımlamada start=2, stop=10, step=2 değerini alır. range(2, 10) tarzı bir tanımlamada step değeri 1 olur.


##### Python'da Fonksiyonel Programlama #####
#FP'da herşey fonksiyonlardan oluşmaktadır
#FP daha esnek ve bizi daha iyi anlayan bir programlama yaklaşımıdır.
#Python dilini kullanırken bir  program yazacak olduğumuzda bunu nesneye yönelimli programlama özellikleri ile de yazabiliriz, fonksiyonel programlama özellikleri ile de yazabiliriz.

### FP Özellikleri
#Fonksiyonlar dilin bastacidir ve daha esnek bir çalışma yapısı vardır.
#Yan etkisiz fonksiyonlar vardır. (stateless, girdi-cikti) Yani ancak girdi verildiğinde çıktı üretilir.
#Yuksek seviye fonksiyonlar mevcuttur. Vektorel operasyonlar ile daha az çaba ile daha fazla iş yapma imkanı sağlar.
#Yani özetle FP daha esnek ve bizi daha iyi anlayan bir programlama yaklaşımıdır.


#Yan Etkisiz Fonksiyonlar (Pure Functions)

#Ornek1:Bagimsizlik (Yan etki var)

A = 9

def impure_sum(b):#saf olmayan bir takım bağımlılıkları var yani dışarıdan bağımlılığı var (Global tanımlanmış A değişkenine bağlı)
    return b + A


def pure_sum(a,b): #saf yani bağımlılığı yok dışarıdan etki yok. Ancak bir girdi verdiğimizde bir çıktı üretir ve hep aynı sonucu üretir.
    return a + b


impure_sum(6)
pure_sum(3,4)



# #Ornek2: Olumcul yan etkiler
# #OOP
# class LineCounter: # bu kodları bu ders kapsamında bilmemize gerek yok #dosyayı açıp içerisindeki satırları saymak üzere bir sınıf tanımladık
#     def __init__(self, filename): #örnek özelliği tanımladık
#         self.file = open(filename, 'r')
#         self.lines = []
    
#     def read(self): #fonksiyon tanımladık
#         self.lines = [line for line in self.file]
    
#     def count(self):#fonksiyon tanımladık
#         return len(self.lines)


# lc = LineCounter('deneme.txt') #elimizde içeriği okunacak olan deneme.txt diye bir dosya var

# print(lc.lines) 
# print(lc.count())

# lc.read()

# print(lc.lines)
# print(lc.count())

# #sınıf içerisinde bir fonksiyon ile bir işlem yaptık ve bu örneğin değerlleri değişti. Bu bizi rahatsız edici bir durumdur. Nesne yapıları kolayca değişiyor.
# #birde bunu fonksiyonel programlama ile ele alalım.



#FP (Dosya okuma işlemi)

def read(filename): #fonksiyon tanımladık
  with open(filename, 'r') as f:
      return [line for line in f]

def count(lines): #fonksiyon tanımladık
  return len(lines)

example_lines = read('deneme.txt')
lines_count = count(example_lines)
lines_count
#examples lines ve lines_count ancak girdi verildiğinde çıktı üretecek şekilde değişecektir ve başka hiçbir yapıyı etkilemeyecektir.
#Birbirinden bağımsız, birbirlerini etkileyen hiçbir yapı yok.



##### Isimsiz Fonksiyonlar (Anonymous Functions) #####


def old_sum(a,b): #eski tarzda ismi olan bir fonksiyon
    return a + b

old_sum(4,5)


new_sum = lambda a,b: a + b #lambda ile fonksiyon tanımladık
new_sum(4,5)


sirasiz_liste = [('b', 3), ('a', 8), ('d', 12), ('c', 1)]
#sirasiz_liste.sort()

sorted(sirasiz_liste, key = lambda x: x[1]) #liste içerisindeki tuple'ları tuple'ların 1. indeksindeki değerlere göre sırala
                                            #lambda ile fonksiyon tanımladık (x'e bağlı bir fonksiyon, kendi içine girilen değerin 1. değerine ulaşsın)
#bir fonksiyona isimlendirme yapmadan fonksiyonu kullanabiliriz.
#Kullandığımız lambda ifadesindeki x listenin içindeki her bir tupple'a ayrı ayrı erişiyor ve üstünde işlem yapmamızı sağlıyor.
#Yani x değerleri sırasıyla ('b', 3), ('a', 8), ('d', 12), ('c', 1) oluyor ve buradaki x değerlerinin x[1] leri de integer değerler olarak dönüyor.

sorted()


#### Vektorel Operasyonlar (Vectorel Operations) ####
#Klasik olarak yapalım
a = [1,2,3,4] #liste oluşturduk.
b = [2,3,4,5]

#iki liste içerisindeki her elemanı birbiri ile çarpalım

ab = [] #çarpma sonuçlarını tanımlamak için global alanda boş bir liste oluşturduk
a*b	#hata

range(0, len(a)) #0'dan a'nın içinde ne kadar eleman varsa o aralık
for i in range(0, len(a)): #0'dan a'nın içinde ne kadar eleman varsa o kadar gezin
    ab.append(a[i]*b[i])

ab


#FP ile aynı işlemi yapalım

import numpy as np # numpy isimli bir modülü (kütüphaneyi) çalışma dizinimize dahil et ne buna np ismini ata
a = np.array([1,2,3,4]) #numpy array oluştur 
b = np.array([2,3,4,5]) #numpy array oluştur 
#aynı a, b 'yi baştan oluşturduk
a*b #elemanları tek tek gezmeden tüm elemanlar üzerinde çarpma yaptık

#Bu işlem vektörel bir işlemdir


#### map & filter & reduce #### 

liste = [1,2,3,4,5] #liste oluşturduk

for i in liste: #listenin her bir elemanına 10 ekliyoruz ve ekrana yazdırıyoruz
    print(i+ 10)


###map(fonksiyon, veri):
#Türkçe anlamı haritalamak demektir. 
#Yaptığı iş şudur: herhangi bir fonksiyonu, belli verilere, bir bir uygular. Belirtilen fonksiyonu, verilen verilere uygular.
#Aldığı parametreler: fonksiyon, veri.


list(map(lambda x: x+10, liste)) #fonksiyonlara fonksiyon ekliyoruz
                                 #map fonksiyonu verilen bir vektörün içerisinde bir fonksiyonu çalıştırma imkanı verir. lambda ile isimsiz fonksiyon tanımlanır ve bu fonksiyon liste'ye uygulanır.
                                 #verilen bir nesne üzerinde bir fonksiyonu çalıştırma imkanı verir
                                 #en dıştaki list sonucu listeler


#isimsiz fonksiyon yerine normal fonksiyon ile yapsaydık
def topla(a):
    return a+10

liste = [1,2,3,4,5]
b=map(topla,liste);
print(list(b))



#filter
# Verilen nesne içerisinde aradığı şartı sağlayan tüm elemanlar filtrelenir.
#Belirtilen fonksiyonu, verilen verilere uygularken verileri filtreler. Bunun için de fonksiyona şart koşar:
liste = [1,2,3,4,5,6,7,8,9,10]

list(filter(lambda x: x % 2 == 0, liste)) #2'ye tam bölünenleri filtreledi bize geri döndürdü, normalde klasik programlamada döngü ve if kullanmamız gerekirdi

#reduce
#Parametre olarak verilen veri yapısına, belirtilen fonksiyonu uygularken sonuçları biriktirir. 
#Yani verilere belirtilen fonksiyonu uygulayarak, verileri tek bir veri haline getiriyor. 
#Verileri azaltıyor…

#from functools import reduce ->burada functools kütüphanesi içindeki reduce fonksiyonu import edildi 
#import functools as fn -> burada functools kütüphanesi tamamen import edildi

from functools import reduce #modül içerisinden fonksiyon import ettik

liste = [1,2,3,4]
reduce(lambda a,b: a + b, liste)# a ve b'ye bağlı isimsiz bir fonksiyon tanımladık liste üzerinde 

#bu fonksiyonlar lambda isimsiz fonksiyonları kullanılar ve vektörel işlemler yapmamızı sağlarlar

#Fp, işlerimizi daha kolay hale getiren daha az yan etkileri olan programlardır.


#import functools as fn
#fn.reduce(lambda a,b: a + b, liste)


# ##### Modul Olusturmak #####
#Belirli amaçları yerine getirmek için bir arada bulunan fonksiyonlar topluluğudur.
#Bazen modul, bazen kütüphane bazen de paket olarak isimlendirilebilir.

#HesapModulu.py
def yeni_maas(x):
    print(x*20/100 + x)
    
maaslar = [1000,2000,3000,4000]  


#test
import HesapModulu 
HesapModulu.yeni_maas(1000) #içerisindeki fonksiyon çağırılıyor


import HesapModulu as hm
hm.yeni_maas(2000)

from HesapModulu import yeni_maas #Modülden yalızca fonksiyon import ediliyor
yeni_maas(3000)

import HesapModulu as hm
hm.maaslar #hesap modulu içerisindeki nesne çağırılıyor

from HesapModulu import maaslar #Modülden yalızca nesne import ediliyor
maaslar 


#### Hatalar / istisnalar (exceptions) ####
#Hata yönetimi programcılık açısından önemlidir.
#-->Kullanıcı (programcı) hataları, söz dizimi hataları, yakalanabilecek hatalardır.
#-->Program (bug) hataları zor hatalardır; kritik hatalardır. Testerlar ile olası problemler gözlemlenmeye çalışılır.
#-->istisnalar (exceptions) programda gözlemlediğimiz bazı hatalar bu hatalar geldiğinde çalışmayı durdurma devam ettir diyebiliriz. 

#ZeroDivisionError hatasi
a = 10
b = 0

a/b #hata: paydada 0 olamaz. Buna bir önlem koyabiliriz. try, excep yapısıdır.


try: #dene demek
    print(a/b)
except ZeroDivisionError: #  hata türü ile except kullanıldı. Dene eğer çalışmazsa bunu istisna olarak gör dışarıda bırak çalışmayı devam ettir.
    print("Payda da sifir olmaz")


#tip hatasi
    
a = 10    
b = "2"

a / b #int ve str tiplerini matematiksel bir ifadeye sokuyoruz tip hatası alırız

try:
    print(a/b)
except TypeError:
    print("Sayi ve string problemi")




a = 10    
b = 2

a / b

try:
    print(a/b)
except TypeError:
    print("Sayi ve string problemi")

