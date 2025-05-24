Projenin Amacı: Dairenin özelliklerini analiz ederek kira fiyatı tahmini yapan bir makine öğrenmesi modeli geliştirmek.  
Veri Setinin Özellikleri: 
	Veri Seti:  https://www.google.com/url?q=https%3A%2F%2Fwww.kaggle.com%2Fdatasets%2Fdrmurataltun%2Fantalya-muratpaa-daire-kira-cretleri-2024-ocak 
	751 gözlem sayısı ve 19 öznitelik sayısı içerir.
	Veri setindeki öznitelikler: turkey,mahalle,fiyat,brut_alan_m2,net_alan_m2,oda_sayisi,bina_yas,dairenin_bulundugu_kat,bina_kat_sayisi,isitma_turu,banyo_sayisi,balkon,asansor,otopark,esya_durumu,site_icinde,aidat,depozito,sahibi
Veri Ön İşleme :
	Eksik veriler dropna() ile sildim. 
	Kategorik değişkenleri sayısallaştırmak için dummy tuzağı yöntemini kullandım. Kategorik veriler makine öğrenmesinde modelin eğitilmesini zorlaştırır bu sebep ile one hot enccoding gibi işlemler ile sayısallaştırma işlemi gerçekleştirmek işimizi kolaylaştırır. 
	Veri setimizin hedef değişkeni yani makine öğrenmesi modelimizin tahmin etmesini hedeflediğimiz değişken fiyat değişkeni, diğer değişkenler ise hedef değişkenizmiz üzerinde etkili olan bağımsız değişkenlerdir.
	Korelasyon matrisi ile hedef değişkenimiz üzerinde etkili olan bağımsız değişkenlerimizin ilişkilerini gözlemledim. 

 
Modelleme : 
	İlk olarak ver setimizi %80 eğitim ve %20 test olmak üzere ikiye böldüm.
	Daha sonra makine öğrenmesi algoritmalarından olan lineer regresyon ve xgboost regressor ile hedef değişken ile bağımsız değişkenler arasındaki ilişkiyi gözlemledim. 
	Lineer regresyon: Hedef değişken ile bağımsız değişkenler arasında doğrusal bir ilişki ile tahminleme yapar. 
	XGBoost algoritması: Karar ağaçlarını temel alır. Güçlü ve hızlı çalışan bir algoritma türüdür. Yüksek doğruluk oranına sahip olduğu için çoğunlukla tercih edilir. Bunun dışında eksik veriler ile başa çıkabilme, overfittingi ( modelin aşırı öğrenmesi durumudur)  önleyebilmek gibi özellikleri tercih sebebidir. 
Performans Değerlendirme:
	 Bu modelde RMSE(ortalama karesel hata) ve MAPE (yüzde hata sapması) metriklerine başvurdum. 
	Modelimi eğitirken kullandığım veri setinde XGBoost lineer regresyona göre daha iyi sonuçlar verdi. Bu model için  için XGBoost daha başarılı sonuçlar verdi. 
