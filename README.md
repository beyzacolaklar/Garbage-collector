  ## Garbage-collector ve Generic Classlar
C# garbage collector 
Garbage Collector, C# ve Java gibi yüksek seviyeli dillerde heap belleğinin verimli yönetilmesini sağlar. Kullanılmayan alanları temizleyerek bu bölgeleri yeni nesneler için tekrar kullanılabilir hale getirir.Bellek sızıntılarını önlemeye yardımcı olur.Nesneleri yaşlarına göre gruplandırarak daha etkili bir temizlik yapar(Generational Approach).
Garbage collector, uygulama çalışırken bellek alanını izler ve kullanılmayan nesneleri tespit ettiğinde, bu nesneleri temizlemek için bir toplama döngüsü başlatır. Bu işlem, uygulamanın performansını en iyi duruma getirmek için arka planda gerçekleşir.


  __Generic Yapıların Avantajları__
- **Tip Güvenliği:** Generic yapılar, belirli bir veri türüyle çalışmaya olanak tanır ve yanlış tür kullanımını daha kod çalıştırılmadan, derleme aşamasında tespit eder.  
- **Esneklik ve Kullanım Kolaylığı:** Tek bir generic sınıf veya metot, farklı veri türleriyle uyumlu çalışabilir. Örneğin, `List<T>` sınıfı hem tamsayıları hem de metinleri saklayabilir.  
- **Daha Yüksek Performans:** Değer türleri için **boxing ve unboxing** işlemlerine gerek kalmaz, böylece bellek yönetimi daha verimli olur.  
- **Kodun Tekrar Kullanılabilirliği:** Generic yapılar, farklı veri türleriyle çalışabilen esnek bir kod yapısı sunarak bakım ve geliştirme süreçlerini kolaylaştırır.
  
**not** :Boxing ve Unboxing, C# gibi dillerde değer türleri ve referans türleri arasındaki dönüşüm işlemleridir. **Boxing**, bir değer türünün (örneğin, int, char, struct) bir referans türüne (örneğin, object) dönüştürülmesi işlemidir. Bu işlem, değer türünü bir nesne (object) olarak bellek içinde "kutuya" alır.
örnek:
int num = 10;          // Değer türü  
object obj = num;     // Boxing işlemi  
**Unboxing**: Unboxing, bir referans türündeki bir nesnenin tekrar değer türüne dönüştürülmesi işlemidir. Bu işlem, boxing ile oluşturulan nesneden orijinal değer türünü geri almak için kullanılır.
örnek:
object obj = 10;        // Boxing (önceden boxing yapılmış bir nesne)  
int num = (int)obj;    // Unboxing işlemi  

Boxing, bir değer türünün yeni bir nesne olarak oluşturulmasını gerektirdiği için ek bellek kullanımı ortaya çıkar. Bu durum, özellikle büyük veri koleksiyonlarında veya sık tekrarlanan işlemlerde performansı olumsuz etkileyebilir.
Unboxing sürecinde ise, bir nesneden değer türünü geri almak için nesne referansının uygun türde olup olmadığını kontrol etmek gerekir. Bu da ek işlem süresi gerektirebilir.
