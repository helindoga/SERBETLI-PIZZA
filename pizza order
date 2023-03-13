
import csv
import datetime


with open("Menu.txt", "w") as f:
  f.write("Pizzanizi seciniz.\n")
  f.write("1: Klasik\n")
  f.write("2: Margarita\n")
  f.write("3: Turk Pizza\n")
  f.write("4: Sade Pizza\n")
  f.write("Sosunuzu seciniz.\n")
  f.write("11: Zeytin\n")
  f.write("12: Mantar\n")
  f.write("13: Keci Peyniri\n")
  f.write("14: Et\n")
  f.write("14: Sogan\n")
  f.write("16: Misir\n")




class pizza:
    def __init__(self,tanim = None,cost = None):
        self.tanim=tanim
        self.cost=cost  

    def get_tanim(self):
       return f'{self.tanim}'

    def get_cost(self):
       return f'{self.cost}' 
    




class KlasikPizza(pizza):
  def __init__(self,tanim,cost):
    super().__init__(tanim,cost)
    self.tanim = "Pizza sosu, mozarella peyniri, sucuk, mantar, biber ve misir."
    self.cost = 100.0



class Margarita(pizza):
  def __init__(self,tanim,cost):
    super().__init__(tanim,cost)
    self.tanim = "Pizza sosu ve mozarella peyniri."
    self.cost = 80.0

class TurkPizza(pizza):
  def __init__(self,tanim,cost):
    super().__init__(tanim,cost)
    self.tanim = "Pizza sosu, mozarella peyniri, domates sosu, pastirma, zeytin, köz biber ve sucuk."
    self.cost = 110.0

class SadePizza(pizza):
  def __init__(self,tanim=None,cost=None):
    super().__init__(tanim,cost)
    self.tanim = "Pizza sosu, mozarella peyniri, sosis, zeytin ve misir."
    self.cost = 90.0


class sos(pizza):
   def __init__(self,tanim,cost,pizza = None,sos=None):
     super().__init__(tanim,cost)
     self.pizza = pizza
     self.sos = sos
   
   def get_tanim(self):
    return self.sos.get_tanim() + "," + pizza.get_tanim()
   def get_cost(self):
    return self.sos.get_cost + pizza.get_cost

class ZeytinSos(sos):
   def __init__(self, pizza=N):
    super().__init__(self,pizza)
    self.get_cost = 5.0
    self.get_tanim='zeytin soslu'
   
    
class MantarSos(sos):
  def __init__(self, pizza):
    super().__init__(pizza, self)
    self.tanim = "Mantar Sosu"
    self._cost = 8.0


class KeciPeyniriSosu(sos):
  def __init__(self, pizza):
    super().__init__(pizza, self)
    self.tanim = "Keci Peyniri Sosu"
    self._cost = 9.0

class EtSosu(sos):
  def __init__(self, pizza):
    super().__init__(pizza, self)
    self.tanim = "Et sosu"
    self._cost = 11.0

class SoganSosu(sos):
  def __init__(self, pizza):
    super().__init__(pizza, self)
    self.tanim = "Sogan Sosu"
    self._cost = 4.0

class MisirSosu(sos):
  def __init__(self, pizza):
    super().__init__(pizza, self)
    self.tanim = "Misir Sosu"
    self._cost = 6.0
   
  
def pizza_sec():
  print("Pizzanızı seciniz.")
  print("1: Klasik\n2: Margarita\n3: Turk Pizza\n4: Sade Pizza\n")
  choice = int(input("Secim: "))
  if choice == 1:
    pizza = KlasikPizza()
  elif choice ==2:
    pizza = Margarita()
  elif choice == 3:
    pizza = TurkPizza()
  elif choice == 4:
    pizza = SadePizza()
  else:
    print("Hata!")
 



      
def siparis_yazdir(Siparis):
  with open("Orders.cvs", "a", "newline=") as f:
    writer = csv.writer(f)
    writer.writerow(Siparis)
      
    
while True:
  print("Siparise devam etmek icin 1'i, biritmek icin 0'i tuslayiniz.")
  choice = int(input("Secim:"))
  if choice == 0:
    break
  now = datetime.datetime.now()
  time = now.strftime("%Y-%m-%d %H:%M:%S")
  Pizza = pizza_sec()
  if Pizza is None:
    continue

while True:
    print("Sosunzu seciniz.")
    print("11: Zeytin Sosu\n12: Mantar Sosu\n13: Keci Peyniri Sosu\n14: Et Sosu\n15: Sogan Sosu\n16: Mısır Sosu\n")
    choice = int(input("Secim: "))
    if choice == 11:
      pizza = ZeytinSos(pizza)
      break
    elif choice == 12:
      pizza = MantarSos(pizza)
      break
    elif choice == 13:
      pizza = KeciPeyniriSosu(pizza)
      break
    elif choice == 14:
      pizza = EtSosu(pizza)
      break
    elif choice == 15: 
      pizza = SoganSosu(pizza)
      break
    elif choice == 16:
      pizza = MisirSosu(pizza)
      break
    else:
      print("Hata!")

Siparis = [time, sos.get_cost(), pizza.get_cost()]

siparis_yazdir(Siparis)

print("Serbetli Pizzayı tercih ettiginiz icin tesekkurler!\nTarih: {}\nPizza: {}\nUcret: {:.2f}\n".format(time, Pizza.get_description(), Pizza.get_cost()))








    
