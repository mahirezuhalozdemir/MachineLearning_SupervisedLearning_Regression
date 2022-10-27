
# Makine Öğrenmesi Dersi Denetimli Öğrenme Regresyon Raporu
Makine Öğrenmesi Dersi Denetimli Öğrenme (Regresyon) Raporu
# İÇİNDEKİLER

<hr/>

### [DENETİMLİ ÖĞRENME](#denetimliogrenme)
- #### [DENETİMLİ ÖĞRENME NEDİR?](#denetimliogrenmenedir)
- #### [DENETİMLİ ÖĞRENME TARİHÇESİ](#denetimli-öğrenme-tarihçesi)
- #### [DENETİMLİ ÖĞRENME ÖRNEKLERİ](#denetimli-öğrenme-örnekleri)
### [REGRESYON](#regresyonnedir)
- #### [REGRESYON NEDİR?](#regresyonnedir)
- #### [MAKİNE ÖĞRENMESİNDE REGRESYON](#makine-öğrenmesinde-regresyon)
- #### [REGRESYON ÇEŞİTLERİ](#regresyon-çeşitleri)
- #### [BASİT DOĞRUSAL REGRESYON](#basit-doğrusal-regresyon)
  - ##### [BASİT DOĞRUSAL REGRESYON HESAPLAMALARI](#basit-doğrusal-regresyon-hesaplamaları)
- #### [ÇOKLU REGRESYON](#cokluregresyon)
  - ##### [ÇOKLU LİNEER REGRESYON MODELİ OLUŞTURMAK](#çoklu-lineer-regresyon-modeli-oluşturmak)
- #### [REGRESYON MODELİ KURULUMUNDA 5 METOD](#regresyon-modeli-kurulumunda-5-metod)
  - ##### [GERİYE DOĞRU ELEME](#geriye-doğru-eleme)
  - ##### [İLERİ DOĞRU SEÇME](#ilerisecme)
### [REGRESYON ANALİZİ](#regresyonanalizi)
- #### [REGRESYON ANALİZİ KULLANIM ALANLARI](#regresyonkullanim)
- #### [REGRESYON ANALİZİ HANGİ SEKTÖRLERDE VAR](#regresyon-analizi-hangi-sektörlerde-var)
  - #### [BASİT DOĞRUSAL VE ÇOKLU REGRESYON ÖRNEKLERİ](#basit-doğrusal-ve-çoklu-regresyon-örnekleri)
  - ##### [İŞLETME ÖRNEĞİ](#isletmeornegi)
  - ##### [SAĞLIK ÖRNEĞİ](#sağlık-örneği)
  - ##### [TARIM ÖRNEĞİ](#tarım-örneği)
  - ##### [GAYRİMENKUL ÖRENĞİ](#gayrimenkul-örneği)
  - ##### [İŞ ÖRNEĞİ](#isornegi)
  - ##### [SALGIN HASTALIK ÖRNEĞİ](#salgın-hastalık-örneği)
### [KAYNAKÇA](#kaynakca)



# DENETİMLİ ÖĞRENME<a name="denetimliogrenme"></a>

<hr/>

## Denetimli Öğrenme Nedir?<a name="denetimliogrenmenedir"></a>

<p align="center"><img width="500"  src="https://user-images.githubusercontent.com/73248614/198305611-22537804-b95b-4f3c-bddb-fceaa164417f.jpg">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Denetimli öğrenme; aldığı veriler ve ürettiği sonuçlara dayalı olarak bir model geliştirme işlemidir. Diğer makine öğrenmesi türlerine kıyasla denetimli öğrenmenin en büyük farkı veri etiketi kullanılmasıdır. Etiketlediğimiz veriye, gösterdiğimiz sınıf ve bilgiye göre mevcut gerçekliğe dayanarak model geliştirme algoritmasıdır.Örnekler üzerinde bir öğrenme sağlar ve yeni girdilerde de etiketi tahmin etmeye çalışır.


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Denetimli öğrenmede, makine, bir öğrenme algoritması aracılığıyla etiketli eğitim verilerini çalıştırarak, gelir ve eğitim arasındaki ilişkiyi sıfırdan öğrenmeye çalışır. Denetimli öğrenmenin amacı, Y’nin bilindiği ve Y’nin bilinmediği yeni örnekler verildiğinde Y’yi mümkün olduğunca doğru bir şekilde tahmin etmektir. <br><br>
> Örnek verecek olursak: <br>
Spam ya da spam olmayan mailleri ayırt etmek için elimizde bir veri seti olsun. Bu veri setini kullanarak bir model eğitme işlemi denetimli öğrenmedir.
 
