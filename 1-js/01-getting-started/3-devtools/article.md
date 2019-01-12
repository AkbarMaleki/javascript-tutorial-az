
# Tərtibatçı konsolu

Kod xətayalara meyillidir. Çox güman ki, siz də bəzən səhvlər edəcəksiniz... Çox güman ki?! Yox, əgər robot deyilsinizsə, siz *mütləq* səhvlər edəcəksiniz.

Lakin brauzer mühitində istifadəçilər baş vermiş xətaları görmürlər. Yəni əgər yazdığınız skriptdə nəsə qaydasında deyilsə, problemin nədə olduğunu bilə bilməyəcəksiniz və problemi bilmədən onu həll etmək də olmayacaq.

Xətaları görmək və yazdığımız skriptlər haqqında digər məlumatlar əldə etmək üçün brauzerlərin tərkibində "tərtibatçı alətləri" mövcuddur.

Əksər proqramçılar bu cür alətlər üçün Chrome və Firefoxa arxalanır, çünki bu brauzerlər ən yaxşı tərtibarçı alətlərini təklif edir. Digər brauzerlər isə bəzən yeni xüsusiyyətlər irəli sürsələr də əksər hallarda Chrome və Firefox ilə eyni imkanlar irəli sürürlər. Yəni əksər proqramçıların "sevimli" brauzerləri var, yalnız problem brauzer spesifik olduğu halda digər brauzerlər keçir edirlər.

Tərtibatçı alətləri güclüdürlər; onların çoxlu sayda xüsusiyyətləri var. Başlanğıc üçün, biz onları necə açmağı, xətalara necə baxmağı və sadə JavaScript komandaları icra etməyi öyrənəcəyik.

## Google Chrome

[bug.html](bug.html) səhifəsini açın.

Açdığınız səhifədə kiçik bir xəta mövcuddur. Lakin bu xəta ziyarətçidən gizlədilmişdir, gəlin tərtibatçı alətlərini açaq və xətanın nə olduğunu araşdıraq.

Bunun üçün `key:F12` düyməsini sıxın, əgər Mac istifadəçisinizsə, onda `key:Cmd+Opt+J`.

Tərtibatçı alətləri defolt olaraq Developer Konsolu açacaq.

Aşağıdakı kimi pəncərə görəcəksiniz:

![chrome](chrome.png)

Tərtibatçı alətlərinin dəqiq görünüşü sitifadə etdiyiniz Chrome-un versiyasında asılıdır. Görünüş vaxt keçdikcə dəyişə bilər ancaq sonda eyni təəssüratı yaradır.

- Konsolda biz qırmızı ilə yazılmış xətanın detallarını görə bilirik. Bu halda, xəta bizə bilinməyən "lalala" komandasının işləndiyini deyir.
- Sağ tərəfdə isə kliklənə bilən `bug.html:12` yazısını görürük. Onun üstünə kliklədiyimizdə bizi xətanın hansı faylda və hansı sətirdə baş verdiyini görə bilərik.

Xətadan aşağıda isə mavi rəngdə `>` simvolunu görəcəksiniz. Bu işarə "komanda sətirini" işarə edir və orada JavaScript komandalarını icra edə bilərik. İstədiyiniz skripti yazdıqdan sonra `key:Enter` düyməsinə basın (bir neçə sətir yazmaq üçün `key:Shift+Enter` basın).

İndi biz öz səhvlərimizi görə bilirik, bu başlanğıc üçün kifayətdir. Bu mövzuda daha ətraflı sonrakı bölmələrdə danışacağıq.


## Firefox, Edge, və başqaları

Əksər brauzerlər tərtibatçı alətlərini `key:F12` düyməsi ilə açırlar.

Yerdə qalan görünüş və funksionallıqlar demək olar ki, eynidir. Bu alətlərlə hər hansı biz brauzerdə kifayət qədər təcrübə topladıqdan sonra rahatlıqla digərlərinə keçid edə bilərsiniz. Başlağız üçün Chromedan istifadə etməyiniz məsləhətlidir.

## Safari

Safari (Mac brauzerdir, Windows/Linux tərəfindən dəstəklənmir) bir qədər fərqlidir. Əvvəlcə "Develop menu" seçimini aktivləşdirmək lazımdır.

Bunun üçün Preferences menyusundan "Advanced" panelini seçək lazımdır. Ən aşağıda bir checkbox görəcəksiniz:

![safari](safari.png)

İndi isə konsolu açmaq üçün `key:Cmd+Opt+C` basın. Onu da nəzərdən qaçırmayın ki, yuxadırda "Develop" adlı yeni bir menyu meydana gəlmişdir, ondan istifadə edib, bir çox xüsusiyyətlərindən yarana bilərsiniz.

## Xülasə

- Tərtibatçı alətləri bizə səhvləri görmək, komandalar icra etmək və başqa bir çox imkanlar yaradır.
- Onlardan istifadə etmək üçün əksər brauzerlərdə `key:F12` düyməsini sıxmaq lazımdır. Mac üçün Chromda `key:Cmd+Opt+J`, Safaridə isə `key:Cmd+Opt+C` düyməsindən istifadə etmək lazımdır (aktivəşdirdikdən sonra).

Artıq mühit haqqında kifayət qədər məlumatımız olduğu üçün növbəti bölmədə JavaScripti özünü öyrənməyə başlayacağıq.
