# TeknikServis

1 - Randevu Hizmetleri - Kullanıcı Menüsü

* Müşteriler sistemden kayıt olduktan sonra randevu alabilmek için aşağıdaki akışı kullanabilmelidir.

* Sistemin belirlediği ilk boş gün ve saatte randevu veriliyor olmalıdır

* Yapılacak işlem ve eklenen optional not (en fazla 300 karakter) belirtmelidir

* Servis randevu sonucunda randevu id sini döndürmelidir

* Bu id ile randevu bilgileri başka bir servisten alınabilmelidir

* DeleteById işlemi ile müşteri kendi randevusunu silebilmelidir

* Bir gün 10 saattir. Sistem bir sonraki randevuyu günlük 10 saatten fazla iş olmayacak şekilde otomatik hesaplar. Bugün 1 disk kurtarma işlemi olduğunda bir sonraki randevu ne olursa olsun yarına vermelidir gibi.

2 - Randevu Hizmetleri - Admin Menüsü

* Admin kullanıcılar sisteme login olduktan sonra 2. el satış kaydedebilecektir (Sale tablosu)

* Bu servis 4 adet üründen 1 tanesini (CPU, GPU, RAM, Motherboard) ve bu ürünle ilgili notu ve fiyatını parametre olarak alacaktır

* Kaydedilen bütün satış bilgileri getall metodu ile alınabilecektir

* Bu satış bilgileri deletebyid ile silinebilir

* Bu servisler sadece admin kullanıcılarına açık olacaktır

3 - İkinci El Satış İşlemleri - Admin Menüsü

* Admin kullanıcılar sisteme login olduktan sonra 2. el satış kaydedebilecektir (Sale tablosu)

* Bu servis 4 adet üründen 1 tanesini (CPU, GPU, RAM, Motherboard) ve bu ürünle ilgili notu ve fiyatını parametre olarak alacaktır

* Kaydedilen bütün satış bilgileri getall metodu ile alınabilecektir

* Bu satış bilgileri deletebyid ile silinebilir

* Bu servisler sadece admin kullanıcılarına açık olacaktı

4 - İkinci El Alım İşlemleri - Kullanıcı Menüsü

* Sistemde kullanıcılar login oldukları takdirde 2. el satılan ürünleri listeleyebilirler

* Bir getmapping işlemi ile işlemci, Ekran kartı, Ram ve Anakart satışlarını listeleyebilmelidirler

* Bu ürünler 2. el olarak satın alınabilen ürünlerdir. Response içerisinde fiyatları, girilen notlar ve ürün bilgisi yazılacaktır

* Satılan ürünlerde parça ile arama yapılabilmelidir (anakartalar, ekran kartları veya işlemciler gibi)

* Bir postmapping ile bu satış id si ve kredi kartı bilgisi gönderilip satış gerçekleşecektir

* Yapılan satışlar veritabanında satış_log tablosunda kullanıcıid, ürün bilgisi, tarih saat ve fiyat olarak tutulacaktır

* Satış yapıldıktan sonra satılan ürün satın alma işlemi bittikten sonra direkt olarak silinecektir. Aynı üründen birden fazla satış girilmelidir eğer birden fazla satılıyorsa.

5 - İkinci El Satış İşlemleri - Kullanıcı Menüsü

* Kullanıcılar 2. el satış için yani teknik servisin 2. el parçacı alması için teklif verebilecektir. (Proposal tablosu)

* Sisteme giriş yapıldıysa 4 bilgisayar parçasından birisi (CPU, Ram, GPU, Motherboard) ile beraber not ve fiyat bilgileri bir post mapping ile gönderilecektir

* Bundan sonrası için randevuya gerek yoktur.

* Sistemde kayıtlı tekliflerini listeleme ve id ile silme endpointi olmalıdır

* Adminler bu teklifleri reddedebilir veya onaylayabilir. Onaylanırsa müşteri istediği zaman servise gidecek ve işini halledecektir.

6 - İkinci El Alım İşlemleri - Admin Menüsü

* Sistemde admin kullanıcılar müşterilerin girdiği teklifleri (hemen üstteki işlem) gelen teklifler servisinden görecektir.

* Bu serviste bütün teklifler listelenebilecektir

* GetByID metodu ile hangi parça olduğu, fiyatı ve not bilgileri alınabilecektir

* Bir postmapping ile teklif id göndererek onay veya red işlemleri yapabilecektir. Bu servisten cevap olarak teklif bilgileri dönmelidir güncel hali ile.
Bu sayede müşteriler listelediğinde teklif durumlarını görür. Teklifler adminler tarafından silinmez.

7 - Login İşlemleri

* Sistemde kullanıcı adı ve email ve şifre ile kayıt yapılabilmelidir.

* Sistemde aşağıdaki 2 bilgi hazır olarak bulunmalıdır, testleri yapabilmek için

* 2 rol (ADMIN ve USER) sistemde script ile insert edilecektir (data.sql)

* 2 kullanıcı (bir admin bir user rolünde) sistemde script ile insert edilecektir (data.sql)

* Login yapılınca bir jwt token döndürülmelidir

* Yetki isteyen servisler jwt tokenı ile çalışacaktır