<br><br>
<p align="left"><img width="700"  src="https://user-images.githubusercontent.com/73248614/197515891-659a4174-300c-4124-9007-9773c05d4d7f.jpg">

## Denetimli Öğrenme Tarihçesi
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Denetimli öğrenme fikri Perceptron deneyi ile ortaya çıkmıştır. Bu deneyle yapay sinir ağının temelleri atılmıştır. 
1958 yılında psikolog Frank Rosenblatt tarafından üçgen ya da üçgen olmayan nesneleri belirlemek için bir çalışma yürütülüyor. Rosenblatt  zamanına göre yüksek kalitede kameralar(400 pixel) kullanarak oldukça büyük bir makine yapıyor ve buna da perceptron ismini veriyor. Perceptron tek katmanlı yapay sinir ağından oluşuyordu.<br>
<p align="left"><img width="350"  src="https://user-images.githubusercontent.com/73248614/197516401-e317a7b5-6033-479a-b2db-fcc1e0ad2a86.jpg">
<br>

> **Peki Rosenblatt bu deneyi nasıl gerçekleştiriyor?**<br>
Öğrenmeyi gerçekleştirmek için önce, kameraya çeşitli resimler gösteriyor. Deney için 2 sınıfımız var. Üçgen ya da değil.
Kamera gördüğü şeye bağlı olarak perceptrona farklı bir elektrik sinyal gönderiyor. Daha sonra Rosenblatt, üçgen şekliyle eşleşen tüm sinyalleri perceptrona uyguluyor. Eğer total skor threshold değerinden büyükse makine bir elektrik sinyali gönderir ve ışıklar açılır. Eğer elektriksel yük threshold değerinden küçükse ışık yanmıyor ve bu da üçgen olmadığı anlamına geliyor. İlk başta perceptron rastgele tahminler yaparak threshold değerini belirlemek için kullanıldı.Daha sonra Rosenblatt ‘evet’, ‘hayır’ butonlarıyla denetimli öğrenmeyi gerçekleştirdi. Eğer perceptron doğru tahmin yapıyorsa ‘evet’ tuşuna basıyordu,yanlış tahminde de sinapslardan geçen elektrik değerini ölçüp threshold değeri olarak belirliyordu.
Evet ,hayır butonları kullanıldığı için, bu uygulama denetimli öğrenmenin temeli sayıldı. 
 
 <br>
<p align="left"><img width="500"  src="https://user-images.githubusercontent.com/73248614/197516493-54d09b25-1c67-4377-a714-2855962b4d99.jpg"><br>

## Denetimli Öğrenme Örnekleri
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Denetimli öğrenmenin ne olduğunu anlamak için bir örnek kullanacağız. Örneğin, bir çocuğa içinde on aslan, on maymun, on fil ve diğerleri gibi her türden on hayvanın bulunduğu 100 oyuncak hayvan veriyoruz. Daha sonra, çocuğa bir hayvanın farklı özelliklerine (özelliklerine) dayalı olarak farklı hayvan türlerini tanımayı öğretiyoruz. Rengi turuncuysa, o zaman bir aslan olabilir. Gövdesi büyük bir hayvansa, fil olabilir. Çocuğa hayvanları nasıl ayırt edeceğini öğretiriz, bu denetimli öğrenmeye bir örnektir. Şimdi çocuğa farklı hayvanlar verdiğimizde, onları uygun bir hayvan grubuna ayırabilmelidir.
Bunlara ek olarak en meşhur denetimli öğrenme uygulaması ,ev özelliklerine göre satış fiyatı tahmini yapmayı amaçlayan Boston konut fiyatı veri kümesidir. Ev özelliklerini kullanarak satış fiyatını tahmin etmeyi amaçlamıştır.
<br><br>
<p align="left"><img width="800"  src="https://user-images.githubusercontent.com/73248614/197517157-f8b62e7c-ef57-4357-b54d-3561a00c386a.jpg">

- CRIM : Kasabaya göre kişi başına düşen suç oranı<br>
- ZN : 25.000 sq.ft'den büyük parseller için imar edilen konut arazilerinin oranı<br>
- INDUS : Kasaba başına satışı olmayan iş dönümü oranı<br>
- CHAS : Eğer nehir varsa 1,yoksa 0 değeri alır<br>
- NOX : 10 milyonda nitrik oksit konsantrasyonu<br>
- RM : Konut başına düşen ortalama oda sayısı<br>
- AGE : 1940'dan önce inşa edilmiş ve sahibi tarafından yaşanan ev oranı<br>
- DIS : 5 Boston iş merkezine olan uzaklık<br>
- RAD : Otoyollara ulaşım indexi<br>
- TAX : 10.00 dolar başına düşen emlak vergisi oranı<br>
- PTRATIO : Şehre göre öğretmen öğrenci oranı <br>
- LSTAT : Popülasyonda düşük gelirli insanların oranı<br>
- MEDV : Evin ortalama değeri <br>

