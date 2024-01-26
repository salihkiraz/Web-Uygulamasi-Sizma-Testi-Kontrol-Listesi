# Web Uygulaması Sızma Testi Kontrol Listesi

- ** Bilgi Toplama Aşaması**
    - [ ] Web sunucusunu, teknolojilerini ve veritabanını tanımlama
    - [ ] İştirak ve Satın Alma Keşfi
    - [ ] Ters Arama(Reverse Lookup)
    - [ ] ASN & IP Alanı Keşfi ve Hizmet Numaralandırma
    - [ ] Google Dorking
    - [ ] Github Recon
    - [ ] Dizin Keşfi
    - [ ] IP Aralığı Keşfi
    - [ ] JS Dosyaları Analizi
    - [ ] Alt Alan Adı Keşfi ve Bruteforcing
    - [ ] Alt Alan Adı Devralma
    - [ ] Parametre Bulanıklaştırma
    - [ ] Port Tarama
    - [ ] Şablon Tabanlı Tarama (Nuclei)
    - [ ] Wayback Geçmişi
    - [ ] Bozuk Bağlantı Korsanlığı
    - [ ] Arama Motoru Keşfi
    - [ ] Yanlış Yapılandırılmış Bulut Depolama
- **Kayıt Olma Özellik Testi**
    - [ ] Mükerrer kayıt olup olmadığını kontrol et/Mevcut kullanıcının üzerine yaz
    - [ ] Zayıf parola politikasını kontrol edin
    - [ ] Mevcut kullanıcı adlarının yeniden kullanımını kontrol edin
    - [ ] E-posta doğrulama işleminin yetersiz olup olmadığını kontrol edin
    - [ ] Zayıf kayıt uygulaması-Tek kullanımlık e-posta adreslerine izin verir
    - [ ] Zayıf kayıt uygulaması-HTTP üzerinden
    - [ ] Özel olarak hazırlanmış kullanıcı adı kayıtları ile varsayılan web uygulama sayfalarının üzerine yazın. => Kayıt olduktan sonra, profil bağlantınız [www.tushar.com/](http://www.chintan.com/chintan)tushar gibi bir şey görünüyor mu?
    
            a. Eğer öyleyse, web uygulamasının /images, /contact, /portfolio gibi varsayılan klasörlerini numaralandırın 
            
            b. Resimler, iletişim, portföy gibi kullanıcı adını kullanarak bir kayıt yapın 
            
            c. Bu varsayılan klasörlerin profil bağlantınız tarafından üzerine yazılıp yazılmadığını kontrol edin.
    
- **Oturum Yönetimi Testi**
    - [ ] Uygulamadaki toplu çerezlerden gerçek oturum çerezini tanımlama
    - [ ] Base64, hex, URL, vb. gibi bazı standart kod çözme algoritmalarını kullanarak çerezleri çözün
    - cookie.session token değerini 1 bit/byte değiştirin. Ardından yeniden gönderin ve tüm belirteçler için aynısını yapın. Belirtecin hangi kısmının gerçekten kullanıldığını ve hangisinin kullanılmadığını belirlemek için gerçekleştirmeniz gereken iş miktarını azaltın
    - [ ] Kendi kendine kayıt mevcutsa ve kullanıcı adınızı seçebiliyorsanız, A, AA, AAA, AAAA, AAAB, AAAC, AABA ve benzeri gibi aralarında küçük farklılıklar içeren bir dizi benzer kullanıcı adıyla oturum açın. Oturum açma sırasında kullanıcıya özel başka bir veri gönderilirse veya kullanıcı profillerinde saklanırsa (e-posta adresi gibi)
    - [ ] Oturum çerezlerini ve çerez son kullanma tarihini/saatini kontrol edin
    - [ ] Çerez etki alanı kapsamını tanımlama
    - [ ] Çerezde HttpOnly bayrağını kontrol edin
    - [ ] Uygulama SSL üzerinden ise çerezde Güvenli(Secure) bayrağını kontrol edin
    - [ ] Oturum sabitlemesini, yani kimlik doğrulamadan önce ve sonra oturum çerezinin değerini kontrol edin
    - [ ] Sunucunun makinenin durumunu koruyup korumadığını kontrol etmek için oturum çerezini farklı bir etkin IP adresinden veya sistemden yeniden oynatın
    - [ ] Farklı makine/IP üzerinden eşzamanlı oturum açma kontrolü
    - [ ] Çerez değerinde kullanıcıya ait herhangi bir bilginin saklanıp saklanmadığını kontrol edin Evet ise, diğer kullanıcı verileriyle kurcalayın
    - [ ] Oturumun Geçersiz Kılınamaması (E-posta Değişikliği, 2FA Etkinleştirme)
- **Kimlik Doğrulama Testi**
    - [ ] Kullanıcı adı keşfi
    - [ ] Kullanıcı adı ve parola alanında çeşitli SQL Enjeksiyonları kullanarak kimlik doğrulamasını atlayın
    - Şifre onayı eksikliği
        - [ ] E-posta adresini değiştir
        - [ ] Şifre değiştirme
        - [ ] 2FA'yı Yönet
    - [ ] Kimlik doğrulaması olmadan kaynakları kullanmak mümkün mü? Erişim ihlali
    - [ ] Kullanıcı kimlik bilgilerinin SSL üzerinden iletilip iletilmediğini kontrol edin
    - [ ] Zayıf oturum açma işlevi HTTP ve HTTPS'nin her ikisi de kullanılabilir
    - Kaba kuvvet saldırısında kullanıcı hesabı kilitleme mekanizmasını test edin
        
        Varyasyon : Sunucu anlık kullanıcı isteklerini engelliyorsa, saldırganın zaman kısıtlama seçeneğini deneyin ve işlemi tekrarlayın.
        
        - [ ] Kullanıcı aracısını Mobil Kullanıcı aracısına kurcalayarak işlem sınırlamasını(rate limit) atlayın
        - [ ] Kullanıcı aracısını Anonim kullanıcı aracısına kurcalayarak işlem sınırlamasını(rate limit) atlama
        - [ ] Boş bayt kullanarak işlem sınırlamasını(rate limit) atlayın
    - [ ] cewl komutunu kullanarak bir parola sözcük listesi oluşturma
    - Oauth oturum açma işlevselliğini test edin
        - OAuth Rolleri
            - [ ] Kaynak Sahibi → Kullanıcı
            - [ ] Kaynak Sunucusu → Twitter
            - [ ] İstemci Uygulaması → [Twitterdeck.com](http://twitterdeck.com/)
            - [ ] Yetkilendirme Sunucusu → Twitter
            - [ ] client_id → Twitterdeck ID (Bu, herkese açık, gizli olmayan benzersiz bir tanımlayıcıdır_
            - [ ] client_secret → Twitter ve Twitterdeck tarafından access_tokens oluşturmak için bilinen Gizli Belirteç
            - [ ] response_type → Belirteç türünü tanımlar, örneğin (kod, belirteç, vb.)
            - [ ] scope → Twitterdeck'in istediği erişim seviyesi
            - [ ] redirect_uri → Yetkilendirme tamamlandıktan sonra kullanıcının yönlendirileceği URL
            - [ ] durumu → OAuth'daki ana CSRF koruması, kullanıcının yetkilendirme sunucusuna yönlendirilmesi ve tekrar geri dönmesi arasında verileri sürdürebilir
            - [ ]  grant_type → Grant_type ve döndürülen token türünü tanımlar
            - [ ] code → twitter tarafından oluşturulan yetkilendirme kodu ?code= şeklinde olacaktır, kod bir access_token almak için client_id ve client_secret ile birlikte kullanılır
            - [ ] access_token → twitterdeck'in kullanıcı adına API istekleri yapmak için kullandığı token
            - refresh_token → Bir uygulamanın kullanıcıya sormadan yeni bir access_token almasını sağlar
        - Kod Kusurları
            - [ ] Kodun Yeniden Kullanılması
            - [ ] Kod Tahmini/Bruteforce ve İşlem Sınırı(rate limit)
            - [ ] X uygulamasının kodu Y uygulaması için geçerli mi?
        - Redirect_uri Kusurları
            - [ ] URL hiç doğrulanmadı: ?redirect_uri=https://attacker.com
            - [ ] Alt alan adlarına izin verilir (Bu alt alan adlarında Alt Alan Adı Devralma veya Açık yönlendirme): ?redirect_uri=https://sub.twitterdeck.com
            - [ ] Ana bilgisayar doğrulandı, yol (Chain değil açık yönlendirme): ?redirect_uri=https://twitterdeck.com/callback?redirectUrl=https://evil.com
            - [ ] Ana bilgisayar doğrulandı, yol doğrulanmadı (Referer sızıntıları): HTML sayfasına harici içerik ekleyin ve Referer aracılığıyla kod sızdırın
            - [ ] Zayıf Regexler
            - [ ] Ana bilgisayardan sonra URL kodlu karakterlerin acımasızca değiştirilmesi: redirect_uri=https://twitterdeck.com§FUZZ§
            - [ ] Anahtar kelimeleri ana bilgisayardan sonra beyaz listeye (veya herhangi bir beyaz liste açık yönlendirme filtresine) bruteforcing: ?redirect_uri=https://§FUZZ§.com
            - [ ] URI doğrulaması yerinde: tipik açık yönlendirme yüklerini kullanın
        - Durum(State) Kusurları
            - [ ] Eksik Durum parametresi? (CSRF)
            - [ ] Öngörülebilir Durum parametresi?
            - [ ] Durum parametresi doğrulanıyor mu?
        - Yanlış
            - [ ] client_secret'i doğrulandı mı?
            - [ ] Facebook telefon numarası kaydı kullanılarak ATO öncesi
            - [ ] E-posta doğrulaması yok Ön ATO
    - 2FA Yanlış Yapılandırmasını Test Edin
        - [ ] Yanıt Manipülasyonu
        - [ ] Durum Kodu
        - [ ] Manipülasyon
        - [ ] Yanıtta 2FA Kodu Sızıntısı
        - [ ] 2FA Kodunun Yeniden Kullanılabilirliği
        - [ ] Kaba Kuvvet Koruması Eksikliği
        - [ ] Eksik 2FA Kodu Bütünlük Doğrulaması
        - [ ] Null veya 000000 ile
- **Hesabım (Giriş Sonrası) Testi**
    - [ ] Aktif hesap kullanıcı kimliğini kullanan parametreyi bulun. Diğer hesapların ayrıntılarını değiştirmek için onu kurcalamaya çalışın
    - [ ] Yalnızca bir kullanıcı hesabıyla ilgili özelliklerin bir listesini oluşturun. E-posta Değiştir Şifre Değiştir -Hesap ayrıntılarını değiştir (İsim, Numara, Adres, vb.) CSRF'yi dene
    - [ ] Giriş sonrası e-posta kimliğini değiştirin ve mevcut herhangi bir e-posta kimliği ile güncelleyin. Sunucu tarafında doğrulanıp doğrulanmadığını kontrol edin. Uygulama yeni bir kullanıcıya yeni bir e-posta onay bağlantısı gönderiyor mu göndermiyor mu? Bir kullanıcı bağlantıyı belirli bir zaman diliminde onaylamazsa ne olur?
    - Profil resmini yeni bir sekmede açın ve URL'yi kontrol edin. E-posta kimliği/kullanıcı kimliği bilgilerini bulun. EXIF Coğrafi Konum Verileri Yüklenen Görüntülerden Çıkarılmıyor.
    - [ ] Uygulama sağlıyorsa hesap silme seçeneğini kontrol edin ve şifremi unuttum özelliği ile bunu onaylayın
    - E-posta kimliğini, hesap kimliğini, kullanıcı kimliği parametresini değiştirin ve diğer kullanıcının şifresini kaba kuvvetle zorlamaya çalışın
    - [ ] Kimlik doğrulama sonrası özellikler için hassas işlem gerçekleştirirken uygulamanın yeniden kimlik doğrulaması yapıp yapmadığını kontrol edin
- **Şifre Testini Unuttum**
    - [ ] Oturum Kapatma ve Parola sıfırlamada oturumun geçersiz kılınmaması
    - [ ] Şifre sıfırlama bağlantısını/kodunu unutma benzersizliğini kontrol edin
    - [ ] Kullanıcı tarafından belirli bir süre kullanılmadığında sıfırlama bağlantısının süresinin dolup dolmadığını kontrol edin
    - [ ] Kullanıcı hesabı tanımlama parametresini bulma ve diğer kullanıcının şifresini değiştirmek için Id veya parametre değerini kurcalama
    - [ ] Zayıf parola politikasını kontrol edin
    - [ ] Zayıf şifre sıfırlama uygulaması Token kullanımdan sonra geçersiz kılınmıyor
    - [ ] Sıfırlama bağlantısının tarih ve saat gibi başka bir parametresi varsa. Sıfırlama bağlantısını etkin ve geçerli kılmak için tarih ve saat değerini değiştirin
    - [ ] Güvenlik soruları sorulup sorulmadığını kontrol edin? Kaç tahmine izin veriliyor? --> Kilitleme politikası sürdürülüyor mu, sürdürülmüyor mu?
    - [ ] Yeni şifre ve onaylanmış şifreye sadece boşluk ekleyin. Sonra enter tuşuna basın ve sonucu görün
    - [ ] Şifremi unuttum formatı tamamlandıktan sonra aynı sayfada eski şifre görüntüleniyor mu?
    - [ ] İki şifre sıfırlama bağlantısı isteyin ve kullanıcının e-postasındaki eski şifreyi kullanın
    - [ ] Parola değiştirildiğinde aktif oturumun yok edilip edilmediğini kontrol edin?
    - [ ] Zayıf parola sıfırlama uygulaması HTTP üzerinden gönderilen parola sıfırlama belirteci
    - [ ] Sıralı belirteçler gönderebilmesi için sürekli parolayı unut istekleri gönderme
- **Bize Ulaşın Form Testi**
    - email flooding saldırılarını kısıtlamak için bize ulaşın formunda CAPTCHA uygulanıyor mu?
    - [ ] Sunucuya dosya yüklemeye izin veriyor mu?
    - [ ] Kör XSS
- **Ürün Satın Alma Testi**
    - Şimdi Satın Al
        - [ ] Düşük ödüllü yüksek değerli başka bir ürün satın almak için ürün kimliğini tahrif etme
        - [ ] Kurcalanmış ürün verileri aynı ödüle sahip ürün sayısını artırmak için
    - Hediye/Kupon
        - [ ] Kullanılacak kupon/hediye sayısını artırmak/azaltmak için (varsa) talepteki hediye/kupon sayısını değiştirin
        - [ ] Kuponun değerini para cinsinden artırmak/azaltmak için hediye/kupon değerini değiştirin. (örn. 100 $ kupon olarak verilir, parayı artırmak veya azaltmak için değeri kurcalayın)
        - [ ] Parametre kurcalamada eski hediye değerlerini kullanarak hediyeyi/kuponu yeniden kullanın
        - [ ] Hediye/kupon parametresinin benzersizliğini kontrol edin ve diğer hediye/kupon kodunu tahmin etmeyi deneyin
        - [ ] BurpSuite isteğinde aynı parametre adını ve değerini & ile tekrar ekleyerek aynı kuponu iki kez eklemek için parametre kirliliği tekniğini kullanın
    - Sepetten Ürün Ekleme/Silme
        - [ ] Diğer kullanıcının sepetinden ürün silmek için kullanıcı kimliğini değiştir
        - [ ] Diğer kullanıcının sepetinden ürün eklemek/silmek için sepet kimliğini değiştir
        - [ ] Diğer kullanıcının hesabından eklenen öğeleri görüntülemek için sepet özelliği için sepet kimliği/kullanıcı kimliği tanımlayın
    - Adres
        - [ ] BurpSuite'in diğer kullanıcının gönderim adresini sizinkiyle değiştirme isteğini kurcalayın
        - [ ] Gönderi adresine XSS vektörü ekleyerek depolanmış XSS'yi deneyin
        - [ ] Aynı ürünü iki teslimat adresine göndermek için uygulamayı manipüle etmeye çalışmak yerine iki teslimat adresi eklemek için parametre kirliliği tekniğini kullanın
    - Sipariş Verin
        - [ ] Ödeme yöntemini değiştirmek için ödeme seçenekleri parametresini kurcalayın. Örneğin, bazı ürünlerin teslimatta nakit olarak sipariş edilemeyeceğini düşünün, ancak talep parametrelerini banka / kredi / PayPal / ağ bankacılığı seçeneğinden teslimatta nakit olarak değiştirmenize izin verebilir.
        söz konusu ürün için sipariş verin
        - [ ] Her bir ana ve alt talep ve yanıtta ödeme manipülasyonu için miktar değerini kurcalayın
        - [ ] CVV'nin açık metin olarak gidip gitmediğini kontrol edin
        - [ ] Uygulamanın kendisinin kart bilgilerinizi işleyip işlem yapıp yapmadığını veya işlem yapmak için herhangi bir üçüncü taraf ödeme işleme şirketini arayıp aramadığını kontrol edin
    - Parça Sırası
        - [ ] Sipariş takip numarasını tahmin ederek diğer kullanıcının siparişini takip edin
        - [ ] Diğer kullanıcıların toplu siparişlerini takip etmek için takip numarası ön ekini veya son ekini kaba kuvvetle zorlama
    - İstek listesi sayfası testi
        - [ ] Bir A kullanıcısının diğer B kullanıcısının hesabındaki İstek Listesine ürün ekleyip ekleyemeyeceğini kontrol edin
        - [ ] Bir A kullanıcısının kendi (A kullanıcısının) İstek Listesi bölümünden B kullanıcısının sepetine ürün ekleyip ekleyemeyeceğini kontrol edin.
    - Ürün satın alma sonrası testi
        - [ ] A kullanıcısının B kullanıcısının satın alma siparişlerini iptal edip edemeyeceğini kontrol edin
        - [ ] A kullanıcısının B kullanıcısı tarafından önceden verilmiş siparişleri görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] A kullanıcısının B kullanıcısı tarafından verilen siparişin sevkiyat adresini değiştirip değiştiremeyeceğini kontrol edin
    - Bant dışı test
        - [ ] Kullanıcı stokta olmayan ürünü sipariş edebilir mi?
- **Bankacılık Uygulama Testi**
    - Faturalama Faaliyeti
        - [ ] 'A' kullanıcısının 'B' kullanıcısının hesap özetini görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı için işlem raporunu görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı için özet raporu görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı adına e-posta yoluyla aylık/haftalık hesap özeti için kayıt olup olamayacağını kontrol edin
        - [ ] Kullanıcı 'A'nın aylık/haftalık hesap özetini almak için kullanıcı 'B'nin mevcut e-posta kimliğini güncelleyip güncelleyemeyeceğini kontrol edin
    - Mevduat/Kredi/Bağlı/Harici Hesap Kontrolü
        - [ ] 'A' kullanıcısının 'B' kullanıcısının mevduat hesabı özetini görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] Mevduat hesapları için hesap bakiyesi tahrifatını kontrol edin
    - Vergi İndirimi Sorgulama Testi
        - [ ] 'A' kullanıcısının 'a' müşteri kimliği ile 'B' kullanıcısının 'b' müşteri kimliğini kurcalayarak vergi kesintisi ayrıntılarını görüp göremeyeceğini kontrol edin
        - [ ] Faiz oranını, faiz tutarını ve vergi iadesini artırmak ve azaltmak için parametre kurcalamayı kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısının TDS ayrıntılarını indirip indiremeyeceğini kontrol edin
    - [ ] 'A' kullanıcısının 'B' kullanıcısı adına çek karnesi talep edip edemeyeceğini kontrol edin.
    - Sabit Mevduat Hesabı Testi
        - [ ] 'A' kullanıcısının 'B' kullanıcısı adına FD hesabı açmasının mümkün olup olmadığını kontrol edin
        - [ ] Kullanıcının mevcut hesap bakiyesinden daha fazla tutarda FD hesabı açıp açamayacağını kontrol edin
    - Çek/Tarih Aralığı Bazında Ödemenin Durdurulması
        - [ ] 'A' kullanıcısı 'B' kullanıcısının ödemesini çek numarası üzerinden durdurabilir mi?
        - [ ] Kullanıcı 'A', kullanıcı 'B' için tarih aralığı bazında ödemeyi durdurabilir mi?
    - Durum Sorgulama Testi
        - [ ] 'A' kullanıcısı 'B' kullanıcısının durum sorgusunu görüntüleyebilir mi?
        - [ ] 'A' kullanıcısı 'B' kullanıcısının durum sorgusunu değiştirebilir mi?
        - [ ] 'A' kullanıcısı kendi hesabından 'B' kullanıcısı adına gönderi ve sorgulama yapabilir mi?
    - Fon transferi testi
        - [ ] 'A' kullanıcısından 'B' kullanıcısına aktarılmak istenen fonun 'B' kullanıcısı yerine 'C' kullanıcısına aktarılması mümkün müdür?
        - [ ] Fon transfer miktarı manipüle edilebilir mi?
        - [ ] 'A' kullanıcısı 'B' kullanıcısının alacaklı listesini parametre ile değiştirebilir mi?
         Aynı ödüle sahip ürün sayısını artırmak için
    - Hediye/Kupon
        - [ ] Kullanılacak kupon/hediye sayısını artırmak/azaltmak için (varsa) talepteki hediye/kupon sayısını değiştirin
        - [ ] Kuponun değerini para cinsinden artırmak/azaltmak için hediye/kupon değerini değiştirin. (örn. 100 $ kupon olarak verilir, parayı artırmak veya azaltmak için değeri kurcalayın)
        - [ ] Parametre kurcalamada eski hediye değerlerini kullanarak hediyeyi/kuponu yeniden kullanın
        - [ ] Hediye/kupon parametresinin benzersizliğini kontrol edin ve diğer hediye/kupon kodunu tahmin etmeyi deneyin
        - [ ] BurpSuite isteğinde aynı parametre adını ve değerini & ile tekrar ekleyerek aynı kuponu iki kez eklemek için parametre kirliliği tekniğini kullanın
    - Sepetten Ürün Ekleme/Silme
        - [ ] Diğer kullanıcının sepetinden ürün silmek için kullanıcı kimliğini değiştir
        - [ ] Diğer kullanıcının sepetinden ürün eklemek/silmek için sepet kimliğini değiştir
        - [ ] Diğer kullanıcının hesabından eklenen öğeleri görüntülemek için sepet özelliği için sepet kimliği/kullanıcı kimliği tanımlayın
    - Adres
        - [ ] BurpSuite'in diğer kullanıcının gönderim adresini sizinkiyle değiştirme isteğini kurcalayın
        - [ ] Gönderi adresine XSS vektörü ekleyerek depolanmış XSS'yi deneyin
        - [ ] Aynı ürünü iki teslimat adresine göndermek için uygulamayı manipüle etmeye çalışmak yerine iki teslimat adresi eklemek için parametre kirliliği tekniğini kullanın
    - Sipariş Verin
        - [ ] Ödeme yöntemini değiştirmek için ödeme seçenekleri parametresini kurcalayın. Örneğin, bazı ürünlerin teslimatta nakit olarak sipariş edilemeyeceğini düşünün, ancak talep parametrelerini banka / kredi / PayPal / ağ bankacılığı seçeneğinden teslimatta nakit olarak değiştirmenize izin verebilir.
        söz konusu ürün için sipariş verin
        - [ ] Her bir ana ve alt talep ve yanıtta ödeme manipülasyonu için miktar değerini kurcalayın
        - [ ] CVV'nin açık metin olarak gidip gitmediğini kontrol edin
        - [ ] Uygulamanın kendisinin kart bilgilerinizi işleyip işlem yapıp yapmadığını veya işlem yapmak için herhangi bir üçüncü taraf ödeme işleme şirketini arayıp aramadığını kontrol edin
    - Parça Sırası
        - [ ] Sipariş takip numarasını tahmin ederek diğer kullanıcının siparişini takip edin
        - [ ] Diğer kullanıcıların toplu siparişlerini takip etmek için takip numarası ön ekini veya son ekini kaba kuvvetle zorlama
    - İstek listesi sayfası testi
        - [ ] Bir A kullanıcısının diğer B kullanıcısının hesabındaki İstek Listesine ürün ekleyip ekleyemeyeceğini kontrol edin
        - [ ] Bir A kullanıcısının kendi (A kullanıcısının) İstek Listesi bölümünden B kullanıcısının sepetine ürün ekleyip ekleyemeyeceğini kontrol edin.
    - Ürün satın alma sonrası testi
        - [ ] A kullanıcısının B kullanıcısının satın alma siparişlerini iptal edip edemeyeceğini kontrol edin
        - [ ] A kullanıcısının B kullanıcısı tarafından önceden verilmiş siparişleri görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] A kullanıcısının B kullanıcısı tarafından verilen siparişin sevkiyat adresini değiştirip değiştiremeyeceğini kontrol edin
    - Bant dışı test
        - [ ] Kullanıcı stokta olmayan ürünü sipariş edebilir mi?
