# Naive Bayes Uygulaması
Bu projede Naive Bayes algoritması kullanılarak bir makine öğrenmesi gerçekleştirilmiştir. Amacımız veri setinin ham hali, normalize edilmiş hali ve Grid Search kullanarak hiperparametre optimizasyonu yapılmış halinin doğruluk oranlarını (accuracy score) karşılaştırmak. 

Diyabet veri setinine Naive Bayes algoritması ile makine öğrenmesi yaparak hastaların diyabet olup olmadığı tahmin etmeye çalışılmıştır.
## Naive Bayes
Naive Bayes, Bayes Teoremine dayanan istatistiksel bir sınıflandırma tekniğidir. En basit denetimli öğrenme algoritmalarından biridir. Naive Bayes sınıflandırıcısı hızlı, doğru ve güvenilir bir algoritmadır. Naive Bayes sınıflandırıcıları büyük veri kümelerinde yüksek doğruluk ve hıza sahiptir.
Naive Bayes sınıflandırıcısı, bir sınıftaki belirli bir özelliğin etkisinin diğer özelliklerden bağımsız olduğunu varsayar.
![1_aFhOj7TdBIZir4keHMgHOw](https://github.com/BilgeGoksel/Diabetes-Homework/assets/163318769/f4ade4c7-1d36-42d4-baae-2e33341a8bb3)
## Veri Ön Hazırlık
Diyabet veri setini Pandas kütüphanesi ile okutup bağımsız değişken ve sonuç değişkenini ayırıyoruz. Daha sonra veri setimizdeki eksik olan değerler için medyan yönetimi kullanarak değer atıyoruz. Son olarak da veriyi test ve train için iki kısma ayırıyoruz.
## Veri Normalizayonu
Normalizasyonun amacı, farklı ölçeklerdeki veya dağılımlardaki verileri aynı ölçek veya dağılıma getirmektir. Bu, veri setindeki anlamsal tutarlılığı artırır ve analiz sürecinde yanıltıcı sonuçların önüne geçer. Makine öğrenimi modellerinin daha iyi performans göstermesine yardımcı olabilir.

Bu kodda ölçekleme için Standart Scaler kullanıldı. Std. Scaler; her özelliğin ortalaması 0, standart sapması 1 olacak şekilde dönüşüm yapar.
## GuassianNB
GaussianNB (Gaussian Naive Bayes), Naive Bayes sınıflandırma algoritmalarından biridir. GaussianNB özellikle sürekli veri setlerinde çalışmak için tasarlanmıştır ve özelliklerin normal (Gaussian) dağılıma sahip olduğunu varsayar. Özellikle basit, hızlı ve düşük boyutlu veri setlerinde iyi performans gösterir.(Kullanılan veri seti için uygundur.)
## Grid Search
Grid Search, makine öğrenimi modellerinde en iyi hiperparametre kombinasyonunu bulmak için kullanılan bir hiperparametre optimizasyon tekniğidir. Grid Search, genellikle çapraz doğrulama (cross-validation) ile birleştirilir. Her bir hiperparametre kombinasyonu, çapraz doğrulama ile modelin performansı ölçülerek değerlendirilir.

Kodda scikit-learn kütüphanesinin GridSearchCV sınıfını kullanarak Destek Vektör Makinesi (SVM) modelinin hiperparametrelerini aramak için bir grid arama gerçekleştirilir. "params" adlı sözlük aranacak hiperparametrelerin adlarını ve olası değerlerini içerir. Örneğin, 'C', 'gamma' ve 'kernel' gibi hiperparametrelerin olası değerleri belirlenir.Ayrıca, verbose parametresi ile işlem sırasında detaylı çıktı alınmasını sağlamak için verbose=3 değeri verilir ve çapraz doğrulama (cross-validation) için 5 katlı çapraz doğrulama (cv=5) kullanılır. Daha sonra en iyi parametreler ile model tekrar eğitilir.
## Yorumlar ve Sonuçlar 
Ham veri setini eğitip sonuçları aldığımız zaman accuracy oranının 0.734 , veri setini normalize ettiğimizde 0.661 ve Grid Search hiperparametre optimizasyonu ile sonucun 0.734 olduğu görülmüştür.

Veri normalize edildiği halde ham haline göre daha düşük çıkması veri setinin özelliklerinden kaynaklanmakta birbirine yakın değerler içerdiği için normalleştirmenin öğrenimde etkisi az olmuştur. Bu nedenle hiperparametre optimizasyonu ile daha yüksek doğruluk oranı amaçlanmıştır. GridSearch ile optimizasyon daha yüksek bir accuracy oranı vermiştir. Fakat bu oran da ham haline oldukça yakındır. Buradan şu yorumu yapmak doğru olacaktır: veri seti doğal olarak iyi ayrılabilir veya düşük boyutluysa, varsayılan hiperparametrelerle eğitilen model zaten yeterince iyi sonuçlar verebilir.
- Ham veri setinin matrisi:
![download](https://github.com/BilgeGoksel/Diabetes-Homework/assets/163318769/cd39c756-ab15-4a0a-82d8-213ef2d24ff2)
- Normalize edilmiş veri setinin matrisi:
![download](https://github.com/BilgeGoksel/Diabetes-Homework/assets/163318769/2cd33248-5279-46ee-8c9e-abb3482ea9fe)
- Hiperparametre optimizasyonlu veri setinin matrisi:
  ![download](https://github.com/BilgeGoksel/Diabetes-Homework/assets/163318769/f6cc611f-7a9f-4325-bdcb-b17bf5074a40)
  


