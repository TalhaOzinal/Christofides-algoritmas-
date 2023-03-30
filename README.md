# Christofides-algoritmas-

Christofides algoritması, mesafelerin metrik bir uzay oluşturduğu durumlarda (simetrik ve üçgen eşitsizliğine uyan) gezgin satıcı problemine yaklaşık çözümler bulmak için kullanılan bir algoritmadır. Bu algoritma, çözümlerinin optimal çözüm uzunluğunun 3/2’si içinde olacağını garanti eden bir yaklaşım algoritmasıdır.

Algoritma şu şekilde çalışır: G = (V,w) gezgin satıcı probleminin bir örneği olsun. G, V köşe kümesi üzerinde tam bir grafiktir ve w fonksiyonu G’nin her kenarına pozitif bir gerçek ağırlık atar. Üçgen eşitsizliğine göre, her üç köşe u, v ve x için w(uv) + w(vx) ≥ w(ux) olmalıdır. Daha sonra algoritma şu şekilde açıklanabilir:

1.G’nin minimum kapsayan ağacını T olarak oluşturun.
2.T’de tek dereceli köşelerin kümesini O olarak belirleyin.
3.O’nun indüklenmiş alt grafiğinde minimum ağırlıklı mükemmel eşleştirme M’yi bulun.
4.M ve T’nin kenarlarını birleştirerek her köşenin çift dereceli olduğu bağlı bir çoklu grafik H oluşturun.
5.H’de Eulerian devresi oluşturun.
6.Önceki adımda bulunan devreyi tekrarlanan köşeleri atlayarak (kısayol) Hamilton devresine dönüştürün.

Bu adımların 5 ve 6’sı mutlaka tek bir sonuç vermeyebilir. Bu nedenle sezgisel olarak farklı yollar verebilir.


Christofides algoritması, verilen bir tam ağırlıklı graf için yaklaşık olarak minimum ağırlıklı Hamilton döngüsü (TSP) bulmak için kullanılan bir algoritmadır.

Algoritma, şu adımlardan oluşur:

1.Grafın minimum ağırlıklı çiftlerini bulun.

2.Bulunan minimum ağırlıklı çiftlerin oluşturduğu çiftleştirilmiş grafın minimum ağırlıklı tam eşleştirmesini bulun.

3.Oluşan minimum ağırlıklı tam eşleştirmeyi çiftleştirilmiş grafa ekleyin ve böylece Euler grafi oluşacaktır.

4.Euler grafi üzerinde Euler turu oluşturun.

5.Euler turunu Hamilton döngüsüne dönüştürmek için, Euler turu üzerinde herhangi bir tekrar eden düğümü kaldırın.

Christofides algoritması, her bir adımın zaman karmaşıklığına sahiptir.

1.Adım: Grafın minimum ağırlıklı çiftlerini bulma, bir çiftli graf oluşturma ve minimum ağırlıklı tam eşleştirme bulma adımları için, verilen grafın boyutuna bağlı olarak O(n^3) zaman karmaşıklığına sahiptir.

2.Adım: Minimum ağırlıklı tam eşleştirme adımı, grafin boyutuna bağlı olarak O(n^3) zaman karmaşıklığına sahiptir.

3.Adım: Euler grafi oluşturma adımı için, O(n^2) zaman karmaşıklığına sahiptir.

4.Adım: Euler turu oluşturma adımı için, O(n) zaman karmaşıklığına sahiptir.

5.Adım: Euler turunu Hamilton döngüsüne dönüştürme adımı, O(n) zaman karmaşıklığına sahiptir.

Bu nedenle, Christofides algoritmasının toplam zaman karmaşıklığı, O(n^3) + O(n^3) + O(n^2) + O(n) + O(n) = O(n^3) olarak ifade edilir.

