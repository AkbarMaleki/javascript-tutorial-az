# Salam, Dünya!

Oxuduğunuz dərslik platformadan asılı olmayaraq, JavaScriptin sırf özündən bəhs edir. Daha sonra biz Node.JS və JavaScripti istifadə edən digər platformalarla da tanış olacağıq.

Skriptləri işə salmaq üçün bizə bir mühit lazımdır. Dərsliyimizin onlayn olduğunu nəzərə alsaq, bunun üçün ən yaxşı mühit brauzerdir. Sizin başqa mühitlərlə maraqlanacağınızı da nəzərə alaraq, brauzer spesifik komandaları (misalçün `alert`) minimum istifadə etməyə çalışacağıq. Brauzer daxili JavaScript haqqında isə [növbəti hissədə](/ui) öyrənəcəyik.

Əvvəlcə, gəlin skripti web səhifəyə necə bağlayacağımıza baxaq. Əgər server mühitindən istifadə edirsinizsə (misalçün Node.JS) skriptinizi `node my.js` komandasını daxil edərək işə sala bilərsiniz.


## "script" etiketi

JavaScript kodları `<script>` ektiketinin köməyi ilə HTML səhifənin istənilən hissəsinə yerləşdirilə bilər.

Misalçün:

```html run height=100
<!DOCTYPE HTML>
<html>

<body>

  <p>Skriptdən əvvəl...</p>

*!*
  <script>
    alert( 'Salam, dünya!' );
  </script>
*/!*

  <p>...Skriptdən sonra.</p>

</body>

</html>
```

```online
Yuxarıdakı nümunəni işə salmaq üçün qutunun sağ yuxarı küncündəki "Play" düyməsini sıxın.
```
JavaScript kodları `<script>` etiketin daxilində yerləşir və brauzer etiketi emal etdiyi zaman, skitptlər də işə düşür.


## Müasir markap

`<script>` etiketinin hazırda nadir hallarda işlənilən bəzi attributları mövcuddur. Onlarla köhnə kodlarda rastlaşa bilərsiniz:

`type` attributu: <code>&lt;script <u>type</u>=...&gt;</code>
: Əvvəlki HTML standartları, HTML4, skriptlərin tipinin olmasını tələb edirdi və çox hallarda bu `type="text/javascript"` olurdu. Bu attributun yazılması artıq tələb olunmur. Yeni HTML standartları, HTML5, bu attributun mənasını tamamilə dəyişmişdir və onu başqa məqsədlər üçün istifadə edir. Hazırda bu attributu JavaScript modulları üçün istifadə edə bilərsiniz. JavaScript modulları haqqında növbəti fəsillərdə öyrənəcəyik.

`language` attributu: <code>&lt;script <u>language</u>=...&gt;</code>
: Bu attribut skriptin dilini təyin etmək üçün yazılır. JavaScript brauzerdə defolt dil sayıldığı üçün artıq bu attributa ehtiyac qalmayıb. Onu istifadə etmək üçün heç bir səbəb yoxdur.

Srkiptdən əvvəl və sonra rəylər.
: Çox köhnə kitablarda `<script>` daxilində rəylərin qeyd olunmasını aşağıdakı kimi görə bilərsiniz:

    ```html no-beautify
    <script type="text/javascript"><!--
        ...
    //--></script>
    ```

    Bu cür rəylər artıq skirptlərdə istifadə olunmur. Əvvəllər bu rəylər `<script>` etiketini dəstəkləməyən brauzerlər üçün yazılırdı ki, brauzer sözügedən skripti emal etməsin. Lakin artıq son 15 ildə belə bir problem olmadığı üçün bu cür rəylər heç bir əhəmiyyət kəsb etmir.


## Xarici skriptlər

Çoxlu JavaScript kodlarımız olduğu təqdirdə, bu kodları başqa bir fayla yerləşdirə bilərik.

Skript faylları HTML səhifəyə `src` attributu vasitəsilə bağlanır:

```html
<script src="/path/to/script.js"></script>
```

Yuxarıda gördüyünüz şəkildə `/path/to/script.js` skriptin yerləşdiri qovluğun tam yoludur. 

`"script.js"` faylı web səhifəmizin yerləşdiyi qovluqdadırsa, onu `src="script.js"` şəklində də daxil edə bilərik.

Bununla bərarbər biz skriptin tam URL-ini də daxil edə bilərik:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js"></script>
```

Bir neçə skripti səhifəyə qoşmaq üçün, o qədər də `<script>` etiketindən istifadə etmək lazımdır:

```html
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
```

```smart
Bir qayda olaraq, sadəcə çox sadə skriptlər bir başa olaraq HTML səhifəyə daxil edilir. Daha mürəkkəb və qarışıq skriptlət başqa fayllarda saxlanılır.

Bunun bir xeyir də ondadır ki, brauzerlər bu cür faylları yükləyib öz [keş](https://en.wikipedia.org/wiki/Web_cache) lərində saxlayırlar və beləliklə eyni fayl hər dəfə istifadəçinin qurğusuna yüklənmir.

Bu yolla trafiki azalda və səhifəmizi daha sürətli edə bilərik.
```

````warn header="`src` təyin olunduğu halda, skriptin məzmunu nəzərə alınmır."
Bir `<script>` etiketində eyni zamanda `src` attributu və daxili skript ola biklməz.

Misalçün aşağıdakı skript işləməyəcək:

```html
<script *!*src*/!*="file.js">
  alert(1); // src təyin olunduğu üçün məzmun nəzərə alınmır
</script>
```

Bunun üçün xarici `<script src="…">` yoxsa müntəzəm `<script>` işlədəcəyimizi əvvəlcədən müəyyənləşdirməliyik.

Yuxarıdakı nümunə normal qaydada işləməsi üçün iki hissəyə bölünə bilər:

```html
<script src="file.js"></script>
<script>
  alert(1);
</script>
```
````

## Xülasə

- Səhifəyə JavaScript kodlarını daxil etmək üçün `<script>` etiketindən istifadə edirik.
- `type` və `language` attributları artıq istifadə olunmur.
- Başqa bir faylda olan skripti səhifəyə daxil etmək üçün `<script src="path/to/script.js"></script>` istifadə edirik.

Brzuer srkiptləri və onları web səhifələr ilə qarşılıqlı əlaqələri ilə bağlı öyrənməli olduqca çox şey var. Amma yadda saxlayaq ki, dərsliyin bu hissəsi sırf JavaScript dilinin özünə həsr edilmişdir. Bu səbəbdən, brauzer spesifik xüsusiyyətlərlə başımızı qarışdırmamaq daha yaxşı olar. Biz brazueri sadəcə olaraq JavaScript kodlarını icra etmək üçün istifadə edəcəyik, çünki bu onlayn oxuyanlar üçün olduqca rahatdır.