# REGRESYON NEDİR?<a name="regresyonnedir"></a>

<hr/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Regresyon, bir bağımlı değişken (genellikle Y ile gösterilir) ve diğer bağımsız değişkenler arasındaki ilişkinin gücünü ve karakterini belirlemeye çalışan finans, yatırım, makine öğrenmesi ve diğer disiplinlerde kullanılan istatistiksel bir yöntemdir. <br>

**Bağımlı Değişken:**  Anlamaya veya tahmin etmeye çalıştığımız değişkendir. <br>

**Bağımsız Değişken:** Analizi veya hedef değişkeni etkileyen ve değişkenlerin hedef değişkenle ilişkisi hakkında bize bilgi veren faktörlerdir. <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Verisetini sınıflara ayırmayı hedeflemez.Girdi veri üzerinden çıktı verilerin sürekli olarak tahmin edilmesini kapsar.Bilgisayar,bir çok farklı regresyon algoritması tekniğini kullanarak,çıktılardaki değişiklikler ve dalgalanmalar ile verileri tahmin edebilir.Regresyon modelleri,sürekli modeller ile ilgilenir.
## Makine Öğrenmesinde Regresyon
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Makine öğrenmesinde regresyon ise kısaca makinenin veri setini ezberlememesi için oluşturulan algoritmadır. İstenen sonuç makinenin ezberlemesi değil “öğrenmesi” yani tutarlı tahmin yeteneğine sahip olmasıdır.
Yöntem olarak bir eğitim kümesi ve eğitim kümesinden makine öğrenmesi metotları ile bir model elde edilip bu model üzerinden yeni gelen veriler tahmin edilmeye çalışılır. Regresyon yönteminde tahmin sonucu kategorik değil nümerik bir değer olmalıdır.
> **Örneğin:**<br>
**Kategorik tahmin sonucu:** Hava çok soğuk, hava soğuk, hava ılık, hava sıcak, hava çok sıcak gibi.<br>
**Nümerik tahmin sonucu:** Hava -10 derece, 0 derece, 10.01 derece, 30.02 derece gibi sayısal değerlerdir.<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Uygun olmayan regresyon yöntemlerinin kullanılması hatalı ve yanıltıcı sonuçların elde edilmesine neden olabilmektedir. Regresyon analizinde incelenen değişkenler sürekli ya da kesikli yapıda olabilmektedir ve bu veri yapısına bağlı olarak farklı regresyon modelleri kullanılabilmektedir.
## Regresyon Çeşitleri
- **1-Doğrusal Regresyon:** Doğrusal regresyon, iki değişken arasındaki doğrusal ilişkinin bir doğru denklemi olarak tanımlanıp, değişkenin değerlerinden biri bilindiğinde diğeri hakkında tahmin yapılmasını sağlar.
İş arkadaşlarınızın daha önce zaten anladıklarını görmüş ve düşünmüş olabilecekleri kalıpları ve ilişkileri ortaya çıkararak daha iyi iç görüler sağlamak için de doğrusal regresyondan yararlanabilirsiniz. Örneğin, satış ve satın alma verilerini analiz etmek, belirli günlerdeki ya da belirli saatlerdeki belirli satın alma kalıplarını ortaya çıkarmanıza yardımcı olabilir. Regresyon analizinden toplanan iç görüler, iş liderlerinin şirketlerinin ürünlerinin yüksek talep göreceği zamanları tahmin etmelerine yardımcı olabilir.
Doğrusal regresyon, basit doğrusal regresyon ve çoklu doğrusal regresyon olarak iki başlık altında incelenir.
Basit doğrusal regresyon, yanıt değişkeni ile tek bir açıklayıcı değişken arasındaki doğrusal ilişkiyi açıklar. Eğer tek bir yanıt değişkeni ve birden fazla açıklayıcı değişken arasındaki doğrusal veya eğrisel bir ilişki tanımlanmak istenirse, ilişki çoklu doğrusal regresyon ile incelenir (Okur, 2009; Weisberg, 2005).
- **2-Polinom Regresyon:** Bir bağımlı ve birden fazla bağımsız değişken arasında polinomal bir artış söz konusu ise bu algoritmayı kullanırız. Polinom Regresyon Formülü: Y = a + bX + cX²
- **3– Karar Ağacı Regresyonu:** Karar Ağaçları Algoritmaları hem sınıflandırma da hem de regresyonda kullanılır. Regresyon için kullanılan algoritmayı şöyle açıklayabiliriz; Bağımsız değişkenleri bilgi kazancına göre aralıklara ayırır. Tahmin esnasında bu aralıktan bir değer sorulduğunda cevap olarak bu aralıktaki (eğitim esnasında öğrendiği) ortalamayı verir. Belli aralıklarda istenilen değerler için aynı sonuçları ürettiğinden kesikli bir modeldir.
- **4-Lojistik Regresyon:** Lojistik regresyon, istatistikte kullanılan bir model oluşturma tekniği olup iki ya da daha fazla sınıfta ifade edilebilen kesikli verilerde yanıt değişkeni (Y) için bir model oluşturma tekniğidir.

