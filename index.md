# Master1
Burada bir aciklama gerçekleşmektedir...

## BU YENİ BİR BAŞLIK
Burada bir paragraf vardır...
Burada bir paragraf vardır...
Burada bir paragraf vardır...
Burada bir paragraf vardır...
--------------------------------
# [Patika.dev](https://www.patika.dev/tr) İleri Seviye GIT Kursu

## Kurs Notları

Eğer son commitin içeriğini değiştirmek istersek,

```shell
git add . // son değişiklikleri versiyonlanmak üzere ekledik
git commit --amend // ile değişiklikleri commit ettik
```

Eğer son commitin mesajını değiştirmek istersek,

```shell
git commit --amend -m "Yeni mesaj" // ile yeni commit mesajını verdik
```

Sondan x adet commiti loglamak istersek,

```shell
git log -n x // x burada bir sayı olmalı
```

Yapılan bir commiti geri almak istersek,

```shell
git revert commitID // geri almak istediğimiz commitin IDsini verdik

// revert ile commiti geri alırken bizden yeni bir commit içeriği girmemizi ister
```

Commitleri geri almak istiyoruz fakat yeni bir commit oluşmasını istemiyorsak,

```shell
git reset --hard commitID // buradaki commitID hangi commite geri dönmek istiyorsak o commitin IDsi olmalı,
// ve o commite kadar olan aradaki bütün commitleri siler
```

Eğer commitler arasındaki farkları görmek istersek,

```shell
git diff eskiCommitID..yeniCommitID dosyaAdi

// eskiCommitID..yeniCommitID burada iki commitin IDlerini verdik

// dosyaAdi parametresi opsiyoneldir eğer bu parametreyi vermeseydik bütün dosyaları karşılaştıracaktı
```

Eğer branchleri listelemek istersek

```shell
git branch // çıktı olarak branch isimlerini verir, aktif olan branchin yanında * işareti yer alır
```

Eğer yeni bir branch oluşturmak istersek

```shell
git branch branch_ismi // branch_ismi adında yeni bir branch oluşturur

// alternatif olarak

git checkout -b branch_ismi // aktif branchi referans alarak yine branch_ismi adında yeni bir branch oluşur,
// ve aktif branchi bu branch yapar
```

Eğer bir branchi silmek istersek

```shell
git branch -D branch_ismi // branch_ismi adındaki branchi siler
```

Eğer yaptığımız değişiklikleri geçici olarak saklamak istersek

```shell
git stash // yaptığımız değişiklikleri saklar son commite döner

git stash list // saklanan değişikliklerin listesini gösterir

git stash clear // saklanan değişiklikleri temizler

git stash pop // saklanan değişiklikleri geri getirir ve saklama listesin temizler

git stash apply stash_id // stash listesindeki stash_id IDsine sahip değişiklikleri getirir,
// poptan farkı; apply listyeyi temizlemez
```

Eğer branchleri birleştirmek istersek,

```shell
git merge branch_ismi // aktif branch ile branch_ismi branchini birleştirir ve commitleri aktarır

git merge --squash branch_ismi // aktif branch ile branch_ismi branchini birleştirir ama commitleri aktarmaz,
// merge işlemini commitlemeyi bize bırakır

git merge --abort // eğer merge sonrası conflict çıkarsa yapılan merge işlemini geri alır

// alternatif olarak

git rebase branch_ismi // aktif branch ile branch_ismi branchini birleştirir,
// mergeden farkı tüm historyi tek bir branch altında toplar, daha sade bir history sunar.
// bir ekiple çalışıyorsak merge işlemi ile branch birleştirmek daha önemlidir,
// çünkü revert etmek rebase işleminde daha bir zahmetli olacaktır
```
