# abapDebug

### Abap Debug(Hata Ayıklama) Nedir?

Hata ayıklama, kusurları veya hataları bulmak ve azaltmak için bir programın akışını analiz etme sürecidir. ABAP hata ayıklayıcı yardımcısı, ABAP programının kaynak kodunda kontrol adımları oluşturarak hataları tespit etmenize ve düzeltmenize yardımcı olur.

### Nasıl Hata Ayıklayabiliriz?

**1. Bir Kesme Noktası(BreakPoint) Ayarlama:** Breakpoint, SAP ABAP programının belirli bir satırında, programın normal yürütülmesini kesintiye uğratan ve Hata Ayıklayıcıya aktarılan bir sinyaldir.

**2. Programı hata ayıklama modunda çalıştırma:** /h komutu ile herhangi bir ekran üzerinde Hata Ayıklayıcı çağrılabilir.


### BreakPoint Türleri Nelerdir?

İki tür BreakPoint vardır;

#### 1. Statik Kesme Noktası:
- BreakPoint'i ayarlamak istediğimiz bir satırda yazılarak oluşturulur. Anahtar kelime: BREAK-POINT.
- Kullanıcıya özel BreakPoint oluşturulur. Anahtar kelime: BREAK <USERNAME>.

  ![image](https://user-images.githubusercontent.com/26427511/159174222-a8c950c0-eb2a-43ea-95c5-79a316bfebae.png)
  
#### 2. Dinamik Kesme Noktası:
- Dinamik kesme noktaları, anahtar kelimeyi kodlamadan istediğimiz satırda bir kesme noktası belirlenir. 
  
![image](https://user-images.githubusercontent.com/26427511/159176397-ee75727d-ce6e-43e9-b1d1-a6b87810777d.png)

### External BreakPoint Nedir?

Harici hata ayıklama, Web Dynpro, BSP Uygulamaları, Soap Web Servisleri vb. gibi harici bir kullanıcı tarafından HTTP aracılığıyla çağrılan programımızı analiz etmek için kullandığımız BreakPoint-lerdir. Harici hata ayıklamayı etkinleştirmek için, yalnızca ayarlanabilen harici kesme noktaları ayarlamamız gerekir. İmleci istenen kod satırında tutarak ve 'Harici Kesme Noktası' simgesine tıklayarak oturum kesme noktaları oluşturulur.
  
![image](https://user-images.githubusercontent.com/26427511/159176653-0a139f8d-76db-4fc6-a7d9-73d801a1e5d8.png)

ABAP Düzenleyici (SE38) → Yardımcı Programlar → Ayarlar → ABAP Editor → Debugging bölümünden harici kullanıcı adı belirlenebilir.

![image](https://user-images.githubusercontent.com/26427511/159176942-f23c6dc9-eceb-4fa8-827c-10987497264b.png)

  

  
  
  