> Örneğin, web sitesi ziyaretçinizin alışveriş sepetindeki ödeme düğmesine tıklayıp tıklamayacağını tahmin etmek istediğinizi varsayalım. Lojistik regresyon analizi, web sitesinde harcanan zaman ve sepetteki ürün sayısı gibi geçmiş ziyaretçi davranışlarına bakar. Geçmişte, ziyaretçiler sitede beş dakikadan fazla zaman geçirdiyse ve sepete üçten fazla ürün eklediyse ödeme düğmesine tıkladıklarını belirler. Lojistik regresyon işlevi bu bilgiyi kullanarak daha sonra yeni bir web sitesi ziyaretçisinin davranışını tahmin edebilir.
<p align="left"><img width="600"  src="https://user-images.githubusercontent.com/73248614/197522816-00fef958-6cf8-4288-a078-62f585fbac24.jpg"><br><br>
Ridge Regresyon, Lasso Regresyon, Sıralı Regresyon gibi daha birçok regresyon türü bulunmaktadır.

## Basit Doğrusal Regresyon
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Açıklayan(bağımlı) ile  tek bir açıklayıcı (bağımsız) değişkenin arasındaki doğrusal ilişkinin modellenmesidir. Bir başka ifadeyle bağımlı değişkenin değerini bağımsız denklemin bir fonksiyonu olarak en doğru şekilde tahmin eden doğrusal ilişkidir. Burada tahmin edilmek istenen bağımlı değişkendir.İki değişken arasındaki ilişkinin ne kadar güçlü olduğu bağımsız değişkenin belirli bir değerinde bağımlı değişkenin değeri bilgilerine ulaşmak için basit doğrusal regresyon kullanılır.
> Gelir ve mutluluk arasındaki ilişkiyle ilgilenen bir araştırmacı olduğunuzu düşünün. Gelirleri 15 bin ile 75 bin arasında değişen 500 kişiyi araştırıyorsunuz ve onlardan mutluluklarını 1'den 10'a kadar puanlamalarını istiyorsunuz.
Bağımsız değişkeniniz (gelir) ve bağımlı değişkeniniz (mutluluk) niceldir, bu nedenle aralarındaki ilişkiyi basit doğrusal regresyon analizi ile açıklayabilirsiniz.

### Basit Doğrusal Regresyon Hesaplamaları
```sh
𝓎 = ß0+ß1X+𝑒 
```

<br>

```sh
𝓎 = yanıt değişkeni
ß0 = kesim noktası
ß1 = doğrunun eğimi
X = bağımsız değişken
𝑒 = hata payı(kalıntı)
```
**𝓔 Nedir?** <br>
&nbsp;&nbsp;Gerçek değer ve tahmini değer arasındaki farktır.Bu farka göre modeller arasındaki doğruluk kontrolü yapılır.

```sh
𝓔i = yi - ŷi
yi = gerçek değer
ŷi  = tahmini çıktı

```
<br>

> Bir pazarlama firmasının televizyon, gazete ve radyoya verdiği reklamların satışlar üzerindeki etkisini araştırdığını varsayalım.
<br> satışlar ≈ β0+β1×TV <br>
Satışlar ve TV değişkenleri   arasındaki doğrusal model formülize edildiği gibidir.

<p align="left"><img width="600"  src="https://user-images.githubusercontent.com/73248614/197635054-73bb45a8-f833-45cd-a89e-b47aa7a2957c.jpg">
<br>

<p align="left"><img width="600"  src="https://user-images.githubusercontent.com/73248614/197635397-a0529020-cb8a-4416-9dde-13152e4e59c3.jpg">
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Regresyon eğrisi temsil ettiği noktalara olabildiğince en yakından geçmeye çalışıyordu. Bunun için her bir noktanın eğriye olan uzaklığı hesaplanıyor ve toplam mesafeyi en küçük kılan doğru regresyon doğrusu oluyordu. 
 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;yi değeri ile tahmin edilen yi^ değeri arasındaki mesafelerin karelerinin toplamının en düşük olduğu eğri (doğru denklemi) regresyon eğrisidir.
