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

JavaScript's abilities in the browser are limited for the sake of the user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.

Examples of such restrictions include:

- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS system functions.

    Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like "dropping" a file into a browser window or selecting it via an `<input>` tag.

    There are ways to interact with camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must contain a special JavaScript code that handles data exchange.

    This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com` and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.png)

Such limits do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugin/extensions which may ask for extended permissions.

## JavaScripti ünikal edən nədir?

JavaScript dilini əvəzedilməz edən ən az *üç* cəhət var:

```compare
+ HTML/CSS ilə tam inteqrasiya bacarığı.
+ Sadə şeyləri asanlıqla həll edə bilmək.
+ Əksər brauzerlər tərəfindən dəstəklənməsi və defolt olaraq aktiv olması.
```

JavaScript bu üç xüsusiyyəti özündə birləşdirən yeganə brauzer texnologiyasıdır.

That's what makes JavaScript unique. That's why it's the most widespread tool for creating browser interfaces.

While planning to learn a new technology, it's beneficial to check its perspectives. So let's move on to the modern trends affecting it,  including new languages and browser abilities.


## JavaScript "üzərindən" dillər

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it "under the hood".

Examples of such languages:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps). It was initially offered by Google as a replacement for JavaScript, but as of now, browsers require it to be transpiled to JavaScript just like the ones above.

There are more. Of course, even if we use one of these languages, we should also know JavaScript to really understand what we're doing.

## Xülasə

- JavaScript ilkin olaraq yalnız brauzerlərdə işləməyi üçün yaradılmışdır, lakin indi o web server, IoT və s. kimi bir çox mühitlərdə istifadə olunur.
- Günümüzdə JavaScript brauzer mühitində ən çox istifadə olunan bir dil kimi unikal mövqe tutmuşdur və HTML/CSS ilə tam inteqrasiya oluna bilir.
- Bir başa JavaScriptə "transpilyasiya" oluna bilən bir çox dil mövcuddur. JavaScript ilə bir qədər təcrübəniz olduqdan sonra onlara da nəzər yetirməyiniz məsləhət görülür.
