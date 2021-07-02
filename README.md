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

1. `repository`:<span style="color:blue"> Kısa ismi ile repo. Kodlarınızın saklandığı depodur. </span>
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