Regresyon eğrisi üzerinde bulunmayan her nokta bizim için bir atık oluyor. Her bir değerde gerçek sonuç ve tahmini sonuç farkının karelerinin toplamı bize
 
 **artık kareler toplamını**
 veririr. 
Her bir değerin ortalama sonuca uzaklığının(farkının) kareler toplamı da bize **toplam kareler toplamını** verir.
 
 <br>
Basit doğrusal regresyon analizi sonucu parametre kestirimlerinin güvenli olabilmesi için bazı varsayımların geçerli olması gereklidir .
Modeldeki bağımsız değişkenlerin, bağımlı değişkeni ne kadar açıkladığı R2 değeri ile ölçülür. <br>
 
**R2 değerini hesaplamak için:** <br>
- Toplam Kareler Toplamı
- Artık Kareler Toplamı <br>
değerlerine ihtiyaç duyarız. <br>
R2 değeri aşağıdaki formül ile hesaplanır. <br>

```sh
R²= (TOPLAM KARELER TOPLAMI-ARTIK KARELER TOPLAMI) / TOPLAM KARELER TOPLAMI

```
R2  0-1 arasında bir değer alır. R2 değerinin 1’e yakın olması bağımsız değişkenlerin, bağımlı değişkenleri iyi bir şekilde açıkladığını gösterir.
<br><br>
## Çoklu Regresyon<a name="cokluregresyon"></a>
<br><br>
Doğrusal regresyon bir bağımsız değişkenin bir bağımlı değişken üzerine etkisini göstermeye yararken, çoklu regresyonda bağımsız değişken sayısı birin üstüne çıkar. 
En az iki bağımsız değişkenin, bağımlı değişken üzerinde etkilerini göstermeye yarayan analiz yöntemidir.
İki değişken varsa, tahminin temelini oluşturan değişken bağımsız değişkendir. Değeri tahmin edilecek değişken bağımlı değişken olarak bilinir.
**Çoklu Regresyon Formülü:** <br>
```sh
Y = ß0 + ß1.x1 + ß2.x2 + ... + ßk.xk+ei = ß0+ΣßrXr+e
```
<br>
Çoklu lineer regresyonda her bağımsız değişkenin bağımlı değişkene etkime derecesi birbirinden farklıdır. Bundan dolayı basit lineer regresyondaki denkleme ek olarak her değişkenin katsayısı aynı olmak zorunda değildir.
 
**P Değeri Nedir?**
 

P değeri, bizim hipotezlerimizin doğru olup olmadığını belirlememize yardımcı olan istatistiksel bir ölçüdür.
P değerleri, deney sonuçlarının gözlemlenen olaylar için normal değerler aralığında olup olmadığını belirlemek için kullanılır. 
Genellikle, bir veri setinin P değeri önceden belirlenmiş belirli bir miktarın altındaysa (örneğin, 0.05 gibi), bilim insanları deneylerinin "boş hipotezini" reddedeceklerdir.
Yani ilgili değişkenin sonuç üzerinde anlamlı bir etkisinin olmadığı anlaşılır.
### Çoklu Lineer Regresyon Modeli Oluşturmak
Çoklu lineer regresyon modeli oluştururken oldukça fazla parametrenin dikkatle incelenmesi gerekir, çünkü her bir değerin bağımlı değişken üzerinde anlamlı bir etkisi olmayabilir. 
Bağımlı değişkeni yüksek oranda etkileyen bir değişkeni veri setinden kaldırdığımız zaman oluşacak hatalar veya gereksiz bir değişkeni veri setinden atmadığımız zaman kaybedeceğimiz verim istenilmeyen bir sonuçtur.
Bu durumu doğru şekilde incelemek için belirli istatistik modelleri vardır. 
## Regresyon Modeli Kurulumunda 5 Metod
- Bağımsız değişkenlerin hepsini birden modele dahil etmek (All-in)
- Geriye doğru eleme (Backward Elimination)
- İleriye doğru seçme (Forward Selection)
- İki yönlü eleyerek seçme (Bidirectional Elimination)
- Sonuçları karşılaştırma (Score comparision)

 
### Geriye Doğru Eleme
Geriye doğru eleme yöntemi tüm değişkenleri içeren bir modelden, fazlalıklarını atarak daha verimli daha küçük bir model oluşturma içeren algoritmadır.
- Değişkenlerin modelde kalması için önem değeri belirlenir. Bir çeşit eşik değeri(threshold) olarak işlev görür. (p<0.05) 
- Modelle alakasız değişkenler modelden çıkarılır.
- En yüksek P değerine sahip değişkeni bul. Eğer önem değerinden yüksekse (P>SL) bir sonraki adıma ilerle. Eğer düşükse modelin geriye doğru eleme algoritmasını tamamlamıştır.
- P değeri önem değerinden yüksek değişkeni modelden çıkart ve 3. adıma dön.
### İleri Doğru Seçme<a name="ilerisecme"></a>
İleri doğru seçme yöntemi geriye doğru eliminasyon yönteminden farklı olarak hiçbir bağımsız değişken içermeyen bir model olarak başlar yolculuğuna. Sonrasında ise hipoteze en yararlı olduğu tahmin edilen değişkenleri alarak kendisini daha büyük bir model haline getirir. İşleyişi ise şöyledir:
<br>
- Modele giriş için bir önem değeri belirlenir. (Örneğin SL=0,05)
- Bütün bağımsız değişkenler ve bağımlı değişkenle ayrı ayrı ikişerli modeller oluşturulur. En küçük P değerine sahip değişken seçilir.
- Seçilen değişken modele eklenir. Bundan sonrasında ise belirlenen önem değerinden düşük olmakla beraber yine en küçük P değerine sahip değişken modele eklenir.
- Bu işlem seçilen yeni değişkenin P değerinin önem değerinden fazla olmasına kadar devam eder. En küçük P değerine sahip yeni değişkenin P değerinin önem değerinden fazla olduğunu gördüğümüzde daha önce eklediğimiz değişkenlerin model için yeterli olduğunu anlamalıyız.
<br>
Bu yazıda sizleri daha fazla yöntemle karmaşaya boğmak istemiyorum. Çok yönlü eleme yöntemi hakkında bilgi sahibi olmak isterseniz 
 
 **bidirectional elimination** anahtar kelimesiyle araştırma yapabilirsiniz.