- **Bankacılık Uygulama Testi**
    - Faturalama Faaliyeti
        - [ ] 'A' kullanıcısının 'B' kullanıcısının hesap özetini görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı için işlem raporunu görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı için özet raporu görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısı adına e-posta yoluyla aylık/haftalık hesap özeti için kayıt olup olamayacağını kontrol edin
        - [ ] Kullanıcı 'A'nın aylık/haftalık hesap özetini almak için kullanıcı 'B'nin mevcut e-posta kimliğini güncelleyip güncelleyemeyeceğini kontrol edin
    - Mevduat/Kredi/Bağlı/Harici Hesap Kontrolü
        - [ ] 'A' kullanıcısının 'B' kullanıcısının mevduat hesabı özetini görüntüleyip görüntüleyemeyeceğini kontrol edin
        - [ ] Mevduat hesapları için hesap bakiyesi tahrifatını kontrol edin
    - Vergi İndirimi Sorgulama Testi
        - [ ] 'A' kullanıcısının 'a' müşteri kimliği ile 'B' kullanıcısının 'b' müşteri kimliğini kurcalayarak vergi kesintisi ayrıntılarını görüp göremeyeceğini kontrol edin
        - [ ] Faiz oranını, faiz tutarını ve vergi iadesini artırmak ve azaltmak için parametre kurcalamayı kontrol edin
        - [ ] 'A' kullanıcısının 'B' kullanıcısının TDS ayrıntılarını indirip indiremeyeceğini kontrol edin
    - [ ] 'A' kullanıcısının 'B' kullanıcısı adına çek karnesi talep edip edemeyeceğini kontrol edin.
    - Sabit Mevduat Hesabı Testi
        - [ ] 'A' kullanıcısının 'B' kullanıcısı adına FD hesabı açmasının mümkün olup olmadığını kontrol edin
        - [ ] Kullanıcının mevcut hesap bakiyesinden daha fazla tutarda FD hesabı açıp açamayacağını kontrol edin
    - Çek/Tarih Aralığı Bazında Ödemenin Durdurulması
        - [ ] 'A' kullanıcısı 'B' kullanıcısının ödemesini çek numarası üzerinden durdurabilir mi?
        - [ ] Kullanıcı 'A', kullanıcı 'B' için tarih aralığı bazında ödemeyi durdurabilir mi?
    - Durum Sorgulama Testi
        - [ ] 'A' kullanıcısı 'B' kullanıcısının durum sorgusunu görüntüleyebilir mi?
        - [ ] 'A' kullanıcısı 'B' kullanıcısının durum sorgusunu değiştirebilir mi?
        - [ ] 'A' kullanıcısı kendi hesabından 'B' kullanıcısı adına gönderi ve sorgulama yapabilir mi?
    - Fon transferi testi
        - [ ] 'A' kullanıcısından 'B' kullanıcısına aktarılmak istenen fonun 'B' kullanıcısı yerine 'C' kullanıcısına aktarılması mümkün müdür?
        - [ ] Fon transfer miktarı manipüle edilebilir mi?
        - [ ] 'A' kullanıcısı 'B' kullanıcısının alacaklı listesini parametre ile değiştirebilir mi?
        /onload='+/"/+/onmouseover=1/+/[*/[]/+alert(1)//'>
     - XSS Güvenlik Duvarını Atlatma
         - [ ] Güvenlik duvarının yalnızca küçük harfleri engelleyip engellemediğini kontrol edin
         - [ ] Yeni satırla güvenlik duvarı normal ifadesini kırmayı deneyin(\r\n)
         - [ ] Çift Kodlamayı Deneyin
         - [ ] Özyinelemeli filtrelerin test edilmesi
         - [ ] Bağlantı etiketini boşluk olmadan ekleme
         - [ ] Kurşun kullanarak boşlukları atlamayı deneyin
         - [ ] İstek yöntemini değiştirmeyi deneyin
