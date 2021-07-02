# Git-Versiyon-Kontrol-Sistemi 

<img src="https://user-images.githubusercontent.com/74687192/124278728-4ca96000-db4f-11eb-9ea1-055f1c988449.png" width="100%" height="350px" title="hover text">
<p> GIT nedir? diye sorduğunuzda versiyon kontrol sistemi cevabını almışsınızdır. İyi de versiyon kontrol sistemi nedir?

Projemi geliştirirken "proje", "projee", "projee_son", "projee_son_5" şeklinde klasörlesem olmaz mı? GIT öğrenmeden olmaz mı? - OLMAZ!

Son sorudan başlayayım. Eğer profesyonel işler yapacaksanız GIT öğrenmek zorundasınız. Klasör isminin sonuna fazladan harfler, rakamlar ekleyerek proje geliştirmek ilerleyen süreçlerde başa çıkılabilecek bir yöntem değildir.

Versiyon Kontrol Sistemi Nedir? sorusuna gelirsek; Bir döküman (yazılım projesi, ofis belgesi vb.) üzerinde yaptığınız degişiklikleri adım adım izleyen, istediğinizde kayıt eden ve isterseniz bunu internet üzerindeki bir bilgisayarda veya yerel bir cihazda (respository / repo / depo) saklamanızı ve yönetmenizi sağlayan bir sistemdir.</p>

---
<p> GIT Bize Ne Sağlar?
Birden fazla yerde (dağıtık olarak) dosyalarınızı ve versiyon kontrol bilgilerinizi depolayabilirsiniz. Böylelikle cihaz bağımsız olarak dosyalarınıza erişebilirsiniz.
"commit" yaparak SnapShot (anlık görüntü) özelliği ile istediğiniz zaman proje veya dosyaların o anki halini kayıt altına alabilirsiniz. Böylelikle ileride bir hata ile karşılaşırsanız herhangi bir zamandaki herhangi bir versiyona dönüş yapabilirsiniz.
SnapShot alındıktan sonra değişiklik yapılan dosyaları görebilirsiniz.
Takımların aynı projede beraber çalışmasına imkan verir. Kim neyi düzenledi? Ne ekledi? Ne çıkarttı? Son değişiklik ne zaman yapıldı? gibi bilgilere erişebilirsiniz. Bu sayede topluluk ile proje geliştirme süreçlerini kolaylaştırabilirisiniz.
Projede verisyonlanmasını istemediğiniz dosyaları belirtebilirsiniz. (node_modules, .mp4, .log, .env gibi)</p>

## Başlamadan Önce

GIT sistemini kullanmaya başladığınızda karşınıza daha önce aşina olmadığınız bazı tanımlar çıkacaktır. Temel bazı terimleri kısaca açıklayarak içeriğimizi bitirelim.

1. `repository`:<span style="color:blue;"> Kısa ismi ile repo. Kodlarınızın saklandığı depodur. </span>
 2. `master`: Depodaki kararlı sürüme master denir.

 3. `branch`: GIT ağaç mantığı ile çalışır. Bir projeyi versiyonladığımızda master branch'i oluşur. Ana dosya (master) üzerinde değişklik yapmak hem tehlikelidir hem de çok kişi ile yapılan geliştirmelerde karışıklığa sebep olur. Kimin neyi değiştirdiğini takip etmek zorlaşır. Bu sebeple geliştiriciler master'den açılan dallar (branch) üzerinde geliştirmelerini yapar. Kullanıcılar branch (dallar) üzerinde yaptıkları geliştirmeleri master'a birleştirmesi için proje sahibine gönderirler.

4. `merge`: branch'larda yapılan değişikliklerin master branch'ı ile birleştirilmesidir.

5. `push`: Dosyaları repo'ya (depo) göndermek için kullanılır.

6. `pull`: Depodan dosyaları çekmek için kullanılır.

7. `.gitignore`: GIT'in takip etmesini istemediğimiz dosya ve klasörleri belirttiğimiz dökümandır. Mesela node_module klasörünün izlenmesine gerek yoktur ve .gitignore dökümanı içinde bunu belirtiriz.

---

![Github](https://user-images.githubusercontent.com/74687192/124280326-3ac8bc80-db51-11eb-9859-d7940534e4bf.PNG)

Başlıca bilmemiz gereken bazı terimler;
<ol>
<li>  untracked (izlenmeyen): GIT tarafından henüz takip edilmeyen, yani yeni oluşturulmuş dosyaları ifade eder. </li>
<li> unstaged (hazırlanmamış): Güncellenmiş ancak commit’lenmek için hazırlanmamış dosyaları ifade eder. </li>
 <li>  staged (hazırlanmış): Commit’lenmeye hazır olan dosyaları ifade eder. </li>
<li> deleted (silinmiş): Projeden silinmiş ama GIT üzerinden kaldırılmamış dosyaları ifade eder. </li>
 </ol>
 
 ---
 ## Başlıyoruz 
 <p> Yapacağımız ilk kongigürasyon ayarlarını yapılandırmak olacaktır , bu ayarlardan ikisi `user.name` ve `user.email` dir. bu ayarları yapılandırmak için </p>
 >git config --global user.name "Adınız soyadınız"
 >git config --global user.email "email@adresiniz"
 <p>Bu ayarlar global yani sistem genelinde kullanılan ve aktif olan ayarlardır .</p>
 >Bu ayarların bütününü görmek için ise `git congif --list` kullanabilirsiniz 

 ### git init
 Henüz versiyon kontrolü altında olmayan bir proje dizininde , boş bir git deposu oluşturmak için kullanılır.
 1. İlk başta dosya dizinimize boş bir klasör ekleyiyoruz.
 2. ![mkdir](https://user-images.githubusercontent.com/74687192/124282222-44ebba80-db53-11eb-820a-0371fdcb5176.PNG)
 3. Ardından yapacağımız ilk iş kendi local bilgisayarımızda repoyu oluşturmak
 4. ![gitinit](https://user-images.githubusercontent.com/74687192/124282219-44532400-db53-11eb-84da-46abc94229cb.PNG)

### git clone
Olan bir repositoryi clone edip local repomuzla bağlamak için kullanacağımız git komutudur

### git remote
Uzaktaki repoya yani bizim için şuanda oluşturduğumuz Git-Versiyon-Kontrol-Sistemi

### git status
senin git versiyonundaki statün ne , bu dosya geçişte mi çalışma halinde mi bakmaya yarıyor 

### git add .
Komutu ile staging areaya gönderiyoruz


### git commit -m 'herhangi bir commit'

Burada local areaya göndermiş oluyoruz. Dosyaları işledim burada da ne yaptığımı hatırlamak için sisteme not ekliyorum.

### git push
Projemizde aldığımız commit'leri, remote repository'e gönderir.

### git pull
remote repositoryideki değişikleri local repoma çekmiş olurum
`örnek kullanım = Githubda readme dosyanızda değişiklik yaptınız . Bunu git ile pushlamaya çalışırsanız hata alırsınız ve uzak remoda değişiklikler oldu denir bu komutu kullanabilirsiniz`

### git log

Bütün Yaptığımız komitleri buradan gözlemleyebiliriz.

### git show 

En son yaptığımız komiti gösterir

### ls -al
Bütün dosya adlarını görebilirsiniz

### git branch frontend 
### git branch backend

frontend adında bir dal oluşturabilirsiniz

### git branch -a
Tüm dallanmaları görebiliyoruz buradan


### git checkout frontend 
frontend dalına geçebilirsiniz bu durumda

### git merge frontend backend
backend ve frontend dalını birleştirebilirsiniz
