# Ridge Regression / Hitters-Dataset
(Turkish Language)

* amaç hata kareler toplamını minimize eden katsayıları, bu katsayıları bir ceza uygulayarak bulmaktır
* öle katsayılar bulmalıyız ki hata mse, rmse değerleri mininmum olsun
* çoklu doğrusal regresyondan farklı olarak katsayılara ceza uygulucaz.

* Çoklu doğrusal regresyon
$SSE(hata kareler toplamı)= \sum_{i=1}^{n}(y_{i} - {\hat{y}_{i}})^{2}$

* Ridge regresyon
$SSE_{L_{2}}= \sum_{i=1}^{n}(y_{i} - {\hat{y}_{i}})^{2} + \lambda \sum_{j=1}^{P}\beta _{j}^{^{2}}$
* $\lambda$ : ayar parametresi, yani kullanıcı tarafından verilen ve ayarlanan parametre
* $\sum_{j=1}^{P}\beta _{j}^{^{2}}$ : ceza terimi
* $_{L_{2}}$ : Düzenlileştirme Normu - regularization 
* düzenlileştirme, belirli bir model yerine düzenli bir modeli izleyen veriler için hedefleri tahmin etmede üstün olan bir model kurma 
* aşırı öğrenmeye karşı dirençlidir
* yanlıdır fakat varyans düşüktür (bazen yanlı modelleri daha çok tercih ederiz)
* çok fazla parametre olduğunda EKK'ya göre  yani klasik regresyona göre daha iyidir
* Değişken sayısı gözlem sayısından fazla olduğu (çok boyutluluk laneti p >n) durumlara karşı çözüm sunar 
* çoklu doğrusal bağlantı problemi olduğunda etkilidir. Yani bağımsız değişkenler arasında yüksek korelasyon olması demektir. Bir değişkenin taşıdığı bilgiyi neredeyse aynısını başka değişen de taşıyor. bu bir problemdiri korelasyon değerine bakılır.iki bağımsız değişken arasındaki korelasyon değeri %90 ise büyük ihtimalle bu iki bağımsız değişken arasında çoklu doğrusal bağlantı problemi olacağını gösterir
* Tüm değişkenler ile model kurar. İlgisiz değişkenleri modelden çıkarmaz, katsayılarını sıfıra yaklaştırır 
**$\lambda$**
* $\lambda$ kritik roldeddir. iki terimin (formüldeki) göreceli etkilerini kontrol etmeyi sağlar.Optimize edilmesi gerekn parametresidir.
* $\lambda$ için iyi bir değer bulunması önemlidir. Bunun için CV (cross validation) yöntemi kullanılır. 
* $\lambda$'nın sıfır olduğu yer EKK(yani klasik regresyon)'dır. HKT(hata kareler toplamı-SSE) yi minimum yapan $\lambda$'yı arıyoruz
* $\lambda$ için belirli değerleri içeren bir küme seçilir ve her birisi için cross validation test hatası hesaplanır
* En küçük cross validation'ı veren $\lambda$ ayar parametresi olarak seçilir
* son olarak seçilen bu $\lambda$ ile model yeniden tüm gözlemlere fit edilir
