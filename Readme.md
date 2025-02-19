# Git Versiyon Kontrol Sistemi (VCS)

Çalışma Klasörü  `` git add `` ->  Index - Staging  ``git commit`` -> Local Repository

``git status`` -> gitin güncel durumunu gösterir.

``git init`` -> git ile ilgili herşeyi başlatır.

``rm -rf .git`` -> .git dosyasını siler.

``touch ilkdefter.txt`` -> ilkdefter.txt adında bir file oluşturur.

``git add`` -> Git'te belirli dosyaları veya değişiklikleri staging area (hazırlık alanı) denilen bölüme eklemek için kullanılan bir komuttur.

``git add .`` -> tüm değişiklikleri ekler.

``git commit -m "mesaj"`` -> staging area'ya (git add ile eklenen değişiklikler) alınan dosyaları kalıcı olarak bir anlık görüntü (snapshot) şeklinde Git deposuna kaydeden bir komuttur.

``git log`` -> Git deposundaki tüm commit geçmişini görüntülemek için kullanılan bir komuttur. Yapılan commit’leri, yazarlarını, tarihlerini ve commit hash’lerini gösterir.

# .gitignore

.gitignore, Git deposuna eklenmesini istemediğin dosya ve klasörleri belirttiğin bir dosyadır. Genellikle proje içinde gereksiz, geçici veya hassas verileri içeren dosyaları hariç tutmak için kullanılır.

*.log ->	Tüm .log uzantılı dosyaları hariç tutar.

/cache/ ->	Sadece proje kök dizinindeki cache klasörünü hariç tutar.

debug/*.txt ->	Sadece debug klasöründeki .txt dosyalarını hariç tutar.

!important.txt ->	.gitignore tarafından hariç tutulan dosyalarda bile istisna olarak eklenmesini sağlar.

# Git Branch & Merge

``HEAD`` -> son commiti gösterir. 

``git branch`` -> tüm branchleri gösterir.

``git branch feature`` -> feature adında branch oluşturur.

``git switch master`` -> master branchına geri döner.

``git switch master`` -> feature branchına geçer.

``git merge feature`` -> iki branchi birbirine birleştirir. feature branchini master ile birleştirdi.

``Fast-Forward`` -> Git'te fast-forward (hızlı ileri sarma), bir dalın (branch) başka bir dala birleştirilmesi (merge) sırasında, hedef dalın doğrudan ileri alınarak yeni değişiklikleri içerecek şekilde güncellenmesi anlamına gelir.

# Merge Conflict

Merge conflict (birleştirme çatışması), Git’in iki farklı branch’i birleştirirken hangi değişikliğin kullanılacağını bilemediği durumlarda ortaya çıkar.

# Stash

``git stash`` -> çalışmalarını geçici olarak saklamanı ve temiz bir çalışma alanına dönmeni sağlayan bir Git komutudur.
Ne İşe Yarar?
-Çalışmalarını commit etmeden geçici olarak kaydetmek
-Başka bir branch’e geçmen gerektiğinde değişiklikleri kaybetmeden stash’e almak
-Merge yaparken ya da güncelleme alırken çakışma yaşamamak için değişiklikleri gizlemek

``git stash pop`` -> Bu komut, en son eklenen stash’i geri yükler ancak stash’ten silmez.

``git stash list`` -> Kaydedilen stash’leri görmek için

``git stash apply stash@{0}`` -> Bu komut, stash’i uygular ve otomatik olarak stash listesinden siler.

``git stash clear`` -> Tüm stash’leri temizlemek için

# Geçmişe Dönme

``git restore`` -> Çalışma alanındaki değişiklikleri geri almak için kullanılır.

``git checkout`` -> Başka bir branch’e veya commit’e geçmek için kullanılır.

``git reset`` -> Commit geçmişini değiştirmek veya geri almak için kullanılır.

``git revert`` -> , Git'te bir veya daha fazla commit'i geri almak için kullanılan bir komuttur. Bu komut, belirtilen commit'lerde yapılan değişiklikleri tersine çevirerek yeni bir commit oluşturur. Bu, mevcut commit geçmişini değiştirmeden, yanlış veya istenmeyen değişiklikleri geri almanın güvenli bir yoludur.

``git diff`` -> Git'te değişiklikleri incelemek için kullanılan bir komuttur. Bu komut, çalışma dizinindeki değişiklikleri, staging alanındaki (indeks) değişiklikleri veya commit'ler arasındaki farkları gösterir.

# Rebase 

``git rebase`` -> bir branch'teki commit'leri alıp başka bir branch'in en son commit'inden itibaren yeniden oluşturur. Bu işlem, iki branch'i birleştirmenin alternatif bir yoludur ve git merge'den farklı olarak commit geçmişini daha temiz ve doğrusal hale getirir.

# Git Push & Pull 

```git push`` -> Ne işe yar? git push, yerel deponuzdaki değişiklikleri uzak depoya gönderir.

Nasıl çalışır? Yerel deponuzdaki commit'leri ve dalları uzak depoya yükler. Bu, diğer geliştiricilerin sizin yaptığınız değişiklikleri görmesini sağlar.

Ne zaman kullanılır? Yerel deponuzda yaptığınız değişiklikleri uzak depoya yüklemek istediğinizde kullanılır.
```` git push origin main ````

``git pull`` -> Ne işe yar? git pull, uzak depodaki değişiklikleri indirir ve bu değişiklikleri yerel çalışma alanınıza otomatik olarak entegre eder.

Nasıl çalışır? git pull aslında iki işlemi birleştirir: git fetch ve git merge. Önce uzak depodaki değişiklikleri indirir (fetch), ardından bu değişiklikleri yerel dalınıza birleştirir (merge).

Ne zaman kullanılır? Uzak depodaki değişiklikleri yerel çalışma alanınıza hemen uygulamak istediğinizde kullanılır.

```` git pull origin main ````


``git fetch`` -> Ne işe yarar? git fetch, uzak depodaki değişiklikleri yerel deponuza indirir, ancak bu değişiklikleri yerel çalışma alanınıza (working directory) uygulamaz.

Nasıl çalışır? Uzak depodaki tüm yeni commit'leri, dalları (branches) ve etiketleri (tags) yerel deponuza getirir, ancak bu değişiklikleri henüz yerel dallarınıza entegre etmez.

Ne zaman kullanılır? Uzak depodaki değişiklikleri görmek istediğinizde, ancak bu değişiklikleri henüz yerel çalışma alanınıza uygulamak istemediğinizde kullanılır.

```` git fetch origin ````