# Finansal Hesaplama Araçları

Bu repo, yaygın finansal senaryolar için basit komut satırı araçları içerir. Bu scriptler, kredi ve taksitli alışverişlerinizdeki gerçek maliyetleri ve fırsat maliyetlerini anlamanıza yardımcı olmak için tasarlanmıştır.

## Araçlar

### 1. Efektif Faiz Hesaplayıcı (`efektif_faiz_hesapla.py`)

Bir kredinin veya taksitli bir ürünün gerçek maliyetini anlamak için kullanılır. Çekilen ana para, taksit sayısı ve aylık ödeme miktarını girdiğinizde, kredinin **gerçek efektif aylık ve yıllık faiz oranını** sayısal analiz yöntemleriyle hesaplar. 

Bu araç, özellikle dosya masrafı, sigorta gibi ek maliyetlerin dahil edildiği toplam geri ödeme tutarı üzerinden net bir hesaplama yapmanızı sağlar. Böylece "düşük faizli" gibi görünen tekliflerin arkasındaki tüm gizli maliyetleri ortaya çıkarabilirsiniz.

#### Kullanım
Terminal veya komut istemcisinde aşağıdaki komutu çalıştırın:
```bash
python efektif_faiz_hesapla.py --ana-para <TUTAR> --taksit-sayisi <AY> --aylik-odeme <TUTAR>
```

#### Örnek
100.000 TL krediyi, 12 ay taksitle, aylık 9.500 TL ödeyerek geri ödediğinizde efektif faizi hesaplamak için:
```bash
python efektif_faiz_hesapla.py --ana-para 100000 --taksit-sayisi 12 --aylik-odeme 9500
```

### 2. Taksitli Alışverişin Bugünkü Değeri (`taksit_bugunku_deger_hesapla.py`)

Taksitli bir satın almanın, bugünün parasıyla gerçekte ne kadara mal olduğunu hesaplar. Alternatif yatırım fırsatlarını (örneğin aylık mevduat faizi) veya enflasyonu "fırsat maliyeti" olarak kullanarak, taksitli tekliflerin ne kadar mantıklı olduğunu analiz etmenizi sağlar.

#### Kullanım
Terminal veya komut istemcisinde aşağıdaki komutu çalıştırın:
```bash
python taksit_bugunku_deger_hesapla.py --toplam-odeme <TUTAR> --taksit-sayisi <AY> --aylik-faiz <YÜZDE>
```

#### Örnek
Toplamda 15.000 TL'ye 6 taksitle alacağınız bir ürünün, aylık %2.5 faiz/enflasyon oranı varsayımıyla bugünkü peşin değerini hesaplamak için:
```bash
python taksit_bugunku_deger_hesapla.py --toplam-odeme 15000 --taksit-sayisi 6 --aylik-faiz 2.5
```