# REGRESYON ANALİZİ<a name="regresyonanalizi"></a>

<hr/>

Bir regresyon analizi 3 adımda gerçekleştirilir.
 
- **1. Öncelikle Bir Hipotez Oluşturulur**
Bir regresyon analizi yapmak için, ilişkili olduğuna inandığınız iki değişkeni seçmeniz gerekir. Mümkün olduğu kadar çok veri toplayarak ilişkileri hakkında hipotezinizi oluşturun. Reklam ve satış ilişkisi söz konusu olduğunda, daha doğru bir analiz için bir yıl boyunca oluşan tüm finansal verileri toplayabilirsiniz.

- **2.Bir Grafik Oluşturulur**
Bir sonraki adım, verilerinizin grafiğini çıkarmaktır. İki veri seti ile doğrusal regresyon için temel bir çizgi grafiği oluşturabilirsiniz. Bir değişken X ekseninde, diğeri Y ekseninde çizilir. Bir elektronik tabloya girdiğinizde, değişkenler arasındaki korelasyonu görebilirsiniz. Düz bir çizgi varsa, bu pozitif bir korelasyon gösterir.

- **3. Sonuçlar Analiz Edilir**
Grafiği temel bir doğrusal regresyonda inceleyerek kesişim, katsayı ve korelasyonu görebilirsiniz. Bu rakamları bir araya getirmek, iki veri seti arasındaki tarihsel ilişkiyi göstererek modelin gelecekte nasıl görüneceğini tahmin etmenize olanak tanır. Geçmişte, çevrimiçi reklamcılık ve satışlar arasında olumlu bir ilişki varsa, gelecek yıl için bir tahmin oluşturmak için yüzdeleri bir modele ekleyebilirsiniz. 
<br>
<p align="left"><img width="300"  src="https://user-images.githubusercontent.com/73248614/197738487-79e8723e-a82e-400a-b98a-f2b89c3a9f28.png"> <br>

# REGRESYON ANALİZİ KULLANIM ALANLARI<a name="regresyonkullanim"></a>

<hr/>

