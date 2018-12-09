
# УВИТ - Програмски језик ЈаваСкрипт

[Владимир Филиповић](https://vladofilipovic.github.io/index-cy.html){:target="_blank"}

## Увод

Материјал курса који се однси на јазик ЈаваСкрипт је иyложен уз претпоставку да је слушалац овладао основним и напредним концептима програмирања у програмском језику C. Ако то није случај, слушалац се упућује на обимнију и једноставнију [литературу](../RESURSI-ZA-UCENJE.md#књиге-и-упутства-за-јаваскрипт){:target="_blank"}.

Програмски језик **ЈаваСкрипт** је један од најпопуларнијих програмских језика на свету. Креиран је пре двадесетак година и прошао је дугачак пут од својих скромних почетака.

Програмски језик ЈаваСкрипт је први и једини скрипт-језик који директно подржавају прегедачи веба (web browsers).

На самом свом почетку, он није ни изблиза био тако моћан као што је то сада случај - највише се користио за креирање богатих анимација 😆 и чудеса која су у то време била позната као Динамички HTML (DHTML).

Са порастом захтева које је постављао веб као платформа, повећавала се потреба да се развија и да расте програмски језик ЈаваСкрипт, како би се прилагођавао потребама једног од најшире коришћених информатичких екосистема на свету.

Дакле, како су се уводиле нове ствари на веб платформи, са API-јима прегледача, тако је растао и усавршавао се програмски језик.

Сада се ЈаваСкрипт често и интензивно користи и ван прегледача веба. Развој платформе **Node.js**, која је нарочито постала популарна у последњих неколико година, омогућио је да се овај језик користи и за развој на серверској страни, шта је донедавно био ексклузивни домен традиционалних серверских прогамских језика, као што су: Јава, Руби,  C#, PHP, итд.

Уз програмски језик ЈаваСкрипт се сада лако могу користити базе података и бројне друге апликације. Чак је могуће користити ЈаваСкрипт за развој уметнутих (embedded) и мобилних апликација, апликација за паметне телевизоре итд. Језик, који је свој живот почео као мали језик који се извршава у прегледачу данас представља један од најпопуларнијих програмских језика.

## Карактеристике језика ЈаваСкрипт

Програмски јетик ЈаваСкрипт има следеће карактеристике:

- **Језик вискокг нивоа**: Обезбеђује апстракције које програмеру дозвољавају да игнорише детаље рачунара на коме се скрипт извршава. Даље, управљање меморијом је аутоматизовано коришчењем сакупљача отпадака (garbage collector), па се програмер може концентрисати на сам програмски код, уместо да се брине о мемориским локацијама. Последње, али не најмање важно је то што језик обезбеђује бројне конструкције које програмеру омогућавају да рукује моћним променљивима, објектима и функцијама.

- **Динамичан**: Програми написани на динамичким програмским језицима че приликом извршавања реализовати многе ствари које програми написани на статичким програмским језицима реализују током превођења. такав приступ има бројне предности и мане, а њиме се обезбеђују и оћне каракеритике као што су: димамичкa типизaција (dynamic typing), касно повезивање (late binding), рефлексија, функционално програмирање, промена структуре објекта током извршавања, затворења итд..

- **Динамички типизиран**: Променљива не утиче на тип. Програмер може доделити променљивој вредност ма ког типа, нпр. променљивој која је претходно садржавала целобројну вредност се може доделити ниска знакова (string).

- **Слабо типизиран**: За разлику од јако типизиранјих језика, овде тип не утиче на објекат. Дакле, овде објекти нису строго типизирани, чиме је програмеру допуштена већа флексибилност, али нема сигурности типа нити његове провере (то се покушава поправити у језицима TypeScript и Flow).

- **Интерпретиран**: Ово значи да је непотребна фаза превођења програма пре његовог извршавања, као што је то нпр. случај са програмским језиком C. У пракси, прегледачи веба обично (због бољих перформанси) преведу у међукод ЈаваСкрипт пре његовог извршења, али ово превођење је транспарентно и не захтева додатне кораке, тј. додатне акције корисника.

- **Подржава више парадигми**: Сам језик не форсира једну фиксирану парадигму. Програмер може писати ЈаваСкрипт и користити објектно-оријентисану парадигму - и то на два начина: преко прототипа и преко класа (почев од верзије ES6). Даље, програмер може писати ЈаваСкрипт програме коришћењем функционалног програмског стила (где су функције "грађани првог реда"), или коришћењем императивне парадгигме (као што је случај у програмском језику C).

**Напомена.** Осим сличности имена, језик ЈаваСкрипт нема скоро ништа заједничко са језиком Јава, само је сплет околности и пословна политика компанија Sun и Netscape је довео до таквог исхода.

## Типови вредности и изрази

Информација да језик јаваСкрипт нема типова није тачна. Наиме, једној променљивој се могу доделити вредности различитих типова, али вредности које се додљују имају сvој тип.

[Типови](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures){:target="_blank"} у ЈаваСкрипту се деле у две основне групе:

- Примитивни типови

- Објектни типови

### Примитивни типови

Као што има само име каже, примитивни типови су најпростији. Вредности примитивног типа су непроменљиве, тј. немутирајуће. То значи да након стварања и чувања у меморији та вредност на датом месту се више не може мењати.

Вредности примитивног типа се чувају у брзом делу меморије која се назива **стек**. Непромењива природа података примитивног типа и јесте разлог што је за поређење промењивих које садрже примитиван тип вредности, довољно да пореде само вредности.

Тако се приликом додељивања примитивне вредности променљивој, нпр. наредбом `let osoba1 = "Dragoljub"`, врши генерисање вредности `"Dragoljub"`, која заузима одређени простор у меморији и постављање промењиве `osoba1` да реферише (указује) на то где је смештена вредност `"Dragoljub"`.
Даље, приликом додељивања већ постојеће промењиве која реферише на примитвну вредност новој промењивој, нпр. наребом `let osoba2 = osoba1`, врши се заузимање новог места у меморији у које се копира вредност на коју реферише "стара" променљива и поставља се "нова" промењива тако да указује на то ново место у меморији. Одавде је јасно да  да две промењиве из претходних примера `osoba1` и `osoba2` указују на два различита места у меморији, при чему су на оба места смештене исте вредности - ако се промењивој `osoba1` додели неку нову вредност, то неће имати утицаја на промењиву `osoba2`.

Примитивни типови су:

- Бројевни типови (number)

- Ниска тип (string)

- Логички тип (boolean)

- Симбол (symbol - почев од ES2015)

као и два специјална типа:

- `null`

- `undefined`

**Напомена.** За разлику од програмског језика C, где је била допуштена измена садржаја ниске, у језику ЈаваСкрипт ниске су немутирајуће.

Вредности примитивног типа се у литератури често значавају појмом "примитивне вредности".

Сада ћемо се детаљније позабавити примитвним вредностима различитих типова.

#### Бројеви

Ако се посматра интерна репрезентација бројева у језику ЈаваСкрипт, могло би се рећи да постоји један тип за бројеве, тј. да је сваки број у ствари број у покретном зарезу.

Бројевни литерал је број записан у програмском тј. изворном коду - у зависности од тога како је записан, то може бити целобројни литерал или литерал који представља број у покретном зарезу.

Пример (бројевни литерали, тј. записи целих бројева и бројева у покретном зарезу):
<script src="https://gist.github.com/vladofilipovic/407dc62f463fb74f09f984f9220b9795.js"></script>

#### Ниске

Ниска тип представља секвенцу знакова. У изворном коду она се дефинише помоћу ниска-литерала, који је ограничен апострофима или наводницима.

Ниска може садржавати и тзв. ескејп-секвенцу која се интерпретира приликом приказа ниске - нпр. ескејп-секвенца `\n` представља знак за крај линије. Исто као и у програмском језику C, скејп-секвенце починњу обрнутим слешом, тј. знаком `\`. Ове секвенце су корисне нпр. када наводник треба да се нађе у оквиру ниске коју ограничавају наводници, када апостроф треба да се нађе у оквиру ниске коју ограничавају апострофи и сл.

Пример (записи ниски):
<script src="https://gist.github.com/vladofilipovic/2503e9d2952e44c53a985f5aaffcec56.js"></script>

Новији начин записа ниски, назван [шаблон за ниску](#шаблони-за-ниске){:target="_blank"}, где се као ограничење користи обрнути апостороф (тј. знак `\``),  је описан касније, у поглављу о изразима.

#### Логички тип

Податак логичког типа може имати тачно једну од следеће две вредности: тачно (записује са  са `true`) и нетачно (тј.) `false`). Велики број оператора поређења: `==`, `===`, `<>` итд. као резултат враћу логичку вредност.