En iyi durumda, Christofides algoritması, TSP probleminin gerçek minimumunu bulur ve bu durumda doğru sonuç verir. En kötü durumda, yaklaşık çözüm, gerçek minimumun 1.5 katını aşabilir. Ortalama olarak, Christofides algoritması, gerçek minimumun 1.5 katını aşmayan yaklaşık bir sonuç üretir.

Christofides algoritması sınırı, yaklaşık olarak minimum ağırlıklı Hamilton döngüsü için elde edilebilecek en iyi yaklaşım oranı olan 3/2'dir. Bu sınır, algoritmanın adımlarından bazılarının özelliklerine dayanır ve algoritmanın gerçek minimumdan daha kötü bir sonuç üretmeyeceği garantilidir.




# Shift Or algorithm

Shift Or algoritması, verilen bir kalıbın bir dizgede olup olmadığını kontrol etmek için bit düzeyinde teknikler kullanan bir algoritmadır. Kalıp uzunluğu makinenin bellek kelime boyutundan daha küçükse verimlidir.

Algoritma şu şekilde çalışır: Dize ve kalıp girdi olarak alınır. 256 boyutunda (ASCII karakterlerinin toplam sayısı) bir dizi olan pattern_mask oluşturulur ve ~0 ile başlatılır. Daha sonra kalıp gezilir ve pattern_mask [pattern [i]]'nin sağdan i’nci bitini 0’a başlatılır.


Shift Or algoritması, bir veri kümesindeki elemanların toplamı en çok verilen sınır değerini (threshold) aşmayacak şekilde alt kümelerine bölünmesi problemi için kullanılan bir algoritmadır. Algoritma, sıralama ve önbellek (cache) kullanımına dayanır.

Algoritma, şu adımlardan oluşur:

1.Veri kümesini sıralayın.

2.Önbellek (cache) boyutunu belirleyin.

3.Sıralanmış veri kümesinin ilk öğesinden başlayarak, önbellekte (cache) biriktirilen toplamın sınır değerini aşmayacak şekilde alt kümeleri oluşturun.

4.Önbellek (cache) dolduğunda, en küçük toplamı olan alt küme öğesini çıkarın ve yerine bir sonraki öğeyi ekleyin.

5.Tüm alt kümeler için en küçük toplamı olan öğeleri seçin ve birleştirin.

Shift Or algoritması, her bir adımın zaman karmaşıklığına sahiptir.

1.Adım: Veri kümesini sıralama adımı için, veri kümesinin boyutuna bağlı olarak O(n log n) zaman karmaşıklığına sahiptir.

2.Adım: Önbellek (cache) boyutu belirleme adımı, sabit bir zamanda gerçekleşir.

3.Adım: Alt kümeleri oluşturma adımı için, veri kümesinin boyutuna bağlı olarak O(n) zaman karmaşıklığına sahiptir.

4.Adım: Önbellek (cache) dolduğunda en küçük toplamı olan alt küme öğesini çıkarma ve yerine bir sonraki öğeyi ekleme adımı için, O(1) zaman karmaşıklığına sahiptir.

5.Adım: Tüm alt kümeler için en küçük toplamı olan öğeleri seçme ve birleştirme adımı için, veri kümesinin boyutuna bağlı olarak O(n^2) zaman karmaşıklığına sahiptir.

Bu nedenle, Shift Or algoritmasının toplam zaman karmaşıklığı, O(n log n) + O(n) + O(n) + O(1) + O(n^2) = O(n^2) olarak ifade edilir.

En iyi durumda, Shift Or algoritması, verilen sınır değeri için tam olarak doğru alt kümeleri oluşturur ve bu durumda doğru sonuç verir. En kötü durumda, algoritma her öğe için ayrı bir alt küme oluşturur ve toplamda n^2 adet alt küme oluşturarak en kötü performansı gösterir. Ortalama olarak, Shift Or algoritması verilen sınır değerini aşmayacak şekilde yaklaşık olarak optimum alt kümeleri oluşturur.