- **1.Tahmin** <br>
İşletmelerde regresyon analizinin en yaygın kullanımı, gelecekteki fırsatları ve tehditleri tahmin etmektir. Örneğin talep analizi, bir müşterinin satın alma olasılığı yüksek olan şeylerin miktarını tahmin eder.
<br><br>
Ancak iş söz konusu olduğunda, talep tek bağımlı değişken değildir. Regresif analiz, doğrudan gelirden çok daha fazlasını öngörebilir.
<br><br>
> Örneğin, belirli bir reklam panosunun önünden geçecek tüketicilerin sayısını tahmin ederek bir reklam için en yüksek teklifi tahmin edebilir.
- **2.CAPM** <br>
Bir varlığın öngörülen getirisi ile ilgili piyasa risk primi arasındaki bağlantıyı kuran The Capital Asset Pricing Model (CAPM), doğrusal regresyon modeline dayanır. Ayrıca, kurumsal getirileri ve operasyonel performansı tahmin etmek için finansal analistler tarafından finansal analizde sıklıkla kullanılır.
Bir hisse senedinin beta katsayısı, regresyon analizi kullanılarak hesaplanır. Beta, toplam piyasa riskiyle ilgili getiri oynaklığının bir ölçüsüdür.
- **3.Rekabet Karşılaştırma** <br>
Bir şirketin finansal performansını belirli bir muadili ile karşılaştırmak için kullanılabilir. Ayrıca iki firmanın hisse senedi fiyatları arasındaki ilişkiyi belirlemek için de kullanılabilir ve hangi yönlerin satışlarını etkilediğini belirlemede firmaya yardımcı olabilir. Bu teknikler, küçük işletmelerin kısa sürede hızlı başarıya ulaşmalarına yardımcı olabilir.
- **4.Güvenilir Kaynak**<br>
Birçok işletme ve üst düzey yönetici, daha iyi iş kararları vermek, varsayımları ve içgüdüleri azaltmak için regresyon analizini kullanır. Yöneticiler, verileri filtrelemek ve mümkün olan en iyi kararları vermek için regresyon analizinden yararlanır.
### Regresyon Analizi Hangi Sektörlerde Var?
Regresyon analizinin nerelerde kullanılabileceğini öğrenmek istiyorsanız, aşağıdaki örnekleri inceleyebilirsiniz.<br> <bR>
**Finans Sektörü:**
Finansta, bir hisse senedinin BETA’sını hesaplamak için regresyon analizi kullanılır. Üstelik bunu Excel yardımı ile kolayca yapabilirsiniz.
Yine finansta, şirketler için mali tabloları tahmin etmek için regresyon analizi de kullanılır. Böylece, iş varsayımlarındaki hangi değişikliklerin gelecekteki giderleri ve geliri etkileyeceğini belirleyebilirsiniz.
Bir şirketin satışları son birkaç yıldır her ay istikrarlı bir şekilde arttıysa, satış verileri üzerinde aylık satışlarla doğrusal bir analiz yaparak şirketin gelecek aylardaki satışlarını tahmin edebilirsiniz.
Bir firmanın yöneticisi, gelecek planlaması için reklam harcamaları ile satışlar arasındaki kesin ilişkiyi öğrenmek istiyorsa, regresyon tekniği ile bu ilişkiyi tahmin edebilir.<br>
**Pazarlama:** 
 Pazar kampanyalarının etkinliğini, tahmin fiyatlandırmasını ve ürünün satışını anlamak.<br>
**Üretim:** 
 Daha iyi performans sağlamak için değişkenlerin ilişkisini değerlendirmek.<br>
**İlaç:**
 Hastalıklar için jenerik ilaçlar hazırlamak için farklı ilaç kombinasyonlarını tahmin etmek.
<br>
### Basit Doğrusal Ve Çoklu Regresyon Örnekleri
#### İşletme Örneği<a name="isletmeornegi"></a>
İşletmeler, reklam harcamaları ile gelir arasındaki ilişkiyi anlamak için genellikle doğrusal regresyon kullanır.
<br>
> revenue= ß0+ß1(ad spending)
- Β0 katsayısı, reklam harcaması sıfır olduğunda beklenen toplam geliri temsil eder.
- Β1 katsayısı, reklam harcamaları bir birim (ör. Bir dolar) artırıldığında toplam gelirdeki ortalama değişimi temsil eder.
- Β1 negatifse, bu, daha fazla reklam harcamasının daha az gelirle ilişkili olduğu anlamına gelir.
- Β1 sıfıra yakınsa, bu, reklam harcamalarının gelir üzerinde çok az etkisi olduğu anlamına gelir.
- Β1 pozitifse, daha fazla reklam harcamasının daha fazla gelirle ilişkili olduğu anlamına gelir.
- Β1 değerine bağlı olarak, bir şirket reklam harcamalarını azaltmaya veya artırmaya karar verebilir.
#### Sağlık Örneği
Tıbbi araştırmacılar, ilaç dozu ile hastaların kan basıncı arasındaki ilişkiyi anlamak için sıklıkla doğrusal regresyon kullanırlar.
> blood pressure= ß0+ß1(dosage)

Örneğin, araştırmacılar hastalara belirli bir ilacın çeşitli dozajlarını uygulayabilir ve kan basıncının nasıl tepki verdiğini gözlemleyebilir. Yordayıcı değişken olarak dozajı ve yanıt değişkeni olarak kan basıncını kullanan basit bir doğrusal regresyon modeline uyabilirler. Regresyon modeli aşağıdaki formu alacaktır:
<br>
<p align="left"><img width="400"  src="https://user-images.githubusercontent.com/73248614/197741252-3df94a19-c6c3-4f08-8550-b46f54b31738.jpg"><br>