- **CSRF Testi**
     - Uygulamada Anti-CSRF belirteci uygulandı
         - [ ] Anti-CSRF Simgesini Kaldırma
         - [ ] Anti-CSRF Jetonun Değiştirilmesi
         - [ ] Saldırganın Anti-CSRF Tokenını Kullanmak
         - [ ] Anti-CSRF Jetonu Sahtekarlığı
         - [ ] Tahmin edilebilir Anti-CSRF Tokenlarının kullanılması
         - [ ] Anti-CSRF Tokenlarını Çalmak
     - Uygulama Çift Gönderim Çerezini kullanır
         - [ ] Alt alan adlarında oturum sabitlemesini kontrol edin
         - [ ] Ortadaki adam saldırısı
     - Başvuru, Yönlendireni veya alınan talebin Kaynağını doğrular
         - [ ] CSRF POC'nin Yönlendiren başlığını göndermesini kısıtlama
         - [ ] Uygulamanın kullandığı beyaz listeye alma/kara listeye alma mekanizmasını atlayın
     - JSON/XML formatında veri gönderme
         - [ ] Normal HTML Form1'i kullanarak
         - [ ] Normal HTML Form2 kullanarak (Getirme İsteğine Göre)
         - [ ] XMLHTTP İsteği/AJAX isteğini kullanarak
         - [ ] Flash dosyasını kullanarak
     - Samesite Cookie özelliği
         - [ ] Yöntem geçersiz kılma aracılığıyla SameSite Lax'i atlama
         - [ ] SameSite İstemci tarafı yönlendirme yoluyla katı geçiş
         - [ ] SameSite Kardeş etki alanı aracılığıyla katı geçiş
         - [ ] Çerez yenileme yoluyla SameSite Lax'i atlama
