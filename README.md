# veri_odevi
2 polinom arasında liste veri yapısı kullanarak toplama çıkarma

def toplama(A, B, m, n): 
  
    uzunluk = max(m, n);# En uzun polinomun değerini uzunluk olarak atıyoruz
    toplamlari = [0 for i in range(uzunluk)] #Toplam Değeri Bulmak İçin Döngüye Sokuyoruz
        
    for i in range(m): 
        toplamlari[i] = A[i]#Toplama dizisinin değerlerini sırayla dolduruyoruz
  
    for i in range(n): 
        toplamlari[i] += B[i]# Yukarıda A için doldurduğumuz değerlere B yi ilave ediyoruz
  
    return toplamlari # Toplamlari sonucumuzu dışarıya return ediyoruz

def cikarma(A, B, m, n): 
  
    uzunluk = max(m, n);# En uzun polinomun değerini uzunluk olarak atıyoruz
    farki = [0 for i in range(uzunluk)] #Toplam Değeri Bulmak İçin Döngüye Sokuyoruz
  
      
    for i in range(m): 
        farki[i] = A[i]#Toplama dizisinin değerlerini sırayla dolduruyoruz
  
    for i in range(n): 
        farki[i] -= B[i]# Yukarıda A için doldurduğumuz değerlere B yi ilave ediyoruz
  
    return farki # Toplamlari sonucumuzu dışarıya return ediyoruz
  

  
def PolinomlariYazdir(polinom, n):# Ana fonksiyondan gönderdiğimiz değerleri polinom ve n ile tutuyoruz.
    for i in range(n): # X in üslünün nereye kadar gitiğini kontrol ediyoruz
        print(polinom[i], end = "")#Polinom elemanlarını yazdırıyoruz
        if (i != 0): 
            print("x^",i, end = "")# x üslülerini yazdırıyoruz 
        if (i != n - 1): 
            print(" + ", end = "") # Polinom elemanlarını topluyoruz(Polinom elemanları pozitif düşünüldü)
  
if __name__ == '__main__':# '__main__' ile kodumuzun ana bölümünün bura olduğunu gösteriyoruz.
      

    # A listesine yazdığımız değerleri polinomal olarak böyle atıyoruz;
    # Virgülden sonraki her değerimiz 'x' üstünü 1 arttırıyor;
    # Örnek  A[0] x^0 + A[1]x^1 + A[2]x^2 ..... 
    A = (3,7,2,4) 

  
    # B listesine  yazdığımız değerleri polinomal olarak böyle atıyoruz;
    # Virgülden sonraki her değerimiz 'x' üstünü 1 arttırıyor;
    # Örnek  B[0] x^0 + B[1]x^1 + B[2]x^2 .....     B = (2, 4) 

    B= (1,6,5) 


    """  Yukarıda değerleri programdan önce atıyoruz eğer kullanıcıdan değer almak istersek for döngüsü içinde aldığımız input
    değerlerini A ve B listelerimize atarak kullanıcıdanda alabiliriz  """


    m = len(A) # Döngüleri oluşturmak için listelerimizin uzunluğunu alıyoruz.
    n = len(B) 
  
    print("1. Polinom:") 
    PolinomlariYazdir(A, m) #Polinomu fonksiyona gönderiyoruz
    print("\n", end = "") 
    print("2.Polinom:") 
    PolinomlariYazdir(B, n) #Polinomu fonksiyona gönderiyoruz
    print("\n", end = "") 
    toplamlari = toplama(A, B, m, n) 
    farklari= cikarma(A,B,m, n)
    uzunluk = max(m, n) # m ve n den hangisinin büyük olduğunu buluyoruz
  

    print("Polinomların Toplanmasını İstiyorsaniz '1'e Basınız:")
    print("Polinomların Farkını İstiyorsaniz '2'ye Basınız:")

    dgr=int(input()) # Yapılması gereken işlem için kullanıcıdan değer alıyoruz
    if(dgr ==1):
    
             print("Polinomlerın Toplamı(A+B):") 
             PolinomlariYazdir(toplamlari, uzunluk) 
             bekle=int(input()) # Konsolun yazdırmadan sonra direkkapanmaması için input kullanıyoruz

    elif  (dgr ==2):
              print("Polinomların Farkı(A-B):") 
              PolinomlariYazdir(farklari, uzunluk)  
              bekle=int(input()) # Konsolun yazdırmadan sonra direkkapanmaması için input kullanıyoruz
