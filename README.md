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
<li> untracked (izlenmeyen): GIT tarafından henüz takip edilmeyen, yani yeni oluşturulmuş dosyaları ifade eder. </li>
<li> unstaged (hazırlanmamış): Güncellenmiş ancak commit’lenmek için hazırlanmamış dosyaları ifade eder. </li>
<li> staged (hazırlanmış): Commit’lenmeye hazır olan dosyaları ifade eder. </li>
<li> deleted (silinmiş): Projeden silinmiş ama GIT üzerinden kaldırılmamış dosyaları ifade eder. </li>
 </ol>
 
 ---
 ## Başlıyoruz 
 <p> Yapacağımız ilk kongigürasyon ayarlarını yapılandırmak olacaktır , bu ayarlardan ikisi `user.name` ve `user.email` dir. bu ayarları yapılandırmak için </p>
 - git config --global user.name "Adınız soyadınız"
 - git config --global user.email "email@adresiniz"
 <p>Bu ayarlar global yani sistem genelinde kullanılan ve aktif olan ayarlardır .</p>
  Bu ayarların bütününü görmek için ise `git congif --list` kullanabilirsiniz 

 ### git init
 Henüz versiyon kontrolü altında olmayan bir proje dizininde , boş bir git deposu oluşturmak için kullanılır.
 1. İlk başta dosya dizinimize boş bir klasör ekleyiyoruz.
 2. ![mkdir](https://user-images.githubusercontent.com/74687192/124282222-44ebba80-db53-11eb-820a-0371fdcb5176.PNG)
 3. Ardından yapacağımız ilk iş kendi local bilgisayarımızda repoyu oluşturmak
 4. ![gitinit](https://user-images.githubusercontent.com/74687192/124282219-44532400-db53-11eb-84da-46abc94229cb.PNG)

### git clone
Olan bir repositoryi clone edip local repomuzla bağlamak için kullanacağımız git komutudur

- ![gitClone](https://user-images.githubusercontent.com/74687192/124291119-e4fa1180-db5c-11eb-932a-a687a5f0ed70.PNG)

### git remote
Uzaktaki repoya yani bizim için şuanda oluşturduğumuz Git-Versiyon-Kontrol-Sistemi

- ![git remote ](https://user-images.githubusercontent.com/74687192/124291112-e3304e00-db5c-11eb-9852-0ce7e9ce384f.PNG)

### git status
senin git versiyonundaki statün ne , bu dosya geçişte mi çalışma halinde mi bakmaya yarıyor 
- ![gitStatus](https://user-images.githubusercontent.com/74687192/124291009-c431bc00-db5c-11eb-9d03-ea0a6d54cb4d.PNG)

### git add .
Komutu ile staging areaya gönderiyoruz
- ![gitaddsonrasi](https://user-images.githubusercontent.com/74687192/124291006-c3992580-db5c-11eb-8ef6-ff002835563f.PNG)

### git commit -m 'herhangi bir commit'

Burada local areaya göndermiş oluyoruz. Dosyaları işledim burada da ne yaptığımı hatırlamak için sisteme not ekliyorum.

### git push
Projemizde aldığımız commit'leri, remote repository'e gönderir.

- ![gitPush](https://user-images.githubusercontent.com/74687192/124291855-b03a8a00-db5d-11eb-9ed4-c3907234598d.PNG)

### git pull
remote repositoryideki değişikleri local repoma çekmiş olurum
`örnek kullanım = Githubda readme dosyanızda değişiklik yaptınız . Bunu git ile pushlamaya çalışırsanız hata alırsınız ve uzak remoda değişiklikler oldu denir bu komutu kullanabilirsiniz`



### git log

Bütün Yaptığımız komitleri buradan gözlemleyebiliriz.
- ![GitLog](https://user-images.githubusercontent.com/74687192/124291594-63ef4a00-db5d-11eb-92a7-ed604a111dfe.PNG)

- `git log -p-2` => son 2 değişikliği gösterir
- `git log  --since=30 minutes` => 30 dakika içinde yaptığımız değişiklikleri gösterir

### git show 
En son yaptığımız komiti gösterir
- ![gitShow](https://user-images.githubusercontent.com/74687192/124291590-62be1d00-db5d-11eb-8b9b-c4dd9ca61ec0.PNG)

### ls -al
Bütün dosya adlarını görebilirsiniz

- ![LsAl](https://user-images.githubusercontent.com/74687192/124291852-afa1f380-db5d-11eb-94e8-7d2da65fe001.PNG)


### git branch frontend 
### git branch backend

frontend ve backend adında birer dal oluşturabilirsiniz

### git branch -a
Tüm dallanmaları görebiliyoruz buradan


### git checkout frontend 
frontend dalına geçebilirsiniz bu durumda

### git fetch

Remote branch'deki değişiklikleri indirmek için git fetch komutunu kullanıyoruz.

### git merge 

değişiklikleri otomatik merge et çakışma varsa bir sonraki adıma geçin demek oluyor 

`git pull = git fetch+git merch`

### git merge frontend backend
backend ve frontend dalını birleştirebilirsiniz

### git revert 
bu komut ile değişiklikleri 1 commitlik geri alabiliyoruz

### git reset --soft 
bu komut ile  commit bölgesinden alıyor staging area ve çalışma dizinimize dokunmuyor.

### git reset --mixed 
bu komut ile staging areadanda geri döndürdüm

### git reset --hard
bu komut ile her yer sıfırlanmış oldu.
