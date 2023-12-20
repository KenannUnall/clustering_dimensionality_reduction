<h1>1.</h1>
Random olarak oluşturulan veri seti toplam 1000 adet veri ve 2 adet özellikten oluşmaktadır. Veri seti 4 farklı küme olacak şeklinde oluşturulmuştur. Verilerin özellikleri yönünden dağılımları aşağıdaki gibidir. 
 ![image](https://github.com/KenannUnall/clustering_dimensionality_reduction/assets/83499398/8031bf85-93a9-4de5-87e5-200c51e228b1)

A.	En optimal küme sayısının(k) otomatik olarak seçilme işlemini her kümeleme işlemi sonucunda elde edilen silhoette_score değerine göre gerçekleştiriyoruz.

Silhoutte Skor: Kümeleme algoritmalarının performansını değerlendirmek için kullanılan bir ölçüdür. Sillhoutte skoru [-1,1] arası değer alır. Silhoutte skorunun yüksek olması verilerin kendi kümelerinde yoğunlaştığını ve diğer kümelerle bağlantılarının düşük benzerlikte olduklarını göstermektedir. 

Aşağıdaki kodda 2 ile 10 değerleri arasında değer alan k için toplamda 9 silhouttte scoru elde edilmiş olup, bu skorlar arasında en yüksek değerin index değeri alınarak k değeri elde edilmiştir. 
![image](https://github.com/KenannUnall/clustering_dimensionality_reduction/assets/83499398/8e7b950d-fa7b-48ca-8395-6eafd6402ab4) ![image](https://github.com/KenannUnall/clustering_dimensionality_reduction/assets/83499398/68819a9a-623f-459d-8e83-1da8123a1613)


       
En yüksek değer k değer 4’te iken elde edildiğinden dolayı küme sayısı 4 olarak seçilmiş ve doğru sonuç elde edilmiştir.
Elde ettiğimiz optimal k değerine göre kümeleme işlemi gerçekleştiriyoruz. Son olarak görselleştirme işlemini gerçekleştiriyoruz. 
 
Görselleştirme işleminde kümeleri ve merkezlerini scatter plot üzerinde gösterilmesi aşağıdaki gibidir.
 
B.	Girdi olarak alınan noktanın bir kümeye dahil olduğunu veya bu noktanın anomali olduğunun tespiti yapılmaktadır. Bu aşamada find_farhest_points fonksiyonu ile veri noktalarının merkezlere olan uzaklıkları hesaplanır ve en uzak noktaların indeksleri alınır. Classify_point fonksiyonu ile de noktanın threshold değerden büyük olup olmaması durumunda göre anomali olup olmadığı belirlenmektedir.

 
 


SORU 2
Hiyarerşik kümelede bağlantı türü olarak ‘ward’, k-means algoritmasına en yakın değeri vermektedir. Aşağıdaki görselleştirmede de görünmektedir.  
 



Optimal küme sayısının (k) hesaplanma işleminde silhoutte skor değeri hesaplanmaktadır. Maksimum silhoutte değerinin index değerine göre k değeri seçilmektedir. 
 

Optimal k değeri silhouette skoru en yüksek olan k=4 olarak elde edilmiştir. Aşağıdaki grafikte de skor değerleri gösterilmektedir.
 
k=4 değerinde silhoutte skor 0.85’ in üzerinde bir değer ile en yüksek değerdedir.



SORU 3
Veri seti 1000 örnekten ve noise 0.05 değerindedir. Gürültü (noise), makine öğrenimi ve veri üretimi bağlamında, verideki rastgele değişim ve bozulmaları ifade eder. Noise, oluşturulan veri setinin 0.05 değerinde bir gürültüye sahip olacağını belirtmektedir. Veri seti 2 farklı kümeden oluşmaktadır.
 
Veri setinin özelliklerine göre dağılımları aşağıdaki görseldeki gibidir. Noise değeri arttıkça bu görüntü daha karmaşık bir hale almaya başlamaktadır. 
 
Veri setinin birinci ve ikinci özelliklerine göre dağılımlarına bakıldığında zincir biçiminde bir dağılım görülmektedir ve iki ayrı küme şeklindedir. 
Average (Ortalama) Bağlantısı: Bu bağlantı yöntemi, her iki küme arasındaki uzaklıkların ortalamasını kullanarak küme birleştirmesi yapar. Yani, her iki kümenin elemanları arasındaki uzaklıkların ortalaması alınarak yeni bir küme oluşturulur. 
Ward Bağlantısı: Bu bağlantı yöntemi, küme içi varyansları minimize etmeyi hedefler. İki kümenin birleştirilmesi durumunda, küme içi varyansın artması en az olan birleştirme seçilir. 
Single (Tek) Bağlantısı: Bu yöntemde, iki küme arasındaki en yakın iki elemanın uzaklığı kullanılır. Yani, her iki kümenin elemanları arasındaki en küçük uzaklıkla birleştirme yapılır. 
Complete (Tam) Bağlantısı: Bu yöntemde, iki küme arasındaki en uzak iki elemanın uzaklığı kullanılır. Yani, her iki kümenin elemanları arasındaki en büyük uzaklıkla birleştirme yapılır.

 
Tek bağlantı(single), kümenin bir zincir biçiminde olması durumunda en iyi sonucu verir. Tam bağlantı(complete), kürecikli/küresel kümeli veriler için daha uygundur.
 
Grafikten de görüldüğü üzere optimal küme sayısı (k) değerini 2 olarak elde edilmiştir. Silhouttte skor değeri en yüksek k=2 iken.
SORU 4
Veri seti 1500 adet örnek ve 3 adet özellikten oluşmaktadır. Üç boyutlu olarak görselleştirildiğinde ‘S’ harfi şeklindedir.
 

Veri seti 3 özellikten oluştuğundan dolayı üç boyutlu görselleştirme aşağıdaki plot_3d fonksiyonu ile yapılmaktadır. Grafik başlığı fig.suptitle fonksiyonu ile belirlenmektedir. Noktalar ax.scatter fonksiyonuyla çizdirilmekte ve renkler points_color parametresindeki değerlere göre belirlenmektedir. ax.view_init fonksiyonuyla ise grafik görünümü ayarlanmaktadır.

 
A.	Bu kısımda veri setindeki örnek sayısı, öznitelik sayısı ve S_points değerlerini güzel şekilde sunabilmek için init_printing() fonksiyonunu ve Matrix() fonksiyonları kullanılmıştır. 

S_points.shape[0] değeri toplam örnek sayısı (n) => 1500
S_points.shape[1] değeri toplam öznitelik sayısı (p) => 3

 

Bu aşama S_pointslerin ortalamasının alınma süreci. Bu bir sonraki adımda her sütunu kendi ortalaması etrafında merkezleştirilmesi için kullanılacaktır.
 






Bu kısımda bir önceki aşamada bahsettiğimiz gibi veri setindeki özniteliklerin ölçeklerinin, her bir öznitelik sütunu kendi ortalaması etrafında simetrik olarak dağılmasını sağlamak için kullanılır.
 
Bu kısımda svd kullanarak matris ayırma işlemi gerçekleştiriyoruz. Ve bu sayede U, S ve Vh değerlerini elde ediyoruz. U matrisi, veri kümesinin satır uzayında temsil edilen yeni bir baz vektör kümesini, S matrisi ise veri kümesinin temel özelliklerini (özdeğerlerini) içerir. Vh matrisi ise veri kümesinin sütun uzayında temsil edilen yeni bir baz vektör kümesini içerir.
 

Daha sonra, V matrisi oluşturuluyor. V matrisinin satırları, veri kümesinin özvektörlerini temsil eder. Özvektörler, veri noktalarının yeni düzleme nasıl dönüştürüleceğini gösterir.	




Son olarak, PCA yöntemi kullanılarak veri noktaları yeni düzleme dönüştürülüyor. mean_centered veri kümesi ile V matrisinin ilk satırı (V[0,:]) arasındaki matris çarpımı yapılıyor ve sonucu pca1 olarak adlandırılan değişkene kaydediyoruz. Benzer şekilde, mean_centered veri kümesi ile V matrisinin ikinci satırı (V[1,:]) arasındaki matris çarpımı yapılıyor ve sonucu pca2 olarak adlandırılan değişkene kaydediyoruz. Yine benzer şekilde, mean_centered veri kümesi ile V matrisinin üçüncü satırı (V[2,:]) arasındaki matris çarpımı yapılıyor ve sonucu pca3 olarak adlandırılan değişkene kaydediyoruz. pca1, pca2 ve pca3 veri noktalarının yeni düzleme dönüştürülmüş hallerini temsil ediyor.	
 

S matrisinin karelerinin (S*S) ve veri kümesinin satır sayısının (S_points_c.shape[0]) bölümü hesaplanarak, her bir özdeğerin açıkladığı varyans miktarı hesaplanır. Bu hesaplama (s^2)/n formülünü kullanır, burada s özdeğerleri temsil eder ve n veri kümesinin satır sayısıdır. Bu hesaplama sonucunda d adında bir dizi elde edilir, her bir özdeğer için bir değer içerir. Daha sonra, d dizisinin her bir elemanını toplamına bölerek, açıklanan varyans miktarının artışını gösteren bir kümülatif toplam hesaplanır. Bu hesaplama np.cumsum fonksiyonuyla yapılır ve sonucu PVE (Proportion of Variance Explained) adlı bir diziye kaydedilir. Bu dizi, her bir özdeğerin açıkladığı varyans miktarının artarak toplamını içerir. Son olarak, plt.plot(PVE) komutuyla PVE dizisinin çizimi yapılır, yani açıklanan varyans miktarının artışını gösteren bir eğri çizdirilir. Bu eğri, her bir özdeğerin katkısının toplam varyans içindeki yüzdesini gösterir.
 
B.	İlk olarak, distances adında bir matris oluşturuluyor. Bu matris, S_points matrisindeki noktalar arasındaki Öklidyen uzaklıklarını içeriyor. S_points[:, np.newaxis] - S_points ifadesi, her bir noktanın diğer noktalardan farkını hesaplar. Ardından, bu farkların kareleri alınarak uzaklık matrisi oluşturulur. Son olarak, np.sqrt fonksiyonu kullanılarak uzaklık matrisinin karekökü alınır. 
Svd kullanarak matris ayırma işlemi gerçekleştiriyoruz. Ve bu sayede U, S ve Vh değerlerini elde ediyoruz. U matrisi, veri kümesinin satır uzayında temsil edilen yeni bir baz vektör kümesini, S matrisi ise veri kümesinin temel özelliklerini (özdeğerlerini) içerir. Vh matrisi ise veri kümesinin sütun uzayında temsil edilen yeni bir baz vektör kümesini içerir.
Sonrasında, V matrisi oluşturulur. V = Vh satırı, Vh matrisini V matrisine atar. Vh matrisinin satırları, bileşenlerin yönünü temsil eder. Son olarak, mean_centered matrisi V matrisinin bileşenlerine çarpılarak veri noktaları yeni düzleme dönüştürülür. np.matmul(mean_centered, V[0,:]) satırı, mean_centered matrisini V matrisinin ilk bileşeniyle çarpar ve pca1 adında bir diziye atar. Benzer şekilde, pca2 ve pca3 dizileri de hesaplanır.

 


 


SORU 5
Bu kısımda kullanılan veri seti 4. Soruda kullanılan veri seti ile aynıdır.	
 

 
Bu kısımda n_neigbors değeri optimal bir değer seçilmeyince çok saçma sonuçlar elde edilmekte. Düşük olarak örneğin 3 seçildiğinde çok hatalı bir görüntü elde edilirken aynı zamanda yüksek değer seçerken de hata giderek artmaktadır. 
Locally Linear Embedding (LLE): Veri kümesini düşük boyutlu bir uzaya dönüştürmek için kullanılan bir manifold öğrenme yöntemidir. LLE, veri noktalarının lokal yapılarını koruyarak, veri kümesinin özünü yakalamaya çalışır.
Yakın komşu seçimi ve ağırlık matrisinin hesaplanması gibi parametrelerin doğru bir şekilde ayarlanması önemlidir. Yanlış parametre seçimi, yanlış sonuçlara yol açabilir.
 LLE, büyük veri kümeleri için hesaplama açısından maliyetli olabilir.
 
  
SORU 6
Boyut indirgeme için lle kullanılmış ve method olarak ltsa seçilmiştir.
LLE algoritması LocallyLinearEmbedding sınıfı kullanılarak uygulanır ve veri kümesi indirgenmiş boyuta dönüştürülür. İndirgenmiş veri seti X_lle değişkenine atanır. 
En uzak iki nokta bulunur. İndirgenmiş veri noktaları arasındaki mesafeler hesaplanır ve en uzak noktaların dizinleri (max_distance_idx) bulunur.
Ardından, bu dizinler kullanılarak orijinal veri noktaları (S_points) üzerindeki en uzak iki nokta (max_distance_points) elde edilir.
En uzak iki nokta arasındaki uzaklık hesaplanır ve distance_between_points değişkenine atanır. Sonuçlar ekrana yazdırılır. 
En uzak iki nokta ve aralarındaki uzaklık (max_distance_points, distance_between_points) ve yeni noktanın geometrik şekil üzerinde veya içinde olup olmadığı (is_inside_shape) yazdırılır.
 







Son olarak yeni nokta, en uzak nokta1 ve en uzak nokta 2 noktaları, ltsa ile indirgenmiş olan veri setinin scatter tablosundaki yayılımının üzerinde işaretlenmiştir.
 
