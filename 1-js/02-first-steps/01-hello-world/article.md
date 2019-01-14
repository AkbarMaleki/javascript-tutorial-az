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

````warn header="If `src` is set, the script content is ignored."
A single `<script>` tag can't have both the `src` attribute and code inside.

This won't work:

```html
<script *!*src*/!*="file.js">
  alert(1); // the content is ignored, because src is set
</script>
```

We must choose either an external `<script src="…">` or a regular `<script>` with code.

The example above can be split into two scripts to work:

```html
<script src="file.js"></script>
<script>
  alert(1);
</script>
```
````

## Xülasə

- We can use a `<script>` tag to add JavaScript code to a page.
- The `type` and `language` attributes are not required.
- A script in an external file can be inserted with `<script src="path/to/script.js"></script>`.


There is much more to learn about browser scripts and their interaction with the webpage. But let's keep in mind that this part of the tutorial is devoted to the JavaScript language, so we shouldn't distract ourselves with browser-specific implementations of it. We'll be using the browser as a way to run JavaScript, which is very convenient for online reading, but only one of many.