- **TOA Güvenlik Açıkları**
     - [ ] Internal.company.com Sizi SSO'ya Yönlendiriyorsa; auth.company.com, FUZZ yapın
     Internal.company.com'da
     - [ ] Company.com/internal Sizi SSO'ya Yönlendirirse ör. Google girişi yapın, Eklemeyi Deneyin
     public Dahiliden önce ör. Company.com/public/internal Dahili Erişim Kazanmak İçin
     - [ ] Token ile SAML İsteği Oluşturup Sunucuya Göndermeyi Deneyin ve Şekil
     Sunucunun Bununla Nasıl Etkileşime Girdiği
     - [ ] Token İsteğinde AssertionConsumerServiceURL Varsa
     Alan adı ör. http://me.com Tokenı Çalmak İçin Değer Olarak
     - [ ] Token İsteğinde AssertionConsumerServiceURL Varsa FUZZ Yapmayı Deneyin
     Menşee Benzer Değilse, AssertionConsumerServiceURL'nin Değeri Üzerine
     - [ ] Herhangi bir UUID Varsa, Bunu Kurban Saldırganın UUID'sine Değiştirmeyi Deneyin; E-postası
     Dahili Çalışan veya Yönetici Hesabı vb.
     - [ ] Sunucunun XML İmza Sarmalamaya Karşı Savunmasız Olup Olmadığını Öğrenmeye Çalışın?
     - [ ] Sunucunun İmzalayanın Kimliğini Kontrol Edip Kontrol Etmediğini Öğrenmeye Çalışın?
     - [ ] SAML Yanıtının En Üstüne XXE Verilerini Eklemeyi Deneyin
     - [ ] Çocukken XSLT Verilerini Transforms Öğesine Enjekte Etmeyi Deneyin
     SAML Yanıtının Düğümü
     - [ ] Mağdur, Hizmet Veren Aynı Kimlik Sağlayıcı Tarafından Verilen Tokenları Kabul Edebiliyorsa
     Saldırgan, Böylece Mağdur Hesabını Ele Geçirebilirsiniz
     - [ ] SSO'yu Test Ederken Burp Suite'te Çerez Başlığındaki URL'ler Hakkında Arama Yapmayı Deneyin;
     Ana Bilgisayar=IP; SSRF Almak İçin IP'nizi IP'nize Değiştirmeye Çalışıyorsanız
