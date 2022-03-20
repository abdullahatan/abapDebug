# abapDebug

### Abap Debug(Hata Ayıklama) Nedir?

Hata ayıklama, kusurları veya hataları bulmak ve azaltmak için bir programın akışını analiz etme sürecidir. ABAP hata ayıklayıcı yardımcısı, ABAP programının kaynak kodunda kontrol adımları oluşturarak hataları tespit etmenize ve düzeltmenize yardımcı olur.

#### Nasıl Hata Ayıklayabiliriz?

**1. Bir Kesme Noktası(Breakpoint) Ayarlama:** Breakpoint, SAP ABAP programının belirli bir satırında, programın normal yürütülmesini kesintiye uğratan ve Hata Ayıklayıcıya aktarılan bir sinyaldir.

**2. Programı hata ayıklama modunda çalıştırma:** /h komutu ile herhangi bir ekran üzerinde Hata Ayıklayıcı çağrılabilir.


#### Breakpoint Türleri Nelerdir?

İki tür BreakPoint vardır;

##### 1. Statik Breakpoint:
- Breakpoint'i ayarlamak istediğimiz bir satırda yazılarak oluşturulur. Anahtar kelime: BREAK-POINT.
- Kullanıcıya özel Breakpoint oluşturulur. Anahtar kelime: BREAK <USERNAME>.

  ![image](https://user-images.githubusercontent.com/26427511/159174222-a8c950c0-eb2a-43ea-95c5-79a316bfebae.png)
  
##### 2. Dinamik Breakpoint:
- Dinamik kesme noktaları, anahtar kelimeyi kodlamadan istediğimiz satırda bir kesme noktası belirlenir. 
  
![image](https://user-images.githubusercontent.com/26427511/159176397-ee75727d-ce6e-43e9-b1d1-a6b87810777d.png)

#### External Breakpoint Nedir?

Harici hata ayıklama, Web Dynpro, BSP Uygulamaları, Soap Web Servisleri vb. gibi harici bir kullanıcı tarafından HTTP aracılığıyla çağrılan programımızı analiz etmek için kullandığımız BreakPoint-lerdir. Harici hata ayıklamayı etkinleştirmek için, yalnızca ayarlanabilen harici kesme noktaları ayarlamamız gerekir. İmleci istenen kod satırında tutarak ve 'Harici Kesme Noktası' simgesine tıklayarak oturum kesme noktaları oluşturulur.
  
![image](https://user-images.githubusercontent.com/26427511/159176653-0a139f8d-76db-4fc6-a7d9-73d801a1e5d8.png)

ABAP Düzenleyici(SE38, SE37) → Yardımcı Programlar → Ayarlar → ABAP Editor → Debugging bölümünden harici kullanıcı adı belirlenebilir.

![image](https://user-images.githubusercontent.com/26427511/159176942-f23c6dc9-eceb-4fa8-827c-10987497264b.png)

  
#### Dinamik Breakpoint-ler Nasıl Görüntülenir?

Program üzerinden dinamik olarak oluşturulan kesme noklarını görmek ve yönetmek istenebilir. Aktif kesme noktalarına erişim için aşağıdaki adımlar izlenmelidir.

Düzenleyici(SE38, SE37) → Yardımcı Programlar → Kesme Noktası → Görüntüle

![image](https://user-images.githubusercontent.com/26427511/159177491-8555ea73-1809-41e9-9b8f-8f1e4226f614.png)
  

### Hata Ayıklama Programı(ABAP Debugging)
  
  ABAP hata ayıklama programı çalıştığında aşağıdaki ekran açılır. Aşağıdaki ekran görüntüsü yeni hata ayıklama programının ekran görüntüsüdür. Kullanıcı ABAP düzenleyicide bulunan Yardımcı programlar  → Ayarlar  → Debugging menüsünden ABAP Debugger seçeneğini değiştirmedi ise veya oturum sayısı altıya ulaşmadı ise yeni hata ayıklama programı çalışır. Altıdan fazla bir oturum varsa eski ABAP Debugger açılacaktır.
 
![Adsız](https://user-images.githubusercontent.com/26427511/159178998-b561cfcb-10c1-4ffa-96ad-f23cfda89f96.png)


#### 1) Başlık Alanı:
- Hata ayıklama komutlarının, yürütme adımları ve görünümlerinin bulunduğı kısımdır.
- Mevcut olayı ve kod içerisinden hangi rutinlerde olduğumuz hakkındaki bilgileri görebiliriz.

| Buton      | Tanım       | Kısa Yol    | Açıklama    |   
| -----------| ----------- | ----------- | ----------- |
|![image](https://user-images.githubusercontent.com/26427511/159179805-5753a4e1-67eb-41e0-83d3-cd3a51eabd94.png)| Single Step | F5  | Programın akışını bir sonraki satıra geçirmek için kullanılır. Eğer ifade bir işlem bloğu çağırıyor ise o işlem bloğuna girer |
|![image](https://user-images.githubusercontent.com/26427511/159179936-7a8aa509-830d-430b-a063-99af43616fd8.png)| Execute | F6  | Programın akışını bir sonraki satıra geçirmek için kullanılır. Eğer çalıştırılacak satır bir işlem bloğuna dallanacak ise ise o işlem bloğu çalıştırılır ve ilerler. |
|![image](https://user-images.githubusercontent.com/26427511/159181392-b6fa23bd-80a3-4242-96f4-949f3e4e312e.png)| Return | F7  | İçinde bulunan işlem bloğu içerisindeki tüm alt satırlar çalıştırılır. İşlem bloğu dışındaki bir sonraki ifadeye geçilir. Döngü içerisinde kullanıldı ise döngü bitene kadar kesme noktası satırına döner. |
|![image](https://user-images.githubusercontent.com/26427511/159182042-a9d31bb6-6d00-4e00-bdec-78c2a0b2213d.png)| Continue | F8 | Altında bulunan tüm satırları çalıştırır. Döngü içerisinde kullanıldı ise döngü bitene kadar kesme noktası satırına döner. |
|![image](https://user-images.githubusercontent.com/26427511/159182736-c488d148-8886-4dab-b5be-7ec32f260dd0.png)| Create Breakpoint | F9 | Altında bulunan tüm satırları çalıştırır. Döngü içerisinde kullanıldı ise döngü bitene kadar kesme noktası satırına döner. |
|![image](https://user-images.githubusercontent.com/26427511/159183696-0b1dbcea-f985-43c2-a2ba-60ac93132000.png)| Create Watchpoint | Shift+F4 | Watchpoint oluşturmak için kullanılır. Watchpoint, belirtilen değişkenin satırına yönlenmeyi sağlar. Koşul girilebilir. Koşula göre yönlenme sağlanır. |
|![image](https://user-images.githubusercontent.com/26427511/159183653-3d95196e-2458-4f73-ad52-290409aa1798.png)| Save Layout | Ctrl+Shift+F3 |Hata ayıklama ekranında kullanılan düzeni saklamak için kullanılır |

  
#### Hata Ayıklama Programı Kesme Noktaları(Breakpoint):
  
 Dur işareti simgesi(![image](https://user-images.githubusercontent.com/26427511/159182736-c488d148-8886-4dab-b5be-7ec32f260dd0.png)) bize çok çeşitli kesme noktaları oluşturma olanağı sunar.

![image](https://user-images.githubusercontent.com/26427511/159184747-af04e24a-89fb-442e-bdd2-01b685add79c.png)

- **ABAP Cmnds:** Kod içinde kullanılan anahtar komutlar tayin edilerek programda kesme noktaları oluşturulur. Öreneğin Message komutu tayin edilirse program içerisinde Message konutunu geçtiği tüm satırlara otamatik Breakpoint işaratlenir. 
- **Method:** Kod içinde çağrılan Global ve Local Sınıflara ait methodarda kesme noktaları oluşturmak için kullanılır.
- **Function:** Kod içinde çağrılan fonksiyonları kesme noktalarına dahil etmek için kullanılır.
- **Message:** Kod içerisinde çağrılan mesaj sınıflarına kesme noktaları belirlemek için kullanılır. Mesaj sınıfı, mesaj numarası ve mesaj tipi(S,W,I,E vb.) değerleri ile kesme noktaları oluşturulur.
 
#### Hata Ayıklama Programı Veri İzleme Noktaları(Watchpoint):
  
İzleme noktaları(Watchpoint), bir değişkendeki değerler değiştiğinde programın yürütülmesini durdurmak için kullanılır. Ayrıca Watchpoint'te koşullar belirtirseniz ve koşulları yerine getirilir getirilmez programın yürütülmesi kesilecektir.
  
Bir İzleme Noktası oluşturmak için Yeni ABAP Hata Ayıklayıcı'daki Watchpoint(![image](https://user-images.githubusercontent.com/26427511/159183696-0b1dbcea-f985-43c2-a2ba-60ac93132000.png)) düğmesine tıklayın. Watchpoint Oluştur açılır penceresinde, Watchpoint oluşturmak istediğiniz değişken adını ve değerini giriniz.

![image](https://user-images.githubusercontent.com/26427511/159186295-db83c83a-9aa6-41d0-a060-cfa494d4626e.png)
![image](https://user-images.githubusercontent.com/26427511/159186420-745de0da-4ebf-4720-b80e-e8ba4529bde2.png)
  
#### Hata Ayıklama Programı Breakpoint ve Watchpoint Görünümleri:
  
Break./Wachpoints sekmesinden aktif olan Breakpoint ve Wachpoint-ler izlenebilir. Bu sekmne üzerindeki butonlar ile sileme, inaktif etme, aktif etme ve kaydetme gibi işlemler yapılabilir.

![image](https://user-images.githubusercontent.com/26427511/159187242-a9daa3f8-6c1f-4df5-a20f-359a8c07d8e0.png)

  


  

  

 




  

  







