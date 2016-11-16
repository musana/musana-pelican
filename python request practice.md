Title: Python Request Kütüphanesini Kullanmak
Slug: python-request-lib-practice
Date: 2016-11-16
Author: Musa ŞANA
Tags: python, request,
Category: Python
Password: nothing.

Python dilinin tiyneti gereği request modülü de anlamabilirlik ve okunabilirlik açısından insana doğrudan hitap eden python ile yazılmış bir http kütüphanesidir. Hiç zorlanmadan ve sıkılmadan sadece onlarca satır kod ile çok büyük işleri halledebilirsiniz. 

Request modülünü pip ile kurmak için;

	pip3 install requests  

Kaynak koddan kurmak için ise;
```git
git clone git://github.com/kennethreitz/requests.git
```
indirdiğiniz dizine girip `python3 setup.py install` diyerek kurabilirsiniz.

Artık modülümüzü kullanmaya başlayabiliriz.

## İstek Yapmak

```#!/python
import request
req = requests.get("http://musana.net")
```

musana.net adresine get metoduyla bir istekte bulunduk ve artık elimizde `req` adında bir nesne mevcut. İstekte bulunduğumuz bağlantıya ait bütün bilgilere `req` nesnesi üzerinden erişebiliriz.

Diğer http metodları kullanarak request gönderelim.
 
	#!/python
	req = requests.get("http://musana.net", params={'par1':'value1', 'par2':'value2'}
	print(req.url) #Output: http://musana.net/?par1=value2
	req = requests.post("http://musana.net", data={'anahtar':'deger', 'anahtar2':'deger2'})
	# Yukarıdaki istek bize şöyle bir url verecektir: http://musana.net/?anahtar=deger&anahtar2=deger2
	req = reqeusts.head("http://musana.net")
	req = requests.delete("http://musana.net")
	req = requests.option("http://musana.net")
	req = requests.head("http://musana.net")


Yukarıda dikkat etmeniz gereken nokta post metodunda data parametresi kullanmış olmamızdır. Post ile göndereceğimiz verileri sözlükleri kullanarak göndereceğiz.
 