- **XML Enjeksiyon Testi**
     - [ ] İçerik türünü text/xml olarak değiştirin ve aşağıdaki kodu ekleyin. Tekrarlayıcı aracılığıyla kontrol edin
    
     ```
        <?xml version = "1.0" encoding = "ISO 8859 1"?>
        <!DOCTYPE tushar [
        <!ELEMENT tushar HERHANGİ BİR
        <!ENTITY xxe SİSTEM "file:///etc/passwd" >]><tushar>&xxe;</
        <!ENTITY xxe SİSTEM "file:///etc/hosts" >]><tushar>&xxe;</
        <!ENTITY xxe SİSTEM "file:///proc/self/cmdline" >]><tushar>&xxe;</
        <!ENTITY xxe SİSTEM "file:///proc/version" >]><tushar>&xxe;</
     ```
    
     - [ ] Bant dışı etkileşimli kör XXE
- **Çapraz kaynak paylaşımı (CORS)**
     - [ ] Origin başlıklarını ayrıştırmada hatalar
     - [ ] Beyaz listeye alınmış boş kaynak değeri
- **Sunucu tarafı istek sahteciliği (SSRF)**
     - Ortak enjeksiyon parametreleri
        ```
        "access=", 
        "admin=", 
        "dbg=", 
        "debug=", 
        "edit=", 
        "grant=", 
        "test=", 
        "alter=", 
        "clone=", 
        "create=", 
        "delete=", 
        "disable=", 
        "enable=", 
        "exec=", 
        "execute=", 
        "load=", 
        "make=", 
        "modify=", 
        "rename=", 
        "reset=", 
        "shell=", 
        "toggle=", 
        "adm=", 
        "root=", 
        "cfg=",
        "dest=", 
        "redirect=", 
        "uri=", 
        "path=", 
        "continue=", 
        "url=", 
        "window=", 
        "next=", 
        "data=", 
        "reference=", 
        "site=", 
        "html=", 
        "val=", 
        "validate=", 
        "domain=", 
        "callback=", 
        "return=", 
        "page=", 
        "feed=", 
        "host=", 
        "port=", 
        "to=", 
        "out=",
        "view=", 
        "dir=", 
        "show=", 
        "navigation=", 
        "open=",
        "file=",
        "document=",
        "folder=",
        "pg=",
        "php_path=",
        "style=",
        "doc=",
        "img=",
        "filename="
         ```
        
     - [ ] Temel localhost veri yüklerini deneyin
     - Filtreleri atlamak
         - [ ] HTTPS kullanarak atla
         - [ ] [::] ile atla
         - [ ] Etki alanı yönlendirmesiyle atlama
         - [ ] Ondalık IP konumu kullanarak atlama
         - [ ] IPv6/IPv4 Adres Yerleştirmeyi kullanarak atlama
         - [ ] Hatalı biçimlendirilmiş URL'leri kullanarak atlama
         - [ ] Nadir adres kullanarak atlama (sıfırları bırakarak kısa IP adresleri)
         - [ ] Ekteki alfanümerikleri kullanarak atlama
     - Bulut Örnekleri
         - AWS
            
             ```
             http://instance-data
             http://169.254.169.254
             http://169.254.169.254/en son/kullanıcı verileri
             http://169.254.169.254/latest/user-data/iam/security-credentials/[ROL ADI]
             http://169.254.169.254/latest/meta-data/
             http://169.254.169.254/latest/meta-data/iam/security-credentials/[ROL ADI]
             http://169.254.169.254/latest/meta-data/iam/security-credentials/PhotonInstance
             http://169.254.169.254/latest/meta-data/ami-id
             http://169.254.169.254/latest/meta-data/reservation-id
             http://169.254.169.254/latest/meta-data/ana bilgisayar adı
             http://169.254.169.254/latest/meta-data/public-keys/
             http://169.254.169.254/latest/meta-data/public-keys/0/openssh-key
             http://169.254.169.254/latest/meta-data/public-keys/[ID]/openssh-key
             http://169.254.169.254/latest/meta-data/iam/security-credentials/dummy
             http://169.254.169.254/latest/meta-data/iam/security-credentials/s3access
             http://169.254.169.254/latest/dynamic/instance-identity/document
             ```
            
         - Google Bulut
            
             ```
             http://169.254.169.254/computeMetadata/v1/
             http://metadata.google.internal/computeMetadata/v1/
             http://metadata/computeMetadata/v1/
             http://metadata.google.internal/computeMetadata/v1/instance/hostname
             http://metadata.google.internal/computeMetadata/v1/instance/id
             http://metadata.google.internal/computeMetadata/v1/project/project-id
             ```
            
         - Dijital Okyanus

             ```
             curl http://169.254.169.254/metadata/v1/id
             http://169.254.169.254/metadata/v1.json
             http://169.254.169.254/metadata/v1/
             http://169.254.169.254/metadata/v1/id
             http://169.254.169.254/metadata/v1/user-data
             http://169.254.169.254/metadata/v1/anasistem adı
             http://169.254.169.254/metadata/v1/region
             http://169.254.169.254/metadata/v1/interfaces/public/0/ipv6/address
             ```
            
         - Azure
            
             ```
             http://169.254.169.254/metadata/v1/maintenance
             http://169.254.169.254/metadata/instance?api-version=2017-04-02
             http://169.254.169.254/metadata/instance/network/interface/0/ipv4/ipAddress/0/publicIpAddress?api-version=2017-04-02&format=text
             ```
            
     - [ ] Açık yönlendirme yoluyla atlama
