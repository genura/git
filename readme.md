

# Genel Notlar
## .gitignore kullanimi

1. ornek dosyayi yoksayar (ignore)
2. ornek klasor ve altindaki herseyi yoksayar (ignore)

```bash
# Belirli bir dosyayı yoksay
debug/logs.txt
```

```bash
# Belirli bir klasor ve altindaki herseyi yoksay
debug/
```


Evet, **.gitignore** dosyasını **sonradan eklediğinizde**, Git'in mevcut izlenen dosyaları yoksayması için bazı ek adımlar gerçekleştirmeniz gerekir:

**.gitignore** dosyasını projenizdeki uygun konuma ekleyin.
Daha önce izlenen ancak artık yoksaymak istediğiniz dosyaları "untrack" etmek için şu komutu kullanın:

```bash
git rm --cached -r .
```

Bu komut, deponuzdaki tüm dosyaları "untrack" eder. Ardından:
```bash
git add .
```

Komutuyla, **.gitignore** dosyasında belirtilen kurallar dışındaki dosyaları tekrar izlemeye alırsınız.

Son olarak, değişiklikleri commit edin:
```bash
git commit -m "Apply .gitignore rules"
```

Daha sonra, .gitignore dosyasına göre artık yoksayılan dosyaları deponuzdan tamamen kaldırmak için şu komutu kullanabilirsiniz:
```bash
git clean -Xf
```

Bu adımları izlediğinizde, .gitignore dosyasındaki kurallar tam olarak uygulanacak ve istediğiniz dosyalar Git tarafından artık yoksayılacaktır.


