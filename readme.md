Mərhələ 1: Missiya Parametrləri

Sahələr:

    Missiyanın Kod Adı: Input komponenti. (Məsələn: "Proxima Odisseyası", "Andromeda Ümidi")

    Təyinat Nöqtəsi: Select komponenti - Seçimlər: "Mars (Qırmızı Səhra)", "Titan (Metan Dənizləri)", "Avropa (Buzaltı Okean)", "Kepler-186f (Yeni Dünya)", "TRAPPIST-1e (Sirli Planet)".

    Buraxılış Tarixi: Input type="date" komponenti.

    Missiyanın Növü: RadioGroup və Radio komponentləri - Seçimlər: "Kəşfiyyat", "Təchizat", "Məskunlaşma".

Validasiya Qaydaları:

    Missiyanın Kod Adı: Daxil edilməsi məcburidir. Hər böyük missiyanın bir adı olmalıdır! (minimum 3 simvol)

    Təyinat Nöqtəsi: Seçilməsi məcburidir. Hədəfsiz səyahət olmaz.

    Buraxılış Tarixi: Seçilməsi məcburidir və gələcək bir tarix olmalıdır. Keçmişə səyahət hələ ixtira edilməyib.

    Missiyanın Növü: Seçilməsi məcburidir. Məqsədimiz nədir?

Mərhələ 2: Heyətin Seçimi

Bu bölmə useFieldArray istifadə edərək heyət üzvlərini dinamik olaraq əlavə etməyə və (təəssüf ki) silməyə imkan verməlidir.

Sahələr (hər heyət üzvü üçün):

    Adı: Input komponenti.

    Vəzifə: Select komponenti - Seçimlər: "Komandir", "Pilot", "Mühəndis", "Alim", "Ksenobotanik", "Həkim", "Android (Psixoloji Dəstək)".

    Təcrübə Səviyyəsi: NumberInput komponenti - 1-dən 10-a qədər.

    Komandir tək başına sadəcə təchizat missiyasına çıxa bilər

Validasiya Qaydaları:

    Missiyada minimum 3, maksimum 7 heyət üzvü olmalıdır. Kosmosda tək qalmaq təhlükəlidir.

    Heyət üzvlərindən yalnız biri "Komandir" vəzifəsində olmalıdır. Gəmidə iki kapitan olmaz!

    Hər bir heyət üzvünün Adı və Vəzifəsi məcburidir.

    Təcrübə Səviyyəsi 1 ilə 10 arasında bir rəqəm olmalıdır. Yeni başlayanları təhlükəli missiyalara göndərmirik.

Mərhələ 3: Yük, Raket və Təchizat

Sahələr:

    Raket Seçimi: Select komponenti - Seçimlər:

        "Starship" (Maksimum Yük: 100,000 kq)

        "Falcon Heavy" (Maksimum Yük: 64,000 kq)

        "Artemis V" (Maksimum Yük: 150,000 kq, Yüksək Riskli)

    Yükün Ümumi Çəkisi (kq): NumberInput komponenti.

    Missiya Təchizatı (Şərti): CheckboxGroup və Checkbox komponentləri. Bu sahələr qrupu 1-ci Mərhələdə seçilmiş "Missiya Növü"-nə əsasən dəyişməlidir.

        Əgər "Kəşfiyyat" seçilibsə (Elmi Cihazlar):

            "Spektrometr"

            "Rover (6 təkərli)"

            "Qazma qurğusu"

            "Atmosfer Sensoru"

            "Ekzo-DNT Sekvenseri"

        Əgər "Təchizat" seçilibsə (Logistik Avadanlıq):

            "Avtonom Yük Dronları"

            "Modulyar Anbar Konteynerləri"

            "Resurs Emalı Qurğusu"

            "Hidroponik Ferma Modulu"

        Əgər "Məskunlaşma" seçilibsə (Koloniya Qurğuları):

            "Bio-Qübbə Başlanğıc Kiti"

            "Atmosfer Prosessoru"

            "3D-Habitat Printeri"

            "Su Təmizləmə Sistemi"

Validasiya Qaydaları:

    Raket Seçimi məcburidir. Raketsiz kosmosa gedə bilmərik.

    Yükün Ümumi Çəkisi məcburidir və müsbət rəqəm olmalıdır.

    Daxil edilən Yükün Ümumi Çəkisi seçilmiş raketin maksimum yük həcmindən çox olmamalıdır. Fizika qanunlarına qarşı çıxmaq olmaz!

    Seçilmiş missiya növünə uyğun olaraq ən azı bir təchizat seçilməlidir. Boş getməyin mənası yoxdur.

4. Son Təqdimat (Missiyanı Başlat!)

Son mərhələdə "Missiyanı Koinata Göndər!" düyməsi olmalıdır. Bu düyməyə kliklədikdə, Zustand store-da toplanmış bütün mərhələlərin məlumatları console.log ilə vahid bir "Missiya Manifesti" obyekti şəklində çıxarılmalı və ekranda Alert komponenti ilə bir uğur mesajı göstərilməlidir: "Uğurlar, Kəşfiyyatçı! Missiya planı təsdiqləndi və yola çıxmağa hazırdır."

5. Bonus Tapşırıqlar (Əfsanəvi Statusu üçün)

    Addım Göstəricisi: Formanın yuxarısında Chakra UI Stepper (və ya bənzəri) komponenti ilə aktiv mərhələni vizual olaraq göstərin.

    Yaddaş Protokolu: Zustand store-una persist middleware əlavə edərək, formanın vəziyyətini localStorage-da saxlayın ki, kosmik fırtına (səhifə yenilənməsi) zamanı məlumatlar itməsin.

    Unikallıq Yoxlaması: Asinxron validasiya tələb edən bir sahə əlavə edin. Məsələn, "Missiyanın Kod Adı" daxil edildikdə, bunun Qalaktik Verilənlər Bazasında unikal olduğunu yoxlayan saxta bir API sorğusu (2 saniyəlik setTimeout ilə simulyasiya edilə bilər) göndərin. Əgər ad artıq mövcuddursa, xəta mesajı çıxarın.

    Missiyanın Uğur Ehtimalı: Son mərhələdə toplanan məlumatlara əsasən sadə bir "Uğur Ehtimalı" faizi hesablayıb göstərin. Məsələn: (Heyətin ortalama təcrübəsi * 10)% + (Raketin yük ehtiyatı)% - (Missiyanın risk faktoru)%. Bu, sadəcə əyləncəli bir vizual elementdir!
