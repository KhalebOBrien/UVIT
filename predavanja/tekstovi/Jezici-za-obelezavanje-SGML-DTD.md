# УВИТ - SGML и DTD

[Владимир Филиповић](https://vladofilipovic.github.io/index-cy.html){:target="_blank"}

## Однос SGML и DTD

Садржај и значење елемената није прописано мета језиком, већ сваки језик дефинисан у оквиру SGML-а дефинише сопствени скуп
етикета које користи за обележавање и дефинише њихово значење и могуће међусобне односе.

То је реализовано на следећи начин:

- Сваком документу, придружен је његов тип.

- Тип документа одређује синтаксу документа тј. одређује који елементи, атрибути и ентитети се могу јавити у оквиру документа и какав је њихов међусобни однос.

Посебни програми који се називају SGML парсери или SGML валидатори могу да испитају да ли је документ у складу са својим
типом тј. да ли задовољава сва синтаксна правила прописана одговарајућим типом.

Тип документа се код SGML одређује помоћу тзв. декларација типа документа.

### Опис DTD-a

Дефиниција типа документа - DTD (енг. Document Type Definition) је скуп декларација за обележавање које дефинишу тип документа код језика за обележавање из SGML породице језика за обележавање (SGML, XML, HTML, ...).

DTD користи терцијалну формалну синтаксу, којом декларише који елементи и референце могу да се појаве, и на ком месту у документу одређеног типа. DTD декларацијом се одређује и садржај и атрибути елемената који могу да се појаве у огквиру SGML документа. DTD такође може да декларише ентитете који могу бити искоришћени у инстанци документа.

Сврха DTD-а  је да дефинише дозвољене градивне елементе једног SGML документа. Са DTD-ом, свака SGML датотека може носити опис свог формата. Са DTD-ом, независне групе људи могу се сагласити да користе стандардни DTD за размену података. У таквом случају, развијена апликација може употребљавати стандардни DTD како би проверила да су подаци, примљени из спољашњег света валидни. Такође, она може користити DTD за верификацију сопствених података.

На основу декларације у SGML документу, може се рећи да постоје два типа DTD: унутрашњи DTD и спољашњи DTD.

Када је DTD декларисан унутар SGML датотеке, онда се ради о **унутрашњем** DTD-у, а ако је декларисан у посебној тј. одвојеној датотеци, тада је то **спољашњи** DTD.

DTD-ом се описују следеће важне карактеристике структуре SGML документа:

- елементи који се могу појавити у SGML документу.

- редослед којим се могу појавити.

- факултативни и обавезни елементи.

- атрибути елемената и да ли су они опционални или обавезни.

- могу ли атрибути имати подразумеване вредности.

Коришћење DTD-а обезбеђује следеће предности:

- Документација - може се дефинисати сопствени формат за SGML датотеке, па проучавањем DTD документa, корисник/програмер може да разуме структуру података која се обрађује.

- Провера ваљаности - обезбеђује се начин за проверу ваљаности SGML датотека, тако што се проверава да ли се елементи појављују у правом редоследу, да ли су обавезни елементи и атрибути на месту, елементи и атрибути нису уметнути на нетачан начин итд.

Међутим, одмах се могу уочити и неки недостаци код DTD-а:

- Подржава само ниску као тип података.

- Није објектно оријентисан, па се концепт наслеђивања не може применити на DTD-ове.

- Ограничене су могућности изражавања кардиналности елемената.

## Синтакса DTD-а

DTD може бити наведен унутар SGML документа, или се, алтернативно, може чувати у одвојеном документу, а затим се у оквиру SGML документа постави веза према DTD документу.

Основна синтакса DTD-а је следећа:

```xml
<!DOCTYPE element DTD_identifikator
[
   deklaracija1
   deklaracija2
   ...
]>
```

Значење елелемата претходно описане синтаксе:

- DTD почиње са конструкцијом `<!DOCTYPE`.

- Део `element` саопштава парсеру да парсирање документа започне баш од тог елемента како корена.

- Део `DTD_identifkator` представља идентификатор за DTD, што може бити путања према датотеци која се налази на систему на ком се налази тај SGML документ, или може бити URL датотеке постављене на Интернету. У случају када овај идентификатор реферише на спољашњу путању, он се назива спољашњи подскуп.

- Средње заграде, тј. знаци `[` и `]` ограђују листу декларација елемената (тзв. унутрашњи подскуп). Унутрашњи подскуп се  може опдионално појавити, зависно до тога да какава је структура DTD-а.

Сам DTD се поставља на почетку SGML документа чију структуру описује.

### Унутрашњи DTD

DTD се назива унутрашњим DTD ако су елементи декларисани унутар SGML датотеке. У овом случају, декларација финкционише независно од спољних извора.

Синтакса унутрашњег DTD-а је следећа:

```xml
<!DOCTYPE koreni_element [deklaracije_elemenata]>
```

где је `koreni_element` име елемента који представља корен, a иза њега следе декларације елемената.

Декларације елемената описују струкуру елемената који обарзују SGML (назив, начин записа, редослед појаве, обавезност/опционост, атрибути и сл.).

**Пример.** Илуструје једноставан унутрашњи DTD:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa (ime,kompanija,telefon)>
   <!ELEMENT ime (#PCDATA)>
   <!ELEMENT kompanija (#PCDATA)>
   <!ELEMENT telefon (#PCDATA)>
]>

<adresa>
   <ime>Vladimir Filipovic</ime>
   <kompanija>Matematički fakultet</kompanija>
   <telefon>(011) 123-4567</telefon>
</adresa>
```

&#9608;

Унутрашњи DTD садржи следеће структурне елементе:

- **Почетна декларација.** Она садржи декларацију типа документа, која се обично назива DOCTYPE:

**Пример.** Почетна декларација код претходног унутрашњег DTD-а:

```xml
<!DOCTYPE adresa [
```

Уочавамо да кљуној речи `DOCTYPE` претходи ускличник (знак `!`). &#9608;

 Декларација DOCTYPE обавештава парсер да је DTD чији опис следи повезан са SGML документом у ком се декларација налази. Изјава о типу документа DOCTYPE мора се појавити на почетку документа - она није дозвољена нигде другде у документу. Отворена средња заграда (тј. `[`) после речи `адреса` указује да се ради о DTD-у смештеном унутар датотеке.

- **Тело DTD-а.** Декларацију DOCTYPE прати тело DTD-а, где се декларишу елементи, атрибути, ентитети и анотације:

**Пример.** Тело DTD-а за унутрашњеи DTD из претходног примера:

```xml
   <!ELEMENT adresa (ime,kompanija,telefon)>
   <!ELEMENT ime (#PCDATA)>
   <!ELEMENT kompanija (#PCDATA)>
   <!ELEMENT telefon (#PCDATA)>
```

Овде је декларисано неколико елемената који чине речник документа. Тако `<!ELEMENT kompanija (#PCDATA)>` дефинише  елеменат `kompanija` да буде типа `#PCDATA` '- текстуални податак који се може парсирати.

Даље, слично декларацији DOCTYPE, декларације елемената ткоађе морају почети с ускличником, тј ускличник мора да претходи речи `ELEMENT`. &#9608;

- **Завршна декларација.** Одељак декларације DTD-а се затвара помоћу затворене средње заграде и знака "веће" ( тј помоћу знакова `]>`. Овим се ефективно завршава дефиниција типа документа, након које (код унутрашњих DTD) непосредно следи садржај SGML документа.

Што се садржаја SGML документа после DTD-а тиче, тип коренског елемента мора да одговара имену датом у DOCTYPE декларацији.

**Пример.** У претходном примеру, име у DOCTYPE декларацији је `adresa` и оно се поклапа са називом коренског елемента `adresa`, па је овде по том питању све у реду.  &#9608;

### Спољашњи DTD

У спољашњим DTD-овима елементи су декларисани изван SGML датотеке. Дефиницијама елемената се приступа специфицирањем системских атрибута, који могу бити валидна `.dtd` датотекa или важећи URL.

Спољашњи DTD-ови имају следећу синтаксу:

```xml
 <!DOCTYPE koreni_element SYSTEM "ime_datoteke">
```

где је `koreni_element` име елемента који представља корен, a `"ime_datoteke"` реферише на датотеку са наставком `.dtd`.

**Пример.** Следеће означавање приказује спољну употребу DTD-а:

```xml
<!DOCTYPE adresa SYSTEM "adresa.dtd">

<adresa>
   <ime>Vladimir Filipovic</ime>
   <kompanija>Matematički fakultet</kompanija>
   <telefon>(011) 123-4567</telefon>
</adresa>
```

Садржај DTD датотеке `adresa.dtd` је следећи:

```xml
<!ELEMENT adresa (ime,kompanija,telefon)>
<!ELEMENT ime (#PCDATA)>
<!ELEMENT kompanija (#PCDATA)>
<!ELEMENT telefon (#PCDATA)>
```

&#9608;

Реферисање на спољашњи DTD може да се реализује коришћењем системских идентификатора или јавних идентификатора.

- **Системски идентификатор** омогућава да се одреди локација спољне датотеке која садржи DTD декларације. У том случају, синтакса је следећа:

```xml
<!DOCTYPE koreni_element SYSTEM "adresa.dtd" [...]>
```

Као што се може видети, системски идентификатор садржи кључну реч `SYSTEM` иза које следи URI референцa која упућује на локацију DTD документа.

- **Јавни идентификатори** пружају механизам за проналажење DTD ресурса. Они су записани на следећи начин:

```xml
<!DOCTYPE koreni_element PUBLIC "-//Beginning XML//DTD Address Example//EN">
```

У овом случају идентификатор започиње кључном речју `PUBLIC`, након чега следи специјална ниска, која означава кључ за елеменат јавно доступног каталога. Јавни идентификатори се користе за идентификацију елемента у каталогу. Они могу бити у било ком формату, али уобичајени формат за њих је FPI - формални јавни идентификатори (енгл. Formal Public Identifiers).

## Компоненте SGML и DTD

У овој секцији се разматрају SGML компонентама из перспективе DTD. DTD у основи садржи декларације следећих SGML компоненти: елементи, атрибути и ентитети.

### SGML елементи

SGML елементи се могу дефинисати као градивни блокови SGML документа. Елементи се могу посматрати као контејнер који садржи текст, друге елементе, атрибуте, медијске објекте или комбинацију свега претходно наведеног.

Сваки SGML документ садржи један или више елемената чије су границе или ограничене почетним и/или завршним ознакама (етикетама, таговима), односно празним елементима.

**Пример.** Следеће означавање приказује једноставан пример SGML:

```xml
<ime>
   Marko Markovic
</ime>
```

Као што се јасно уочава, дефинисана је ознака `<ime>`. Текст се налази између почетне и крајње ознаке `<ime>`. &#9608;

Елементе, када се користе у SGML-DTD, треба декларисати, што ће бити детаљно размотрено у поглављу које се односи на DTD елементе.

### SGML атрибути

Атрибути су део SGML елемената. Елемент може имати било који број јединствених атрибута. Атрибути дају више информација о SGML елементу, односно дефинишу одређено својство елемента. SGML атрибут је увек пар име-вредност.

**Пример.** Следеће означавање приказује једноставан пример SGML атрибута:

```xml
<img src = "cvet.jpg"/>
```

Овде је `img` име елемента, док је `src` име атрибута, а `cvet.jpg` је вредност дата атрибуту `src`.  &#9608;

Ако се атрибути користе у SGML DTD-у, тада их треба декларисати, што ће бити детаљно размотрено у поглављу о DTD атрибутима.

### SGML ентитети

Ентитети су резервисана места у SGML-у. Они се могу пријавити у прологу документа или у DTD-у. Ентитети се првенствено могу категоризовати као:

- Уграђени ентитети

- Знаковни ентитети

- Општи ентитети

- Параметарски ентитети

Пет уграђених ентитета сe често јавља у добро обликованом SGML-у. То су:

- знак за "трговачко и" (`&`), записује се као `&amp;`

- апостроф или једностуки наводник (`'`), записује се као `&apos;`

- знак веће од (`>`), записује се као `&gt;`

- знак мање од (`<`), записује се као `$lt;`

- змак ѕа двоструки наводник: (`"`), записује се као `&quot;`

Детаљније ће се проучити декларације SGML ентитета у поглављу које с еодноси на DTD ентитете.

### DTD Елементи

DTD елемент се декларише декларацијом `ELEMENT`. Када SGML датотеку буде валидирана преко DTD-а, рашчлањивач у почетку проверава корени елемент, а затим редом све његове потомке.

Декларације DTD елемената имају овај општи облик:

```xml
<!ELEMENT ime_elementa (sadrzaj)>
```

Уочавају се следећи делови:

- Декларација `ELEMENT` користи се за означавање парсеру да следи дефиниција елемента.

- `ime_elementa` је назив елемента (такође се зове и генерички идентификатор) који се дефинише.

- `sadrzaj` дефинише који садржај (ако постоји) може да уђе у састав елемента.

Садржај декларације елемената у DTD-у може се категорисати на следећи начин:

- Празан садржај

- Садржај елемента

- Мешовити садржај

- Било који садржај

#### Празан садржај

Ово је посебан случај декларације елемената, када елемент не садржи никакав садржај. Празни садржаји су декларисани кључном речи `EMPTY`.

Декларација празног елемента има следећу синтаксу:

```xml
<!ELEMENT ime_elementa EMPTY>
```

У горњој синтакси `ELEMENT` је декларација елемента категорије `EMPTY`, а `ime_elementa` је име празног елемента.

**Пример.** Следећи једноставан пример показује декларацију празног елемента:

```xml
<!DOCTYPE hr[
   <!ELEMENT hr EMPTY>
]>

<hr />
```

У горњем примеру адреса (елеменат `hr`) је декларисана као празан елемент. Ознака за елемент адресе појавити ће се као ниска `<hr />`.  &#9608;

#### Садржај елеменат/елементи

У декларацији елемента са садржајем елемента, садржај би били дозвољени елементи у заградама. Ту се, по потреби, може укључити више елемената.

Следи синтакса декларације елемента са садржајем елемента:

```xml
<!ELEMENT ime_elementa (potomak1, potomak2...)>
```

У овом случају, `ELEMENT` је ознака декларације елемента, `ime_elementa` је име елемента, а `potomak1`, `potomak2` ... су елементи и сваки од тих елемената мора имати своју дефиницију унутар DTD-а.

**Пример.** Једноставан пример за декларацију елемента са садржајем елемента:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa (ime,kompanija,telefon)>
   <!ELEMENT ime (#PCDATA)>
   <!ELEMENT kompanija (#PCDATA)>
   <!ELEMENT telefon (#PCDATA)>
]>

<adresa>
   <ime>Vladimir Filipovic</ime>
   <kompanija>Matematički fakultet</kompanija>
   <telefon>(011) 123-4567</telefon>
</adresa>
```

У овом примеру, `adresa` је елеменат-родитељ, а `ime`, `kompanija` и `telefon` су његови потомци.

У табели која следи приказана је листа оператора и правила синтаксе која се могу применити у дефинисању елемената - потомака:

| Оператор | Синтакса | Опис | Пример |
| :------: | :------- | :--- | :----- |
| **+**    | &lt;!ELEMENT ime_elementa (potomak1+)&gt; | Указује да се елеменат - потомак може појавити један или више пута унутар родитељског елемента | `<!ELEMENT adresa (ime+)?` Елеменат  `ime` може да се појави једном или више пута унутар елемента `adresa`. |
| **&#42;**  | &lt;!ELEMENT ime_elementa (potomak1*)&gt; | Указује да се елеменат - потомак може појавити нула, један или више пута унутар родитељског елемента | `<!ELEMENT adresa (ime*)>` Елеменат `ime` може да се појави нула, једном или више пута унутар родитељског елемента `adresa` |
| **?**  | &lt;!ELEMENT ime_elementa (potomak1?)&gt; | Указује да се елеменат - потомак може појавити нула пута или једном унутар родитељског елемента | `<!ELEMENT adresa (ime?)>` Елеменат `ime` може опционално да се појави унутар родитељског елемента `adresa` |
| **,**  | &lt;!ELEMENT ime_elementa (potomak1, potomak2)&gt; | Даје секвенцу елемената-потомака који морају бити укључени у родитељски елеменат, по редоследу набрајања | `<!ELEMENT adresa (ime, kompanija)>` Секвенца елемената `ime`, `kompanija` се морају појавити у истом редоследу унутар елемента `adresa` |
| **&#124;**  | &lt;!ELEMENT ime_elementa (potomak1 &#124; potomak2)&gt; | Омогућава доношење избора о елементу-потомку | `<!ELEMENT adresa (ime | kompanija)>` Доношење избора који ће од елементата `ime` или `kompanija` морати да се појави унутар елемента `adresa` |

#### Мешовити садржај

Ово је комбинација (`#PCDATA`) и елемената-потомака. `PCDATA` означава текстуалне податке који се огу парсирати, односно текст који није обележен. У моделима мешовитог садржаја текст се може појавити изолован или се може умешати између елемената. Правила за моделе мешовитог садржаја слична су правилима о садржају елемената, што је објашњено у претходном одељку.

Следи генеричка синтакса за садржај мешовитих елемената:

```xml
<!ELEMENT ime_elementa (#PCDATA|potomak1|potomak2)*>
```

Ovde je `ELEMENT` је ознака декларације елемента, `ime_elementa` је назив елемента, `PCDATA` је текст који не садржи обележавања, а `potomak1`, `potomak1` ... су елементи (сваки од ових елемената мора имати своју дефиницију унутар DTD-а).

У декларацији мешовитог садржаја:

- `#PCDATA` мора бити на првом месту.

- Оператор `*` мора следити декларацију мешовитог садржаја ако су укључени елементи - потомци.

- Декларације `#PCDATA` и елементи - потомци морају бити одвојене оператором `|`.

**Пример.** Једноставан пример који демонстрира декларацију мешовитог садржаја у DTD-у:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresа (#PCDATA|ime)*>
   <!ELEMENT ime (#PCDATA)>
]>

<adresа>
   Ovo je tekst koji će biti pomešan sa elementom.potomkom.
   <ime>
      Paja Patak
   </ime>
</adresа>
```

&#9608;

#### Било који садржај

Може да се декларише елемент користећи кључну реч `ANY` у садржају. Најчешће се назива елементом мешовите категорије. Овај сценариоје користан када тек треба да се одлучи о дозвољеном садржају елемента.

Синтакса декларисања елемената са било којим садржајем је следећа:

```xml
<!ELEMENT imelementa ANY>
```

Овде кључна реч `ANY` означава да се текст `PCDATA` и / или било који елементи декларисани у DTD-у могу користити у садржају елемента `imelementa`. Oни се могу користити у било ком редоследу било који број пута. Међутим, кључна реч `ANY` не дозвољава да се укључе елементи који нису декларисани у DTD-у.

**Пример.** Једноставан пример који демонстрира декларацију елемента са било којим садржајем:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresа ANY>
]>

<adresа>
   ovde ime nešto malo nekakvog teksta
</adresа>


&#9608;

### DTD Атрибути

У овом поглављу ћемо размотрити DTD атрибуте. Атрибут даје више информација о елементу или тачније дефинише својство елемента. SGML атрибут је увек у облику пара име-вредност. Елемент може имати било који број јединствених атрибута.

Декларација атрибута је по много чему слична декларацијама елемената, осим што се, уместо декларисања дозвољениог садржаја за елементе, декларише листа дозвољених атрибута за сваки елемент. Ове листе се називају `ATTLIST` декларација.

Основна синтакса декларације DTD атрибута је следећа:

```xml
<!ATTLIST ime_elementa ime_atributa tip_atributa vrednost-atributa>
```

У претходној синтакси DTD атрибути почињу са кључном речи `<!ATTLIST` ако елемент садржи атрибут, `ime_elementa` специфицира име елемента на који се атрибут односи, `ime_atributa` одређује име атрибута који је укључен у `ime_elementa`, а
`tip_atributa` дефинише врсту атрибута, а `vrednost-atributa` узима фиксну вредност коју атрибути морају дефинисати. Типови и вредности атрибута ће бити детаљније разматрани у наредним секцијама.

**Пример.** Једноставан пример који демонстрира декларацију атрибута у DTD:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa ( ime )>
   <!ELEMENT ime ( #PCDATA )>
   <!ATTLIST ime id CDATA #REQUIRED>
]>

<adresa>
   <ime id = "123">Marko Kraljević</ime>
</adresa>
```

У разматрању горњиег примера, концентришемо се на тело DTD-а. Овде смо прогласили елемент и атрибут:

```xml
<!ELEMENT adresa ( ime )>
<!ELEMENT ime ( #PCDATA )>
```

Атрибут `id` за елеменат `ime` је дефинисан као што је дато у наставку (овде је тип атрибута `CDATA` и његова вредност је `#REQUIRED`):

```xml
<!ATTLIST ime id CDATA #REQUIRED>
```

&#9608;

Сви атрибути који се користе у SGML документу морају бити декларисани у дефиницији типа документа (DTD) помоћу изјаве о листи атрибута.

Атрибути се могу појавити само у почетним етикетама или празним етикетама.

Кључна реч `АТТЛИСТ` мора бити написана свим великим словима.

Унутар листе атрибута за дати елемент није дозвољена поновљена имена атрибута.

#### Врсте атрибута

Приликом декларисања атрибута треба одредити како процесор треба да обрађује податке који се појављују у вредности. Врсте атрибута можемо категорисати у три главне категорије:

- Ниска типови

- Токенизовани типови

- Енумерисани типови

Следи резиме различитих типова атрибута:

1. CDATA - представља текстуалне податке (без обележавања). Спада у категорију ниска типова.

2. ID - јединствени идентификатор атрибута. Не би требало да се појави више од једном. ID је токенизовани тип атрибута.

3. IDREF -користи се за рферисање на идентификатор другог елемента. На тај начин се успоставља веза између елемената. IDREF је токенизовани тип атрибута.

4. IDREFS - користи се за реферисње на више идентификатора. IDREFS је токенизовани тип атрибута.

5. ENTITY - представља спољни ентитет у документу. ENTITY је токенизовани тип атрибута.

6. ENTITIES - представља листу спољних ентитета у документу. ENTITIES је токенизовани тип атрибута.

7. NMTOKEN - сличан је CDATA типу атрибута, при чему се вредност атрибута састоји се од важећег SGML имена. NMTOKEN је токенизовани тип атрибута.

8. NMTOKENS - сличан је CDATA типу атрибута, при чему атрибута садржи листу важећих SGML имена. NMTOKENS је токенизовани тип атрибута.

9. NOTATION - елемент ће бити упућен на нотацију декларисану у DTD документу. NOTATION је енумерисани тип атрибута.

10. Enumeration - омогућава дефинисање одређене листе вредности где се вредност аатрибута мора поклопити са једном од набројаних вредности. То је је енумерисани тип атрибута.

#### Вредности атрибута

Унутар сваке декларације атрибута мора се навести како ће се вредност појавити у документу. Дакле, треба одредити да ли атрибут:

- може имати подразумевану вредност

- може имати фиксну вредност

- је захтевам

- jе имплицитан

##### Подразумеване вредности

Садржи подразумевану вредност. Вредности се могу затворити у појединачне наводнике (`'`) или двоструке наводнике (`"`).

Следи синтакса deklaracije atributa :

```xml
<!ATTLIST ime_elementa ime_atributa tip_atributa "podrazumevana-vrednost">
```

Овде је `podrazumevana-vrednost` дефинисана вредност атрибута.

**Пример.** Следи једноставан пример декларације атрибута са подразумеваном вредношћу:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa ( ime )>
   <!ELEMENT ime ( #PCDATA )>
   <!ATTLIST ime id CDATA "0">
]>

<adresa>
   <ime id = "123">
      Tanmay Patil
   </ime>
</adresa>
```

У овом примеру елемент `ime` је са атрибутом `id` чија је подразумевана вредност `0`. Подразумевана вредност је записана унутар наводника. &#9608;

##### Фиксне вредности

Кључна реч `#FIXED` праћена фиксном вредношћу користи се када треба да се одреди да је вредност атрибута константна и да се не може променити. Уобичајена употреба фиксних атрибута је одређивање бројева верзија.

Следи синтакса фиксних вредности:

```xml
<!ATTLIST ime_elementa ime_atributa tip_atributa  #FIXED "vrednost" >
```

где је фиксирана вредност дефинисане вредности атрибута.

**Пример.** Следи једноставан пример декларације атрибута са фиксном вредношћу:

```xml
<!DOCTYPE adresa [
  <!ELEMENT adresa (kompanija)*>
  <!ELEMENT kompanija (#PCDATA)>
  <!ATTLIST kompanija ime NMTOKEN #FIXED "matf">
]>

<adresa>
  <kompanija ime = "matf">mi smo mnog jaki!</kompanija>
</adresa>
```

У овом примеру је коришћена и кључна реч `#FIXED` где означава да је вредност `"matf"` једина вредност за име атрибута елемента `<kompanija>`. Ако се покуша са променом вредности атрибута, добиће се грешка, односно документ више неће бити валидан.

Следи садржај документа заснованог на истом DTD-у који није валидан:

```xml
<!DOCTYPE adresa [
  <!ELEMENT adresa (kompanija)*>
  <!ELEMENT kompanija (#PCDATA)>
  <!ATTLIST kompanija ime NMTOKEN #FIXED "matf">
]>

<adresa>
  <kompanija ime = "abc">ovo smo mi!</kompanija>
</adresa>
```

&#9608;

##### Захтеване вредности

Кад год треба да се наведе да је атрибут неопходан, користи се кључна реч `#REQUIRED`.

Следи синтакса декларације:

```xml
<!ATTLIST ime_elementa ime_atributa tip_atributa #REQUIRED>
```

**Пример.** Једноставан пример декларације DTD атрибута са кључном речи `#REQUIRED`:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa ( ime )>
   <!ELEMENT ime ( #PCDATA )>
   <!ATTLIST ime id CDATA #REQUIRED>
]>

<adresa>
   <ime id = "123">
      Tanmay Patil
   </ime>
</adresa>
```

У овом примеру је коришћена кључна реч `#REQUIRED` да би се навело да атрибут `id` мора бити обезбеђен за елеменат `ime`. &#9608;

##### Имплицитне вредности

Приликом декларисања атрибута увек се мора навести декларацију вредности. Ако атрибут који се декларише нема подразумевану вредност, нема фиксну вредност и није потребан, тада атрибут морате прогласити имплицитним. Кључна реч `#IMPLIED` користи се за одређивање да је атрибут имплицитан.

Следи синтакса такве декларације:

```xml
<!ATTLIST ime_elementa ime_atributa tip_atributa #IMPLIED>
```

Овде је дефинисани `tip_atributa` имплицитан.

**Пример.** Следи једноставан пример декларације атрибута са имплицитном вредношћу:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa ( ime )>
   <!ELEMENT ime ( #PCDATA )>
   <!ATTLIST ime id CDATA #IMPLIED>
]>

<adresa>
   <ime />
</adresa>
```

У овом примеру је коришћена кључну реч `#IMPLIED` јер нисмо желели да наведемо било какве атрибуте који ће бити укључени у име елемента. &#9608;

### DTD Ентитети

Ентитети се користе за дефинисање пречица до посебних знакова у SGML документима. Ентитети могу бити првенствено четири врсте:

- Уграђени ентитети

- Знаковни ентитети

- Општи ентитети

- Параметарски ентитети

Генерално, ентитети се могу декларисати интерно или екстерно, па се у складу са тим називају унутрашњи или спољашњи.

#### Унутрашњи ентитет

Ако је ентитет декларисан у DTD-у, он се назива унутрашњим ентитетом.

Следи синтакса за интерну декларацију ентитета:

```xml
<!ENTITY ime_entiteta "vrednost_entiteta">
```

У овој синтакси `ime_entiteta` је име ентитета праћено његовом вредношћу у двоструким наводницима или појединачним наводницима, док `vrednost_entiteta` садржи вредност за име ентитета.

На вредност ентитета код унутрашњег ентитета уклања се референца додавањем префикса `&` имену ентитета.

**Пример.** Једноставан пример за интерну декларацију ентитета:

```xml
<!DOCTYPE adresa [
   <!ELEMENT adresa (#PCDATA)>
   <!ENTITY ime "Vuk Mandušić">
   <!ENTITY kompanija "Epika">
   <!ENTITY phone_no "(011) 123-4567">
]>

<adresa>
   &ime;
   &kompanija;
   &phone_no;
</adresa>
```

У горњем примеру, одговарајућа имена ентитета `ime`, `kompanija` и `phone_no` замењени су њиховим вредностима у SGML документу. Вредности ентитета се добијају додавањем префикса `&` на име ентитета. &#9608;

#### Спољашњи ентитет

Ако је ентитет декларисан изван DTD-а, он се назива спољашњим ентитетом. Може се реферисати на спољни ентитет коришћењем системских идентификатора или јавних идентификатора.

Следи синтакса за екстерну декларацију ентитета:

```xml
<!ENTITY ime_entiteta SYSTEM "URI/URL">
```

У горњоем опису `ime_entiteta` је назив ентитета, `SYSTEM` је кључна реч, `"URI/URL"` је адреса спољног извора затворена унутар двоструких или појединачних наводника.
