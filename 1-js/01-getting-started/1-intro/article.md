# JavaScriptə giriş

Gəlin JavaScriptin niyə belə xüsusi olduğuna, onunla nələrə nail olacağımıza və onun hansı texnologiyalarla uzlaşdığına baxaq.

## JavaScript nədir?

*JavaScript* ilkin olaraq *"web səhifələri canlandırmaq"* üçün yaradılmışdır.

Bu dildə yazılan proqramlar *skript* adlanır. Həmin skriptlər bir başa olaraq HTML səhifənin içərisində yazıla və səhifə yeniləndiyində avtomiatik işə düşə bilər.

Skriptlər təmiz mətn şəklində yazılır və icra olunur. Belə ki, onların xüsusi hazırlığa və ya kompilyasiya mərhələsinə ehtiyacı yoxdur.

Bu nöqteyi nəzərdən, JavaScript, çox vaxt özünə bənzədilən və məşhur bir proqramlaşdırma dili olan [Java](https://en.wikipedia.org/wiki/Java_(programming_language))dan olduqca fərqlənir.

```smart header="Niyə <u>Java</u>Script?"

JavaScript ilk dəfə yaradılarkən onun başqa bir adı var idi: "LiveScript". Lakin o dövrdə (1995) Java daha məşhur olduğu üçün, bu dilə Javanın "kiçik qardaşı" kimi yanaşmaq qərarı verildi.

Lakin qısa bir müddət sonra JavaScript, özünə məxsus, [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) adlı standartlara sahib olan müstəqil bir dilə çevrildi və hazırda Java ilə demək olar ki, heç bir əlaqəsi yoxdur.
```

Günümüzdə isə JavaScript sadəcə brauzer mühitində deyil, serverdə və [JavaScript mühərriki](https://en.wikipedia.org/wiki/JavaScript_engine) quraşdırılmış istənilən qurğuda icra oluna bilir.

Brauzerlər "JavaScript virtual maşını" adlı daxili mühərrikə sahibdirlər.

Müxtəlif şirkətlər tərəfindən hazırlaşnmış bu cür mühərriklərin müxtəlif "kod adları" var. Misalçün:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome və Opera'da.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox'da.
- ...Bu adlara Internet Explorer'in tərkibində olan "Tridient" və "Chakra", Microsoft Edge'in tərkib hissəsi olan "ChakraCore" və Safari brauzerindəki "Nitro" və "SquirrelFish" də daxildir.

Yuxarıda qeyd etdiyimiz terminlərlə bir çox məqalələrdə və bloqlarda rastalaşacağınız üçün, onları yadda saxlamağınız məsləhətlidir. Misalçün, əgər *"filan özəllik V8 tərəfindən dəstəklənmir"* deyildiyində biz artıq həmin funksionallığın Opera və Chrome'da heç bir işə yaramayacağını bilmiş olacağıq.

```smart header="Mühərriklər necə işləyir?"

JavaScript mühərrikləri olduqca qəliz bir quruluşa malikdirlər. Lakin təməl məfhumlar sadədir.

1. Mühərrik skriptləri oxuyur və təhlil edir.
2. Daha sonra həmin skriptləri maşın koduna çevirir.
3. Və son olaraq həmin kodlar sizin kompüteriniz tərəfindən icra olunur.

Mühərriklər sadəcə bununla kifayətlənməyib, hər mərhələdə bir çox optimallaşdırma işləri aparırlar. Onlar maşın koduna çevrilmiş (kompilyasiya olunmuş) sktriprləri analiz edir və əldə olunan biliklərə əsasən həmin maşın kodunu da optimallaşdırmağa çalışırlar. Bu mərhələlərdən sonra skriptlər daha sürətli icra olunmağa başlayır.
```

## JavaScrip brauzer daxilində nələrə qadirdir?

Müasir JavaScipt olduqca "güvənli" dildir. Belə ki, o, ilkin olaraq brauzer daxilində istifadə olunduğu üçün daxili yaddaş və prosessora bir başa çıxış imkanı vermir.

Buna baxmayaraq JavaScriptin qabiliyyətləri onun işlədiyi mühittən də çox asılıdır. Misalçün [Node.JS](https://wikipedia.org/wiki/Node.js) JavaScript üçün sənədləri oxuyub yazmaq, şəbəkə səviyyəli sorğular göndərmək və s. kimi əlavə imkanlar yaradır.

JavaScript brauzer daxilində web səhifənin manipulyasiyası ilə bağlı hər şeyi etmək bacarığına malikdir. Buraya istifadəçi ilə qarşılıqla təsirdə olmaq, web serverə sorğu göndərmək və digər mühüm funksionallırlar daxildir.

Misalçün, bzauzer daxilində JavaScript aşağıdakı funksionallıqlara malikdir:

- Səhifəyə yeni HTML əlavə etmək, mövcud məzmunu dəyişmək və CSS stillərini dəyişmək.
- İstifadəçinin hərəkərlərinə reaksiya göstərmək, siçanın sağ və ya sol düyməsi klikləndiyində, kursor hərəkət etidiyində, hər hansı bir düymə sıxıldığında və s. müəyyən kodlar icra etmək.
- Şəbəkə üzərindən sorğular göndərmək, sənədləri yükləmək və endirmək ([AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) və [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) texnologiyaları vasitəsilə). 
- Çərəzləri (cookie) təyin etmək və əladə etmək, istifadəçiyə sual vermək və mesajlar göstərmək.
- İstifadəçi haqqında məlumatları, onun seçimlərini və s. yadda saxlamaq ("local storage").

## JavaScript brauzer daxilində nələri EDƏ BİLMƏZ?

JavaScriptin bacarıqları bəzi güvənlik məqsədləri üçün brauzer daxilində limitlənmişdir. Məqsəd şəxsi məlumatların digər bir web səhifə tərəfindən oğurlanmasının qarşısını almaq və istifadəçiləri mümkün qədər güvənli bir mühitdə saxlamaqdır.

Bu məhdudiyyətlərə nümunə kimi aşağıdakıları göstərmək olar:

- JavaScript sərt disk üzərindəki sənədləri oxuya/yaza, nüsxələyə və ya icra edə bilməz. Onun əməliyyat sisteminin bu cür funksionallıqlarına bir başa çıxışı yoxdur.

    Müasir brauzerlər sənədlərlə işləməyə müəyyən hallarda yol verir. Buna misal olaraq hər hansı bir sənədi brauzer pəncərəsinə sürüşdürmək və ya onu `<input>` etiketi vasitəsilə seçməyi göstərmək olar.

    Bundan əlavə, brauzerlər yalnız istifadəçinin icazəsi olduğu halda kamera, mikrofon və digər qurğularla işləməyə də imkan yaradır. Bu səbəbdən əminliklə deyə bilərik ki, hər hansı bir web səhifə sizin haqqınızda səsyazma və görüntüləri toplayıb daha sonra [DTX](https://az.wikipedia.org/wiki/Azərbaycanın_Dövlət_Təhlükəsizliyi_Xidməti)-yə göndərmir.

- Müxtəlif pəncərələr bir çox hallarda bir biri haqqında xəbərsiz olurlar. Bəzən isə xəbərdar olurlar, misalçün əgər bir pəncərədəki JavaScript digər səhifəni açmaq üçün istifadə olunursa. Lakin bu halda belə, həmin pəncərələr müxtəlif saytlardan gəlirsə, bir səhifədəki skript digər səhifədə icra oluna və ya orda dəyişikliklər edə bilməz (əgər həmin pəncərələr müxtəlif domenldən və portdan gəlir və ya fərqli protokollardan istifadə edirsə). 

    Bu "Eyni mənşə siyasəti" (Same Origin Policy) adlanır. Bunu həyata keçirmək üçünsə, hər iki səhifə məlumat mübadiləsi üçün zəruri olan xüsusi skriptləri icra etməlidirlər.

    Bu məhdudiyyətlər istifadəçilərin güvənliyini təmin etmək üçün qoyulmuşdur. İstifadəçinin açdığı `http://anysite.com` adlı bir səhifə heç bir halda başqa bir pəncərədə açılmış `http://gmail.com` adlı səhifəyə çatıb ordan məlumat əldə etməməlidir. 

- JavaScript hazırki səhifənin gəldiyi server ilə asanlıqla danışa və məlumat mübadiləsi apara bilər. Lakin başqa serverlər və saytlarla eyni şeyi etmək bir başa mümkün deyil. Bunu mümkün qılmaq üçün həmin serverlər ilə (HTTP başlıqlar vasitəsilə) müəyyən razılığa gəlmək lazımdır. Bir daha qeyd etmək istərdik ki, bu bir güvənlik göstəricisidir. 

![](limitations.png)

Qeyd edək ki, bu cür məhdudiyyətlər yalnız brauzer daxilində mövcuddur. 

## JavaScripti ünikal edən nədir?

JavaScript dilini əvəzedilməz edən ən az *üç* cəhət var:

```compare
+ HTML/CSS ilə tam inteqrasiya bacarığı.
+ Sadə şeyləri asanlıqla həll edə bilmək.
+ Əksər brauzerlər tərəfindən dəstəklənməsi və defolt olaraq aktiv olması.
```

JavaScript bu üç xüsusiyyəti özündə birləşdirən yeganə brauzer texnologiyasıdır.

Bu JavaScripti əvəzedilməz edir və məhz bu səbəbdən JavaScript brauzer daxili interfeyslərin yaradılması üçün ən çox istifadə olunan alətdir.

Yeni bir texnologiyanı öyrənərkən onun perspektivinə kiçik bir nəzər salmaq sizin üçün yararlı ola bilər. Gəlin JavaScriptə təsir edən trendlərə nəzər yetirək.


## JavaScript "üzərindən" dillər

JavaScriptin sintaksisi hər kəsin ehtiyaclarını ödəyə bilmir. Müxətlif insanlar müxtəlif cür funksionallıqlar tələb edir.

Bunu gözləmək olar, çünki layihələr və tələblər hamı üçün fərqli ola bilər.

Belə ki, son dövlərlərdə brauzerdə icra olunmamışdan əvvəl JavaScriptə çevrilən (transpliyasiya olunan) çoxlu sayda yeni dil meydana gəlmişdir.

Müasir ələtlər vasitəsilə bu cür transpilyasiya mərhlələri olduqca sürətli edir və asanlaşdırı. Bu alətlər, proqram tərtibatçılarına rahatlıqla başqa dildə yazmağa və yazdığı kodları avtomatik olaraq JavaScriptə çevirməyə imkan yaradır.  

Bu cür dillərə aşağıdakıları misal çəkmək olar:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [CoffeeScript](http://coffeescript.org/) JavaScript üçün sintaktik şəkərdir (syntactic sugar). 
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps). It was initially offered by Google as a replacement for JavaScript, but as of now, browsers require it to be transpiled to JavaScript just like the ones above.

There are more. Of course, even if we use one of these languages, we should also know JavaScript to really understand what we're doing.

## Xülasə

- JavaScript ilkin olaraq yalnız brauzerlərdə işləməyi üçün yaradılmışdır, lakin indi o web server, IoT və s. kimi bir çox mühitlərdə istifadə olunur.
- Günümüzdə JavaScript brauzer mühitində ən çox istifadə olunan bir dil kimi unikal mövqe tutmuşdur və HTML/CSS ilə tam inteqrasiya oluna bilir.
- Bir başa JavaScriptə "transpilyasiya" oluna bilən bir çox dil mövcuddur. JavaScript ilə bir qədər təcrübəniz olduqdan sonra onlara da nəzər yetirməyiniz məsləhət görülür.