#### Tarım Örneği
Tarım bilimcileri, gübre ve suyun mahsul verimi üzerindeki etkisini ölçmek için genellikle doğrusal regresyon kullanırlar.<br>
Örneğin, bilim adamları farklı alanlarda farklı miktarlarda gübre ve su kullanabilir ve bunun mahsul verimini nasıl etkilediğini görebilirler. Yordayıcı değişkenler olarak gübre ve su ve yanıt değişkeni olarak mahsul verimi kullanan çoklu doğrusal regresyon modeline uyabilirler. Regresyon modeli aşağıdaki formu alacaktır:
> crop yield = ß0+ß1(amount of fertilizer)+ß2(amount of water)

- ß0 katsayısı, gübre veya su olmadan beklenen mahsul verimini temsil eder.
- ß1 katsayısı, su miktarının değişmeden kaldığı varsayılarak, gübre bir birim artırıldığında mahsul verimindeki ortalama değişimi temsil edecektir.
- ß2 katsayısı, gübre miktarının değişmeden kaldığı varsayılarak, su bir birim artırıldığında mahsul verimindeki ortalama değişimi temsil edecektir.
- ß1 ve ß2 değerlerine bağlı olarak, bilim adamları mahsul verimini en üst düzeye çıkarmak için kullanılan gübre ve su miktarını değiştirebilirler.

#### Gayrimenkul Örneği
Ev satmak için en iyi zamanı tahmin etmeye yardımcı olacak bir model oluşturmak isteyen bir emlak uzmanısınız. Evleri maksimum satış fiyatından satmak istersiniz, ancak satış fiyatını birden fazla faktör etkileyebilir. Bu değişkenler, diğer faktörlerin yanı sıra evin yaşını, mahalledeki diğer evlerin değerini, devlet okulu sisteminin öğrenci performansına ilişkin nicel ölçümlerini ve yakındaki parkların sayısını içerir.Evlerin maksimum satış fiyatını tahmin etmek için bu dört bağımsız değişkenden bir tahmin modeli oluşturabilirsiniz. Bu faktörlerden herhangi biri katsayı değerleri açısından değişirse değişkenleri ayarlayabilirsiniz.

#### İş Örneği<a name="isornegi"></a>
Halka açık bir şirkette hisse senediniz var ve şimdi hisse senedinizi satmak için iyi bir zaman olup olmayacağını bilmek istiyorsunuz. Şirketin karlılığı, şirketin maliyetleri, şirketin rekabeti ve şirketin varlıkları dahil olmak üzere hisse senedi fiyatının değerini çeşitli değişkenler etkileyebilir. Hisse senedini hemen satmanız mı yoksa hisse senedini elinde tutmaya devam etmeniz mi gerektiğine karar vermenize yardımcı olmak için bu dört bağımsız değişkenden bir tahmin modeli oluşturabilirsiniz.

#### Salgın Hastalık Örneği
Bulaşıcı bir hastalığın yayılmasını inceleyen bir epidemiyologsunuz. Mevcut bilinen enfeksiyonlara dayanarak bu hastalığın gelecekteki yayılmasını tahmin etmek istiyorsunuz. Çok sayıda bağımsız değişken, popülasyon büyüklüğü, popülasyon yoğunluğu, hava sıcaklığı, asemptomatik taşıyıcılar ve popülasyonun sürü bağışıklığına ulaşıp ulaşmadığı dahil olmak üzere gelecekteki enfeksiyonların sayısını etkileyebilir. Yordayıcı değişkenlerin katsayı değerlerindeki olası değişiklikleri hesaba katan bir sonucu tahmin etmek için ampirik veriler üzerinde istatistiksel modelleme ve çoklu doğrusal regresyon analizi yapabilirsiniz.

# KAYNAKÇA<a name="kaynakca"></a>

<hr/>

- https://en.wikipedia.org/wiki/Simple_linear_regression <br>
- https://dergipark.org.tr/en/download/article-file/187511 <br>
- https://aws.amazon.com/tr/what-is/logistic-regression/ <br>
- https://www.ibm.com/tr-tr/analytics/learn/linear-regression <br>
- https://www.scribbr.com/statistics/simple-linear-regression/#:~:text=What%20is%20simple%20linear%20regressio%20n,Both%20variables%20should%20be%20quantitative. <br>
- https://www.cancankiran.com/makine-ogrenimi/ <br>
- https://www.youtube.com/watch?v=4qVRBYAdLAo <br>






