Наредбе гранања (нпр. [`if` наредба](#наредба-if){:target="_blank"}) и наредбе циклуса (као што је [`while` наредба](#наредба-while){:target="_blank"}) користе логичке вредности да би одредиле даљи ток извршавања програма.

Контролне структуре за гранање и за циклусе нису превише стоге: оне поред чисто логичких података (тј. вредности `true` или  `false`), прихватају и податке других типова који се тумаче (интерпретирају) као тачни или као нетачни.

Вредности које се интерпретирају као нетачне су: `0`, `-0`, `NaN`, `undefined`, `null`, `''` и `""`. Све остале вредности се тумаче као тачне.

#### Специјални тип null

Вредност `null` представља специјану вредност која указује на непостојање (одсуство) вреднпости.

Сличан концепт постоји и у другим програмским језицима, нпр. `null` у језику C#, као и `nil` или `None` у језику Пајтон.

#### Спцеијални тип undefined

Вредност `undefined` указује да променљива још није иницијализована или да недостаје њена вредност.

Уобичајено је да `undefined` буде повратна вредност функције која не враће вредност. Поред тога, ако је приликом позива функције број аргумената у позиву мањи од броја параметара, тада ће на почетку извршавања функције вредност параметара којима није прослеђен аргумент бити `undefined`.

Провера да ли је дата променљива `undefined` се врши тако што се тип променљиве (добијен применом `typeof` оператора) упореди без конверзије типова (тј, применом оператора  `===`) са типом `undefined`.

### Објектни типови

Све што није примитивни тип, то представља објектни тип.

Функције, низови и објекти су примери објектних типова. Свако од њих има своје специфичне карактеристике, али они истовремену наслеђују својства објектног типа - сви они имају [особине](#oсобине-објеката){:target="_blank"} и [методе](#методе-код-објеката){:target="_blank"}.

Вредност објектног (референтог) типа се чувају у делу меморије која се назива **хип**. За разлику од вредности примитивног типа, вредност референтног типа  може да се мења током времена.

Додељивање референтне вредности промењивој извршава исту акцију као и код примитива: вредност заузима место у меморији, а промењиве се поставља тако да указује на то место у меморији. Међутим, додељивње постојеће промењиве новој промењивој не копира ту вредност на ново место у меморији, већ само подеси да "нова "променљива буде преусмерена тако да реферише на то исто "старо" место. Стога ће "стара" и "нова" променљива постати "везане": након вредности једне (било "старе", било "нове" променљиве), долази до промене обе промењиве, јер обе реферишу на исто место у меморији.

Због сложености и важности [функција](#функције-и-затворења){:target="_blank"}, [низова](#низови){:target="_blank"} и [објеката](#објекти){:target="_blank"}, они ће бити обрађени касније, у посебним поглављима.

### Изрази

Изрази су делови програмског кода који могу бити евалуирани и чија се вредност може израчунати.

Иако сваки синтаксно коректан израз приликом евалуације добије неки вредност, у принципу се разлику два типа израза: 

1. изрази са бочним ефектима (нпр. израз којим се променљивој додељује вредност) и

1. изрази су без бочног ефекта.

Конретан пример за први тип израза је `x = 7` - у том случају се користи оператор доделе вредности `=` да би се вредност седам доделила променљивој `x`. У том случају, целокупном изразу ће приликом евалуације бити додељена бројчана вредност седам.  

Конкретан пример за други тип израза је `3 + 4` - у том случају се користи оператор `+` како би се сабрали тројка и четворка и добила вредност седам, али тај резултат не бива додљен променљивој.

Постоје различите категорије израза:

- Примарни изрази: основне кључне речи и најједноставнији изрази у ЈаваСкрипту, који представљају основне (тј. примарне) елементе за грађење свих ЈаваСкрипт израза.

- Аритметички изрази: евалуирају се у бројеве (као што су `12` или `3.14157`), обично коришћењем аритметичких оператора.

- Ниска-изрази: евалуирају се у ниску знакова (као што су `"Fred"` или `"234"`), обично коришћењем оператора за рад са нискама-

- Логички изрази: евалуирају се у `true` или `false`, при чему се често користе релациони и логички оператори.

- Изрази леве стране: обично представљају одредиште наредби доделе, тј. налазе се лево од оператора доделе.

#### Примарни изрази

У примарне изразе спадају претходно описани литерали и константе, као и променљиве, које ће бити описане у [поглављу које следи](#променљиве){:target="_blank"}.

У примарне изразе спадају и следеће кључне речи језика ЈаваСкрипт:

- `function`, описане у [следећем поглављу](#дефиниција-и-позив-фуункције){:target="_blank"}

- `class`, описане у [поглављу које следи](#класе){:target="_blank"} 

- `function* //функција генератор`

- `yield //паузира/наставља рад генератора`, описано у [следећем поглављу](JavaScript-Pprogramiranje-Server.md#нардба-yield){:target="_blank"}

- `yield* //делегат дригог генератора или итератора`

- `async function* //асинхрони функционални израз`, описано у [следећем поглављу](JavaScript-Pprogramiranje-Server.md#наредбе-async-и-await){:target="_blank"}

- `await //паузира/наставља/чека завршетак за асинхрону функцију`, описано у [следећем поглављу](JavaScript-Pprogramiranje-Server.md#наредбе-async-и-await){:target="_blank"}

- `/pattern/i //регуларни израз`

- `() // груписање`, описано у [поглављу о операторима](#оператори){:target="_blank"}

#### Аритметички изрази

У ову категорију  спадају сви изрази који се евалуирају у бројеве.

При грађењу аритметичјих израза, користе се аритметички [оператори](#оператори){:target="_blank"} и [функције](#дефиниција-и-позив-фуункције){:target="_blank"} које враћају бројеве.

Пример (операције над бројевима):
<script src="https://gist.github.com/vladofilipovic/e99c66c6dda94f9233b5755b3ae6c750.js"></script>

#### Логички изрази

Логички изрази приликом евалуације враћају вредности логичког типа (`true` или `false`).

Пример (рад са логичким изразима):
<script src="https://gist.github.com/vladofilipovic/e9be15b3154bccb7b5a1498f07afc232.js"></script>

#### Ниска-изрази

Ниска-изрази приликом евалуације враћају вредности знаковних ниски.

Приликом креираљнових ниски, често се користи оператор спајања `+`.

##### Шаблони за ниске

Шаблони за ниске, уведени у верзији ЈаваСкрипта ES2015, су ниска-литерали који допуштају моћнији начин за дефинисање ниски.

Шаблони за ниске су, уместо апострофа или наводаника, ограничени обрнутим апостофом (тј. знаком `` ` ``). У оквиру шаблона за ниске се могу налази места за замену, која су означена тако што су обухваћена витичастим заградама испред којигх се налази знак за долар, нпр. `${izraz}`. У претходном примеру, `izraz` се налази унутар места за замену и он се прослеђује функцији, која врши спајање делова у једну ниску. Функција ће пре спајања у ниску извршити евалуцаију израза у оквиру места за замену и добијене реѕултате спојити у резултујућу ниску.  

Код шаблона за ниске, белине (знаци за крај линије, размаци, табови и сл.) не треба да се представљају промоћу ескејп-знакова, већ се могу директно унети у шаблон. Начин формирања ниски преко шаблона је елегантнији од "класичног" спајања ниски оператором `+` и продукује читљивији програмски код.

Пример (рад са оператором спајања и са шаблонима за ниске):
<script src="https://gist.github.com/vladofilipovic/cae2937af170ff4e2a3bf2e4d89c83fe.js"></script>

Ако се појави потреба да се у оквиру шаблона за ниску појави обрнути апостоф, то се може постићи помоћу одговарајуће ескејп-секвенце, тј. знака ``\```.

#### Изрази леве стране

Ови изрази представљају одредиште наредбе доделе (било директно, било имплицитно). То могу бити:

- [Променљиве](#променљиве){:target="_blank"}

- Изрази за приступање [особинама](#особине-објеката){:target="_blank"}

- Оператор `new`, којим се креира примерак [конструктора](#класе){:target="_blank"}

- Оператор `super`, којим се позива [родитељски конструктор](#класе){:target="_blank"}

- Листе [аргумената](#pараметри-и-аргументи-функција){:target="_blank"}

### Оператори

Под операторима се најчешће подразумева симболи који се користе када треба извршити неку стандардну често коришћену операцију као нпр. додела вредности, поредјење вредности, аритметичке операције и сл.

Приоритет оператора одређује којим ће се редом оперантори примењивати, а асоцијативност оператораодређује са ког краја се одвија груписање операнада (почев од левог или од десног краја). Сваки оператор има свој ниво приоритета и своје  правило асоцијативности.

У наредној табели су приказани оператори и њихова асоцијативност. Редослед оператора у табели је дат по њиховом приоритету - од најважнијег ка мање важним:

<table border="1px">
<tbody>
<tr>
<th>Приоиритет</th>
<th>Ознака </th>
<th>Назив</th>
<th>Асоцијативност</th>
</tr>
<tr>
<td>20</td>
<td><span>( … )</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Grouping"  target="_blank"    title="The grouping operator ( ) controls the precedence of evaluation in expressions."><span>заграде за груписање</span></a></td>
<td>н/д</td>
</tr>
<tr>
<td rowspan="3">19</td>
<td><span>… <strong>.</strong> …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#Dot_notation"  target="_blank"   title="Property accessors provide access to an object's properties by using the dot notation or the bracket notation."><span>приступ особини објекта тачка-нотацијом</span></a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… [ … ]</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#Bracket_notation"  target="_blank"    title="Property accessors provide access to an object's properties by using the dot notation or the bracket notation."><span>приступ особини објекта нотацијом угластих заграда</span></a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>new … ( … )</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/new"  target="_blank"  title="The new operator creates an instance of a user-defined object type or of one of the built-in object types that has a constructor function."><span>new</span></a> (са аргументима)</td>
<td>н/д</td>
</tr>
<tr>
<td rowspan="2">18</td>
<td><span>… (&nbsp;<var>…&nbsp;</var>)</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Guide/Functions" target="_blank" >позив функције</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>new …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/new" target="_blank"   title="The new operator creates an instance of a user-defined object type or of one of the built-in object types that has a constructor function.">оператор <span>new</span></a>&nbsp;(без аргумената)</td>
<td>сдесна улево</td>
</tr>
<tr>
<td rowspan="2">17</td>
<td><span>… ++</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment"    target="_blank"  title="Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/)."><span>постфиксно увећавање</span></a></td>
<td>н/д</td>
</tr>
<tr>
<td><span>… &#8212;</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Decrement"    target="_blank"  title="Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/)."><span>постфиксно умањивање</span></a></td>
<td>н/д</td>
</tr>
<tr>
<td rowspan="9">16</td>
<td><span>! …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_NOT"  target="_blank" >логичка негација</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>~ …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_NOT" target="_blank" >битовна негација</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>+ …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus" target="_blank" >унарни плус</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>&#8211; …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_negation" target="_blank" >унарни минус</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>++ …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment" target="_blank" >префиксно увећање</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>&#8212; …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Decrement" target="_blank" >префиксно умањење</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>typeof …</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/typeof" target="_blank" >typeof</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>void …</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/void" target="_blank" >void</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>delete …</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/delete" target="_blank" >delete</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td>15</td>
<td><span>… ** …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Exponentiation" target="_blank" >степеновање</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td rowspan="3">14</td>
<td><span>… *&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Multiplication" target="_blank" >множење</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… /&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Division" target="_blank" >дељење</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… %&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder" target="_blank" >остатак при дељењу</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td rowspan="2">13</td>
<td><span>… +&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Addition" target="_blank" >сабирање</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &#8211;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Subtraction" target="_blank" >одузимање</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td rowspan="3">12</td>
<td><span>… &lt;&lt;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators" target="_blank" >битовно померање улево</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &gt;&gt;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators" target="_blank" >битовно померање удесно</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &gt;&gt;&gt;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators" target="_blank" >битовно неозначено померање удесно</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td rowspan="6">11</td>
<td><span>… &lt;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Less_than_operator" target="_blank" >мањи</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &lt;=&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Less_than__or_equal_operator" target="_blank" >мањи или једнак</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &gt;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Greater_than_operator" target="_blank" >већи</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… &gt;=&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Greater_than_or_equal_operator" target="_blank" >већи или једнак</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… in&nbsp;…</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/in" target="_blank" >in</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… instanceof&nbsp;…</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/instanceof" target="_blank" >instanceof</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td rowspan="4">10</td>
<td><span>… ==&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Equality" target="_blank" >једнакост</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… !=&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Inequality" target="_blank" >различитост</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… ===&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Identity" target="_blank" >идентичност</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td><span>… !==&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Nonidentity" target="_blank" >неидентичност</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>9</td>
<td><span>… &amp;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_AND" target="_blank" >битовна конјукција</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>8</td>
<td><span>… ^&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_XOR" target="_blank" >битовна ексклузивна дисјункција</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>7</td>
<td><span>… |&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_OR" target="_blank" >битовна дисјункција</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>6</td>
<td><span>… &amp;&amp;&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_AND" target="_blank" >логичка конјукција</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>5</td>
<td><span>… ||&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_OR" target="_blank" >логичка дисјункција</a></td>
<td>слева удесно</td>
</tr>
<tr>
<td>4</td>
<td><span>… ? … : …</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator" target="_blank" >условни израз</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td rowspan="13">3</td>
<td><span>… =&nbsp;…</span></td>
<td rowspan="13"><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators" target="_blank" >додела</a></td>
<td rowspan="13">сдесна улево</td>
</tr>
<tr>
<td><span>… +=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… -=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… **=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… *=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… /=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… %=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… &lt;&lt;=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… &gt;&gt;=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… &gt;&gt;&gt;=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… &amp;=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… ^=&nbsp;…</span></td>
</tr>
<tr>
<td><span>… |=&nbsp;…</span></td>
</tr>
<tr>
<td rowspan="2">2</td>
<td><span>yield&nbsp;…</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/yield" target="_blank" >yield</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td><span>yield*&nbsp;…</span></td>
<td>оператор <a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/yield*" target="_blank">yield*</a></td>
<td>сдесна улево</td>
</tr>
<tr>
<td>1</td>
<td><span>&#8230;</span>&nbsp;…</td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator" target="_blank" >проширење</a></td>
<td>н/д</td>
</tr>
<tr>
<td>0</td>
<td><span>… ,&nbsp;…</span></td>
<td><a href="https://developer.mozilla.org//en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator" target="_blank" >зарез/секвенца</a></td>
<td>слева удесно</td>
</tr>
</tbody>
</table>

Пример (коришћење унарних и бинарних оператора):
<script src="https://gist.github.com/vladofilipovic/29ed64ecbbabcf1730fa5710ff5e64cb.js"></script>

### Конверзија типова и евалуација израза

ЈаваСкрипт је слабо  типизиран језик, што значи да не захтева да се јасно декларише тип при декларисању промењиве. Код ЈаваСкрипта се тип промењиве имплицитно декларише са придруживањем одређене вредности датој промењивој.

ЈаваСкрипт је такође језик динамичких типова јер је могућа промена типа у току извршења програма. Резултат конверзије је увек нека примитивна вредност, тј. не постоји конверзија чији је резултат нека сложена вредност (као што је објекат или функција).

#### Експлицитна конверзија типа

Када треба променити тип података неке промењиве то се зове експлицитна конверзија типова и врши се користећи неку од уграђених функција за конверзију:

- Конвертовање у ниску: `String()` или `toString()`

- Конвертовање у број: `Number()` или `parseFloat()` или `parseInt`()`

- Конвертовање у логичку вредност: `Boolean()`

#### Имплицитна конверзија типа

Имплицитна  конверзија типова се односи на конверзије које нису експлицитне а извшава их ЈаваСкрипт извршно окружење у ходу као споредни ефекат неких других радњи. Имплицитна конверзија се најчешће јавља када се вредност неког типа користи на начин који аутоматски проузрокује њену конверзију.

Следи табела имплицитних конверзија:

| Оригиналna вредност | Конверзија у `Number` | Конверзија у `String` | Конверзија у `Boolean` |
|:-------------------:|:-------------------:|:-------------------:|:--------------------:|
|`false`|`0 `|`“false”`|`false`|
|:-------------------:|:-------------------:|:-------------------:|:--------------------:|
|`true`|`1`|`“true”`|`true`|
|`0`|`0`|`“0”`|`false`|
|`1`|`1`|`“1”`|`true`|
|`“0”`|`0`|`“0”`|`true`|
|`“000”`|`0`|`“000”`|`true`|
|`“1”`|`1`|`“1”`|`true`|
|`NaN`|`NaN`|`“NaN”`|`false`|
|`Infinity`|`Infinity`|`“Infinity”`|`true`|
|`-Infinity`|`-Infinity`|`“-Infinity”`|`true`|
|`“”`|`0`|`“”`|`false`|
|`“20”`|`20`|`“20”`|`true`|
|`“twenty”`|`NaN`|`“twenty”`|`true`|
|`[]`|`0`|`“”`|`true`|
|`[20]`|`20`|`“20”`|`true`|
|`[10,20]`|`NaN`|`“10,20”`|`true`|
|`[“twenty”]`|`NaN`|`“twenty”`|`true`|
|`[“ten”,”twenty”]`|`NaN`|`“ten,twenty”`|`true`|
|`function(){}`|`NaN`|`“function(){}”`|`true`|
|`{}`|`NaN`|`“[object Object]”`|`true`|
|`null`|`0`|`“null”`|`false`|
|`undefined`|`NaN`|`“undefined”`|`false`|

Најчешће су разлози за имплицитну конверзију поређење или нека друга математичка операција између различитих типова промењивих. Поред овога имплицитна конверзија се дешава и услед потребе за израчунавањем неког услова.

#### Евалуација израза уз имплицитну конверзију

Следи неколико типова евалуација које садрже имплицитну конверзију а које се често јављају:

##### Поређење помоћу оператора ==

Један од најпознатијих примера имплицитне конверзије је “поређење прама једнакости”, након чега се добија логичка вредност. Алгоритам за одређивање логичке вредности која представља резултат поређења тј. `x == y` је следећи:

1. Ако су `x` и `y` истог типа, тада се извршава стриктно поредјење `===`

1. Ако је промењива `x` `null` или `undefined`, тада се враћа `true`

1. Ако је промењива `x` `undefined` а промењива `y` `null`, тада се враћа `true`

1. Ако је промењива `x` `Number` а промењива `y` `String`, онда враћа резултат поређења `x = ТоNumber(y)`

1. Ако је промењива `x` `String` а промењива `y` `Number`, онда враћа резултат поређења `ТоNumber(x) = y`

1. Ако је промењива `x` `Boolean` а промењива `y` `Number`, онда враћа резултат поређења `ТоNumber(x) = y`

1. Ако је промењива `x` `Number` а промењива `y` `Boolean`, онда враћа резултат поређења `x = ТоNumber(y)`

1. Ако је промењива `x` `Number` или `String` или `Symbol` а промењива `y` `Object`, онда враћа резултат поређења `x = ToPrimitive(y)`

1. Ако је промењива `x` `Object` а промењива `y` `Number` или `String` или `Symbol`, онда враћа резултат поређења `ToPrimitive(x) = y`

1. Ако није ништа од претходно наведеног, тада се враћа `False`

У следећој табели су уписани сви случајеви између свих могућих типова за поређење оператором `==`:
<table border="1px">
<thead>
<tr>
<th scope="row">&nbsp;</th>
<th style="text-align: center;" scope="col" colspan="7">Operand B</th>
</tr>
</thead>
<tbody>
<tr>
<th scope="row">&nbsp;</th>
<td>&nbsp;</td>
<td style="text-align: center;">`Undefined`</td>
<td style="text-align: center;">`Null`</td>
<td style="text-align: center;">`Number`</td>
<td style="text-align: center;">`String`</td>
<td style="text-align: center;">`Boolean`</td>
<td style="text-align: center;">`Object`</td>
</tr>
<tr>
<th scope="row" rowspan="6" colspan="1">Operand A</th>
<td>Undefined</td>
<td style="text-align: center;"><span>`true`</span></td>
<td style="text-align: center;"><span>`true`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
</tr>
<tr>
<td>Null</td>
<td style="text-align: center;"><span>`true`</span></td>
<td style="text-align: center;"><span>`true`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
</tr>
<tr>
<td>Number</td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`A === B`</span></td>
<td style="text-align: center;"><span>`A === ToNumber(B)`</span></td>
<td style="text-align: center;"><span>`A === ToNumber(B)`</span></td>
<td style="text-align: center;"><span>`A == ToPrimitive(B)`</span></td>
</tr>
<tr>
<td>String</td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>ToNumber(A) === B</span></td>
<td style="text-align: center;"><span>`A === B`</span></td>
<td style="text-align: center;"><span>`ToNumber(A) === ToNumber(B)`</span></td>
<td style="text-align: center;"><span>`A == ToPrimitive(B)`</span></td>
</tr>
<tr>
<td>Boolean</td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`ToNumber(A) === B`</span></td>
<td style="text-align: center;"><span>`ToNumber(A) === ToNumber(B)`</span></td>
<td style="text-align: center;"><span>`A === B`</span></td>
<td style="text-align: center;"><span>`ToNumber(A) == ToPrimitive(B)`</span></td>
</tr>
<tr>
<td>Object</td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`false`</span></td>
<td style="text-align: center;"><span>`ToPrimitive(A) == B`</span></td>
<td style="text-align: center;"><span>`ToPrimitive(A) == B`</span></td>
<td style="text-align: center;"><span>`ToPrimitive(A) == ToNumber(B)`</span></td>
<td style="text-align: center;"><span>`A === B`</span></td>
</tr>
</tbody>
</table>

Пример (евалуација израза уз имлицитну конверзију типова):
<script src="https://gist.github.com/vladofilipovic/f3c52c66c729dc00b4357a85fcd6c8a0.js"></script>

### [Примери за типове вредности  и изразе](https://github.com/MatfUVIT/UVIT/tree/master/predavanja/primeri-js/p01-js-vrednosti-tipovi-operatori){:target="_blank"}

## Структура ЈаваСкрипт програма

### Лексичка структура језика

#### Unicode знаци

#### Тачка-зарез

#### Белине

#### Разликовање великих и малих слова

#### Коментари

#### Литерали и идентификатори

#### Кључне речи

Кључне речи су:

`break`
`do`
`instanceof`
`typeof`
`case`
`else`
`new`
`var`
`catch`
`finally`
`return`
`void`
`continue`
`for`
`switch`
`while`
`debugger`
`function`
`this`
`with`
`default`
`if`
`throw`
`delete`
`in`
`try`
`class`
`enum`
`extends`
`super`
`const`
`export`
`import`
`implements`
`let`
`private`
`public`
`interface`
`package`
`protected`
`static`
`yield`

### Променљиве

Променљиве су именоване локације у меморији у којима могу да се чувају подаци. Вредност променљиве може да се мења за време извршавања програма, па отуда и назив променљива.

Имена променљивих у ЈаваСкрипту се могу састојати од произвољне комбинације слова и бројева, али постоје нека правила:

- Први знак мора бити слово алфабета или подвлака (знак `_`).

- Резервисане речи не могу се користити као име променљиве.

- Велика и мала слова се разликују, уобичајено је да се променљиве пишу малим словима.

Декларисање и дефинисање промењиве су два различита поступка. Декларација промењиве је поступак стварања промењиве, тада се дефинише име промењиве и обезбедјује простор за њено складиштење, док је дефинисање промењиве поступак када се промењивој додељује нека вредност која се смешта у простор за складиштење.

Пример (променљиве):
<script src="https://gist.github.com/vladofilipovic/9fec667cf7b180511a5b48ae0e1cbfb0.js"></script>

#### Опсег дефинисаности и контексти

Појам **опсеги дефинисаности** промењиве (scope) је везан за појам промењиве и представља део програмског кода у којој је нека промењива доступна. Основна карактеристика опсега дефинисаности је граница тог опсега. Промењивој се може приступити само из њеног опсега дефинисаности тј. не може се приступити промењивој уколико се налазимо извршава код изван опсега дефинисаности те променљиве.

Према **времену дефинисања**, опсези дефинисаности се могу поделити на:

- Статички (лексички) опсег дефинисаности - дефинише се у тренутку превођења, тако да функција тада запамти референце на које указују промењиве у ланцу лексичких опсега (тзв. “рано везивање”). Лексички опсег директно зависи од места где је декларисана промењива у самом програмском коду, па се може закључити да се овај тип опсега промењиве се дефинише у тренутку писању кода. Сходно томе, овај опсег се не може мењати током времена (осим самим мењањем кода), па се зато још зове и статички опсег дефинисаности.

- Динамички опсег дефинисаности - дефинише се у време извршавања кода, па се везује за референце на које указују промењиве у том тренутку када се извршава код (тзв. “касно везивање”). Код програмских језика које користе динамички опсег, након потраге за промењивом у оквиру матичне функције, креће потрага за промењивом у функцији која је позвала матичну функцију, итд.

Према **величини**, опсези дефинисаности се могу поделити на:

- Локални опсег дефинисаности - све до верзије ЕС6 у ЈаваСкрипта, локалну опсег је било могуће направити искључиво коришћењем функције (што је сматрано једном од највећих мана самог језика). Новом ревизијом језика “ЕС6” је омогућено дефинисање локалног тзв. блоковског опсега дефинисаности уз помоћ резервисане речи `let`.

  - Функцијски опсег дефинисаности - када се промењива декларише унутар функције, за њу се дефинише локални опсег дефинисаности који се још зове “функцијска опсег“. Локална промењива функције и њен функцијски опсег дефинисаности постоје само током извршсвања функције.

  - Блоковски опсег дефинисаности - уведена у ЕС 6 је, где нова кључна реч `let` омогућује декларацију промењиве унутар блока кода и самим тим дефинише локални блоковски опсег дефинисаности. Једна од битних карактеристика креирања блоковског опсега дефинисаности са кључном речи `let` је да се при томе не врши померање декларација променљивих на врх тј. на почетак блока у коме су оне декларисане.

- Глобални опсег дефинисаности - свака промењива која није дефинисана у оквиру функције припада глобалном опсегу, а то значи да је промењива доступна свим деловима програма. Уколико се промењива не декларише, она ће постати глобална па чак и ако је дефинисана (тј. додељена јој је вредност) унутар функције. Најешће се глобална промењива креира грешком, па је препорука да се користи стриктни мод (активира се са `use strict`) који при креирању глобалне промењиве пријавлљује грешку.

Треба напоменути да опсег дефинисаности  није исто што и **окружење** тј. **контекст**. Ова два појма се јер имају неке сличности али треба знати да је појам опсег дефинисаности је особина промењиве, док је контекст особина програмског кода.

Када се програм покрене, окружење није празно - оно већ садржи променљиве које су део језичког стандарда, као и променљиве које обезбеђују начин интеракције програма са системом који га окружује. Током извршавања, програм пролази (улази и излази) кроз различите опсеге дефинисаности промењиве, а промењиве су тада или у контексту или ван њега.

Контекст је сличан опсегу дефинисаности јер такође зависи од позиције у програму (лексички контекст) или времена извршавања кода (контекст извршавања).

Опсези дефинисаности и контексти ће бити додатно описани приликом описивања функција у ЈаваСкрипту.

#### Дизање променљиве

Приликом извршавања ЈаваСкрипт кода, пре извршења наредби у коду се прво декларишу промењиве. У оквиру ЈаваСкрипта постоји специјална резервисана реч `var` која се користи за декларацију промењиве. Пошто се декларација промењиве дешава пре извршавања било ког дела кода, декларисање променљиве било где у коду има исти ефекат као да је та промењива декларисана на почетку кода - овај принцип се назива "дизање" (hoisting). Дакле, у случају када се  реферише на нека промењиву у делу кода који претходи њеној декларацији неће бити избачена грешка али вредност те промењиве неће бити дефинисана.

Уколико се не користи резервисана реч `var`, промењива ће бити декларисана "у лету" у глобалном опсегу дефинисаности и биће доступна из целог програмског кода. Ова радња се изводи тек у време извршавања кода, што наступа након тренутка када се извршава “дизање” промењивих на врх кода. Пошто је прошао тренутак када се врши дизање, та промењива неће бити дигнута на почетак кода. Стога, уколико се реферише на такву промењива пре њенњ појаве у коду,биће избачена грешка!

### Наредбе и секвенце наредби

Пример (наредбе са мало смисла):
<script src="https://gist.github.com/vladofilipovic/d5c9153e65dcfacfeea5a63a927232ad.js"></script>

Пример (смислена секвенца наредби):
<script src="https://gist.github.com/vladofilipovic/4f0ecd4395c6bab9499cff73e765bca5.js"></script>

#### Наредбе доделе вредности

#### Наредбе сажетог ажурирања

Ове наредбе се још називају и комбиноване наредбе доделе.

#### Позиви функција

Пример (позив функције за приказ на конзолу):
<script src="https://gist.github.com/vladofilipovic/4e183bd2b858ac5c6d0171a8c00407d8.js"></script>

Пример (позиви математичких функција):
<script src="https://gist.github.com/vladofilipovic/4c458e2adeb128fd5c437254a1519d7c.js"></script>

Пример (секвенца генерисања псеудо-случајних бројева):
<script src="https://gist.github.com/vladofilipovic/3766d6e8d4b18ea6c7ef1901b4e16e11.js"></script>

### Гранања

#### Наредба if

Пример (наредба `if`):
<script src="https://gist.github.com/vladofilipovic/76d3387a5bbce192fa71e3a0a7f48d26.js"></script>

Пример (наредба `if`-`else`):
<script src="https://gist.github.com/vladofilipovic/330e49ee301b349ef2ad74cd5e1ad0b1.js"></script>

Пример (угнеждена наредба `if`-`else`):
<script src="https://gist.github.com/vladofilipovic/bcf0528d97685d1c55fd75e2bd336707.js"></script>

#### Наредба switch

Пример (наредба `switch`-`case`):
<script src="https://gist.github.com/vladofilipovic/9d72bd2ec560597498baf59e725f3694.js"></script>

### Циклуси

Често се јавља потреба да се унутар програма неке наредбе извршавају више пута. Овај начин извршавања се остварају помоћу одговарајућих управљачких структура. Циклуси и итерације су основни градивни елемент сваког програма. Стандардни циклуси се јављају мање-више у истом облику у скоро свим програмским језицима. У овом поглављу ће се описати само циклуси, а итерације че бити описнане у посебномј секцији, после описа низова, објеката и функција.

#### Циклус while

Пример (наредба `while`):
<script src="https://gist.github.com/vladofilipovic/e2de7b756dbf81e3c56797b2d5b86880.js"></script>

#### Наредба do - while

Пример (наредба  `do`-`while`):
<script src="https://gist.github.com/vladofilipovic/653c0ad937424672cb298c88334775e7.js"></script>

#### Наредба for

Пример (наредба  `for`):
<script src="https://gist.github.com/vladofilipovic/431715c98284ddf6120be93d2b59daf2.js"></script>

#### Искакање из циклуса

Пример (наредба  `for`-`break`):
<script src="https://gist.github.com/vladofilipovic/10cd5f3e4391763dbcf94232050b64b0.js"></script>

Пример (циклуси и сажето ажурирање):
<script src="https://gist.github.com/vladofilipovic/5026b3648df928050f821022bd017227.js"></script>

#### Прескакање итерације циклуса

#### Обележена искакање иа циклуса и прескакање итерације

#### Циклуси и опсези важења

## Функције и затворења

### Дефиниција и позив фуункције

### Параметри и аргументи функција

#### Опциони параметри функција

### Декларација функције

### Опсези важења за променљиве и функције

#### Стек позива за функције

### Затворења за функције

#### Рекурзивне функције

### Ламбда-функције

## Низови и објекти

### Низови

#### Низови и функције

### Објекти

#### Особине објеката

#### Методи код објеката

#### Сложени објекти и функције

## Функције вишег реда

### Функције вишег реда и рад са колекцијама

### Мапирање и редукција помоћу функција вишег реда

### Повезивање функција

### Функцијски изрази који се одмах позивају

## Напредни објекти

### Наслеђивање помоћу прототипова

### Класе

### Оператор `this`

### Математички оператори

## Изузетци

## Модули

### ES модули

### CommonJS

## Стриктни мод

## Верзије језика ЈаваСкрипт

### Актуелна ECMAScript верзија

### Динамика појаве нових верзија

### Шта је то TC39

## Стилови кодирања

Стил кодирања за ЈаваСкрипт у ствари представља скуп конвенција које се користе при писању ЈаваСкрипт програма.

Стил кодирања се обично описује као споразум који склапају чланови програмерског тима, како би одржали конзистентност програмског кода у пројекту.

Чак и ако је тим једночлан, опет се стил кодирања може посматрати као споразум који програмер склапа сам са собом, како би програмски код био у складу са сопственим програмеровим стандардима.

Постојање фиксних правила за форматирање програмског кода умногоме помаже да код буде читљивији и лакши за одржавање.

### Популарни стилови кодирања

Поред многобројних постојећих, у овом тренутку су најпопуларнији стилови кодирања описани са следећа два документа:

- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html){:target="_blank"}

- [AirBnb JavaScript Style Guide](https://github.com/airbnb/javascript){:target="_blank"}

Уколико радите на тимском пројекту, добра је пракса да се стил кодирања усагласи на почетку и да се усаглашени документ постави тако да у сваком тренутку  буде доступан свим члановима тима.

### Конвенције кодирања које су коришћене у оквиру овог курса

- У примерима и у опису конструкција биће коришћена актуелна верзија ЈаваСкрипта. Ако буде било потребе да се подрже старији прегледачи веба, биће коришћен алат [Babel](https://github.com/babel/babel){:target="_blank"}.

- Увлачење: користиће се размаци, а не табови, при чему ће нови ниво увлачења бити маркиран са три размака.

- Тачка-запета: ако не мора, неће се користити тачка-запета.

- Дужина линије: ако је могуће. линије програмског кода пресећи тако да не буду дуже од 80 знакова.

- Линијски коментари: у програмском коду користити искључиво линијке коментаре; блоковске коментаре користити искључиво у документационе сврхе.

- Без "мртвог" програмског кода: не остављати искоментарисан стари програмски код, како би, "за сваки случај" он могао бити касније коришћен. У оквиру програмског кода треба да остане сано садржај који је потребан, а ситуације типа "ово ми може требати касније" се решавају помоћу система за контролу верзија и програмерске документације/напомена.

- Коментарисати само када је корисно: не додавати коментаре ако они не доприносе разумевању програмског кода. Ако је коришћењем конвенција кодирања, правилним именовањем променљивих и функција програм и коришћењем [JSDoc](https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler){:target="_blank"} коментара постигнуто да програм буде читљив и само-обашњавајући, тада ге не треба додатно коментарисати.

- Именовање функција, променљивих и метода: називи функција, променљивих и метода увек почињу малим словом тј. при запису се користи тзв. **камиљаНотација**. Једино у случају када се ради о називу означеном са `private`, тада назив почиње подвлаком (тј. знаком _ ), а наставак назва је у складу са камиљомНотацијом.

- Именовање конструкторских функција и класа:  називи конструкторских функције и класа користе тзв. **ПаскалНотацију**. И ту се, слично као код камиље нотације, великом словом сигнализира почетак нове речи у називу - само што назив почиње великим, а не малим словом.

- Именовање датотека: називи датотека треба да буду написани малим словима, при чему ће речи у називу бити раздвојене цртицом (или минусмом, тј. знаком - ).

- Константе: све константе се именују **ВЕЛИКИМ_СЛОВИМА**. У том случају се користи подвлаа (тј. знак _ ) за раздвајање речи унутар имена константе.

- Декларације променљивих: увек треба декларисти променљиве, како би се на тај начин избегло "загађивање" стварањем глобалних објеката. При декларисању проеменљивих не користити `var`. Препоручује се коришћењњ `const` за декларацију променљиве, а `let` трба користити само у случају када ће променљивој бити мењана вредност после инцијален доделе.

- Beline: белине треба паметно користити ради повећања читљивости програмског кода. На пример, поставити размак иза кључне речи иза које следе отворена заграда; поставити размак пре и после бинарних операција (`+`, `-`, `*`, `/`); после сваке од секција унутар наредбе `for`; после сваког знака тачка-зарез (тј. знака `;`); после сваког зареза (тј. знака `,`), и сл.  

- Знаци за крај линије: убацити празне линије како би се раздвојиле секвенце логички повезаних операција.

- Апострофи и наводници: апостроф (тј. знак `'`) треба да има приоритет у односу на наводник (тј. знак `"`). Наиме, наводници су уобичајени код HTML атрибута, па коришљење апостофа помаже да се олакшају проблеми при раду са нискама које садрже HTML описе.

**Напомена.** Ако радни оквир који се користи или већ усвојени стандард кодирањњ садржи другачуја правила, онда се треба њима прилагодити. Један од популарних алата који олакшава сређивање и  форматирање програмског кода је [Prettier](https://prettier.io/){:target="_blank"}.

## Литература

1. Haverbeke M.: [Eloquent JavaScript](https://eloquentjavascript.net/){:target="_blank"}

1. [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript){:target="_blank"} - Mozzila Developer Network (MDN)

1. Живановић, Д.: [Веб програмирање - ЈаваСкрипт](https://www.webprogramiranje.org/scope-oblast-definisanosti-promenjive/){:target="_blank"}

1. Copes F.: [Complete JavaScript Handbook](https://medium.freecodecamp.org/the-complete-javascript-handbook-f26b2c71719c){:target="_blank"}
