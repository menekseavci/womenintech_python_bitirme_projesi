Women in Tech Academy Bitirme Projesi

# E COMMERCE VERİ SETİ ANALİZİ
Bir e-ticaret sitesi verileri üzerinde analiz yaptım

---
## Kullanılan Kütüphaneler
* numpy
* pandas
* matplotlib
* seaborn
* warnings

---
## Veri Seti Hakkında 

### order_payments_dataset.csv
* Bu veri setinde 5 sütun 103887 adet satır bulunmaktadır.
* order_id = Sipariş Numarası
* payment_sequential = Sipariş Taksidi
* payment_type = Siparişin ödeme türü
* payment_installments = Siparişin kaç taksit yapıldığı
* payment value = Ödeme Tutarı

Bu veri setinde siparişin her taksidi için aynı order_id'ye sahip bir satır girilmiş, bu sebeple işlemlerimi yaparken order_id üzeriden gruplama yaptım ve payment_value değerlerini order_id gruplarına göre toplayarak siparişin toplam değerini buldum

### products_dataset.csv
* Bu veri seti 9 sütundan oluşmaktadır
* Bu sütunlar product_id üzerinden ürün hakkında bilgi vermektedir.
* Aynı zamanda ürünün kategorisini belirten product_category_name adlı bir sütun bulunmaktadır.

Bu veri setinden ürün kategorileri için inceleme yaparpken faydalandım, bu veri seti sayesinde ürünün hem ürün id'sine hem de ürün kategorisine ulaşabiliyoruz.


### order_items_dataset.csv
* Bu veri seti siparişiteki ürünlerin fiyatı, kargo ücreti vee satıcısı hakkında bilgi vermektedir.
* order_id, product_id, seller_id sütunları ile siparişin satıcısı, sipariş detayları hakkında diğer veri setleri ile birleştirerek bilgi edindim.
* price sütunu ürünün fiyatı hakkında bilgi edindim.

### orders_dataset.csv
* Bu veri seti siparişin satın alınma, onaylanma, kargoya verilme ve müşteriye ulaşma tarih bilgilerini içermektedir.
* order_status sütunu siparişin hngi aşamada olduğunu belirtmektedir.
* order_estimates_delivery_dates sütunu siparişin ödemesi alındıktan sonra sipariş için tahmini teslimat tarihi için oluşturulan veriyi içermektedir.

Bu veri seti ile siparişlerin müşteriye ulaşma tarihi ile tahmini teslimat tarihi arasında karşılaştırma yaptım

### sellers_dataset.csv
* Bu veri setindeki sütunlar satıcılar hakkında bilgi vermektedir
* seller_id = satıcı id'si
* seller_city = satıcının bulunduğu şehir
* seller_state = satıcının bulunduğu eyalet

Bu veri seti ile hangi eyalette ne kadar satıcı olduğuyla ilgili analiz yaptım.

### order_reviews_dataset.csv
* Bu veri seti müşteri yorumlarını ve puanlamalarını içermektedir.
* review_id = yorum id'si
* order_id = sipariş id'si
* review_score = müşterinin ürüne puanı

Bu veri setini order_items, products veri setleri ile birleştirerek ürün bazında ortalama puanları elde ettim. Ürünleri kategorilere göre gruplayarak her kategorinin ortalama puanını elde ettim.

### product_category_name_translation.csv
* Bu veri setinde ürün kategorileri ve bunların ingilizce karşılıkları bulunmaktadır.
* Bu veri setini diğer veri setleri ile birleştirerel siparişleri ingilizce kategorilerine göre kategorilendirdim.