- **Dosya Yükleme Testi**
     - [ ] kötü amaçlı dosyayı arşiv yükleme işlevine yükleyin ve uygulamanın nasıl yanıt verdiğini gözlemleyin
     - [ ] bir dosyayı yükleyin ve mevcut bir sistem dosyasının üzerine yazmak için yolunu değiştirin
     - [ ] Büyük Dosyada Hizmet Reddi
     - [ ] Meta Veri Sızıntısı
     - [ ] ImageMagick Kütüphanesi Saldırıları
     - [ ] Piksel Sel Saldırısı
     - Baypaslar
         - [ ] Boş Bayt (%00) Baypas
         - [ ] İçerik Türü Atlaması
         - [ ] Sihirli Bayt Atlaması
         - [ ] İstemci Tarafı Doğrulama Atlaması
         - [ ] Kara Listeye Alınmış Uzantı Atlaması
         - [ ] Homografik Karakter Atlaması
- **CAPTCHA Testi**
     - [ ] Captcha Alanı Bütünlük Kontrolleri Eksik
     - [ ] HTTP Fiil İşleme
     - [ ] İçerik Türü Dönüşümü
     - [ ] Yeniden Kullanılabilir Captcha
     - [ ] Captcha'nın aşağıdaki gibi mutlak yolla alınıp alınamayacağını kontrol edin
     [www.tushar.com/internal/captcha/images/24.png](http://www.chintan.com/internal/captcha/images/24.png)
     - [ ] CAPTCHA için sunucu tarafı doğrulamasını kontrol edin. Firebug eklentisini kullanarak GUI'den captcha bloğunu kaldırın ve isteği sunucuya gönderin
     - [ ] Görüntü tanımanın OCR aracıyla yapılıp yapılamayacağını kontrol edin.
- **JWT Token Testi**
     - [ ] Kaba kuvvet kullanan gizli anahtarlar
     - [ ] “Yok” algoritmasıyla yeni bir token imzalamak
     - [ ] Belirtecin imzalama algoritmasının değiştirilmesi (bulanıklaştırma amacıyla)
     - [ ] Asimetrik olarak imzalanmış jetonun simetrik algoritma eşleşmesine göre imzalanması (orijinal genel anahtara sahip olduğunuzda)
- **Websockets Testi**
     - [ ] WebSocket mesajlarını yakalama ve değiştirme
     - [ ] Websockets MITM girişimleri
     - [ ] Gizli başlık websocket'i test ediliyor
     - [ ] Websocket'lerde içerik çalınması
     - [ ] Websocket'lerde belirteç kimlik doğrulama testi
- **GraphQL Vgüvenlik açıkları Testi**
     - [ ] Tutarsız Yetki Kontrolleri
     - [ ] Özel Skalerlerin Doğrulanması Eksik
     - [ ] Hız Limitinin Uygun Şekilde Uygulanmaması
     - [ ] İç Gözlem Sorgusu Etkin/Devre Dışı
- **WordPress'teki Yaygın Güvenlik Açıkları**
     - [ ] WordPress'te XSPA
     - [ ] wp-login.php dosyasında Bruteforce
     - [ ] Bilgi ifşa wordpress kullanıcı adı
     - [ ] Yedekleme dosyası wp-config açığa çıktı
     - [ ] Günlük dosyaları açığa çıktı
     - [ ] load-styles.php aracılığıyla Hizmet Reddi
     - [ ] load-scripts.php aracılığıyla Hizmet Reddi
     - [ ] xmlrpc.php kullanarak DDOS
     - [ ] CVE-2018-6389
     - [ ] CVE-2021-24364
     - [ ] WP-Cronjob DOS
- **XPath Enjeksiyonu**
     - [ ] Kimlik doğrulamayı atlamak için XPath enjeksiyonu
     - [ ] Verileri sızdırmak için XPath enjeksiyonu
     - [ ] Verileri dışarı çıkarmak için Kör ve Zamana Dayalı XPath enjeksiyonları
- **LDAP Enjeksiyonu**
     - [ ] Kimlik doğrulamayı atlamak için LDAP enjeksiyonu
     - [ ] Verileri dışarı çıkarmak için LDAP enjeksiyonu
- **Hizmet Reddi**
     - [ ] Kurabiye bombası
     - [ ] Piksel seli, büyük piksellere sahip görüntü kullanılarak
     - [ ] Çerçeve seli, büyük çerçeveli GIF kullanımı
     - [ ] ReDoS (Regex DoS)
     - [ ] CPDoS (Önbellek Zehirli Hizmet Reddi)
- **403 Baypas**
     - [ ] "X-Original-URL" başlığını kullanma
     - [ ] İlk eğik çizgiden sonra **%2e** ekleniyor
     - [ ] URL'ye nokta (.), eğik çizgi (/) ve noktalı virgül (;) eklemeyi deneyin
     - [ ] Dizin adından sonra "..;/" ekleyin
     - [ ] URL'deki alfabeyi büyük harfle yazmayı deneyin
     - [ ] Araç-**[bypass-403](https://github.com/daffainfo/bypass-403)**
     - [ ] Burp Uzantısı-[403 Bypasser](https://portswigger.net/bappstore/444407b96d9c4de0adb7aed89e826122)
- **Diğer Test Durumları (Tüm Kategoriler)**
     - Rol yetkilendirmesi için test
         - [ ] Normal kullanıcının yüksek ayrıcalıklı kullanıcıların kaynaklarına erişip erişemediğini kontrol edin.
         - [ ] Zorunlu tarama
         - [ ] Güvenli olmayan doğrudan nesne referansı
         - [ ] Kullanıcı hesabını yüksek ayrıcalıklı kullanıcıya geçirmek için parametre değişikliği
     - Güvenlik başlıklarını kontrol edin ve en azından
         - [ ] X Çerçeve Seçenekleri
         - [ ] X-XSS başlığı
         - [ ] HSTS başlığı
         - [ ] CSP başlığı
         - [ ] Yönlendiren Politikası
         - [ ] Önbellek Kontrolü
         - [ ] Genel anahtar pinleri
     - Kör işletim sistemi komut enjeksiyonu
         - [ ] zaman gecikmelerini kullanma
         - [ ] çıktıyı yeniden yönlendirerek
         - [ ] bant dışı etkileşimle
         - [ ] bant dışı veri sızıntısı ile
     - [ ] CSV dışa aktarımında komut ekleme (Yükleme/İndirme)
     - [ ] CSV Excel Makro Enjeksiyonu
     - [ ] Phpinfo.php dosyasını bulursanız, yapılandırma sızıntısını kontrol edin ve ağdaki güvenlik açığından yararlanmaya çalışın.
     - [ ] Parametre Kirliliği Sosyal Medya Paylaşım Butonları
     - Kırık Şifreleme
         - [ ] Kriptografi Uygulama Kusuru
         - [ ] Şifrelenmiş Bilgilerin Tehlikeye Atılması
         - [ ] Şifreleme için Kullanılan Zayıf Şifreler
     - Web Hizmetleri Testi
         - [ ] Dizin geçişini test edin
         - [ ] Web hizmetleri belgelerinin açıklanması Hizmetlerin, veri türlerinin, giriş türlerinin sınırlarının ve limitlerinin numaralandırılması
- **Burp Suite Uzantıları**
     - Tarayıcılar
         - [ ] https://github.com/albinowax/ActiveScanPlusPlus
         - [ ] https://github.com/portswigger/additional-scanner-checks
         - [ ] https://github.com/PortSwigger/backslash-powered-scanner
     - Bilgi toplama
         - [ ] https://github.com/capt-meelo/filter-options-method
         - [ ] https://github.com/moeinfatehi/Admin-Panel_Finder
         - [ ] https://github.com/raise-isayan/BigIPDiscover
         - [ ] https://github.com/P3GLEG/PwnBack
     - Güvenlik Açığı Analizi
         -[ ] https://github.com/matrix/Burp-NoSQLiScanner


kaynak: https://alike-lantern-72d.notion.site/Web-Application-Penetration-Testing-Checklist-4792d95add7d4ffd85dd50a5f50659c6