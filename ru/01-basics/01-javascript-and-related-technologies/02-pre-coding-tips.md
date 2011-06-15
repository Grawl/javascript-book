
# Перед тем, как начать кодить

Есть несколько основных платформ разработки JavaScript/html.

Обычный сайт будет хорош на всех.

=Cut


## Знай своего врага: типы браузеров


<ul>
<li><strong>Firefox</strong> и подобные браузеры платформе <i>Gecko</i> с открытым исходным кодом.</li>
<li><strong>Safari/Chrome</strong> — оба на платформе <i>Webkit</i> с открытым исходным кодом, но разной реализацией JavaScript. Chrome использует <i>Google V8</i>, а Safari использует свою платформу JavaScript с закрытым исходным кодом. Так как они оба на платформе Webkit, у них много общего.</li>
<li><strong>Opera</strong> использует свою платформу <i>Presto</i> с закрытым исходным кодом.</li>
<li><strong>Internet Explorer</strong> использует свою платформу <i>Trident</i> с закрытым исходным кодом. Платформа старая и просто ужасна в IE6 и IE7, но улучшена IE8 и обновлена в соответствии со стандартами в IE9.</li>
</ul>

Термины Gecko, V8, Webkit широко используются в профессиональных кругах. Trident и Presto — реже.

Иногда кросс-браузерная разработка усложняется, так что разделим браузеры по уровню их поддержки от А до В.

<dl><dt>А. Последний Firefox, IE, Safari/Chrome</dt>
<dd>Поддерживаются идеально.</dd>
<dt>Б. Opera и менее популярные браузеры</dt>
<dd>Поддерживаются довольно неплохо, но возможны незначительные проблемы с видом и поведением.</dd>
<dt>В. Старые основные браузеры</dt>
<dd>Поддерживается только основная функциональность.</dd>
<dt>Г. Очень старые браузеры. Текстовые браузеры.</dt>
<dd>Не поддерживаются. Если работает — хорошо. Если нет — всем всё равно.</dd>
</dl>

Это разделение — пример из реальной жизни.


## Выбери современный DOCTYPE   

Как уже известно из HTML, есть две основных модели отрисовки: <i>Режим Стандартов</i> и <i>Режим Совместимости</i>. В действительности же есть ещё один режим, <i>Режим Частичной Совместимости</i>, и все они хорошо описаны в Википедии: <a href="http://en.wikipedia.org/wiki/Quirks_mode">Quirks mode</a>.

Браузер выбирает режим в соответствии с `DOCTYPE` из шапки HTML.

Для современных сайтов хорош такой DOCTYPE:
[html]
*!*<!DOCTYPE HTML>*/!*
[/html]

С этим DOCTYPE современные браузеры работают в Режиме Стандартов, а старые — в Режиме Частичной Совместимости (это максимум, на что они способны).

Обратите внимание, что современный режим отрисовки — вопрос не только для HTML. Есть свойства JavaScript, которые зависят от режима отрисовки, особенно CSS-box и позиционирование.

Также, стили могут быть применены по-разному, например, Internet Explorer 7+ в Режиме Стандартов (строгий !DOCTYPE) может применять псевдо-класс `:hover` к любому элементу (как это и должно быть), а в не строгом режиме он может применять ':hover' только к ссылкам. 

Отказываясь от выбора верного DOCTYPE, вы увеличиваете время отладки. <code>&lt;!DOCTYPE HTML&gt;</code> это ок.


## Resources


### Manuals and how to search in them

<b>There are 2 main manuals on the net about JavaScript.</b> One comes from Microsoft and called <a href="http://msdn.microsoft.com/">MSDN</a>. They also call JavaScript a "JScript".

Another one is documentation center of <a href="https://developer.mozilla.org/">Mozilla Developer Network</a>.

I use the following method of search. When I need to find "RegExp" in Mozilla documentation, I just type <b>"RegExp MDC"</b> in google.

When I want to check MSDN, then "RegExp msdn". Sometimes it helps to add additional "jscript" term: <b>"RegExp msdn jscript"</b>.

MDN is usually good for general and firefox-specific information, while MSDN helps to deal with IE-specific features.


### Incompatibilities

There are many cross-browser incompatibilities in frontend-programming. When you come across them, <a href="http://www.quirksmode.org/">http://www.quirksmode.org/</a> may be a help.

It contains information about lots of incompatibilities. Also, there is a combo to search it. Try entering <b>"quirksmode onkeypress"</b> in google for instance.


### The ECMAScript specification

The language specification (formal description of syntax, basic objects and algorithms) of JavaScript is called <a href="http://www.ecma-international.org/publications/standards/Ecma-262.htm">ECMAScript</a>. 

[smart header="Why not just &quot;JavaScript&quot; ?"]
You may ask: "Why standard for JavaScript is not just <i>JavaScript</i>?".

That's because JavaScript&trade; is a registered trademark of Oracle corporation (used to be Sun trademark, but now Oracle acquired Sun). 

The title "ECMAScript" was choosen to keep the specification independent from trademark owners.
[/smart]

The language specification tells a lot about how it works, but it is an advanced source of information.

Today we live in a time of changes. The modern standard is <a href="http://www.ecma-international.org/publications/standards/Ecma-262.htm">ECMA-262 5th edition (or just ES5)</a>, but browsers are in the process of implementing it.

The old standard is <a href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%203rd%20edition,%20December%201999.pdf">ECMA 262 3rd edition (ES3)</a>. It is supported by all major browsers.

When you want to learn how the language works in-depth, there's more perspective in reading ES5, but remember that many features are not implemented yet. You can find a list of supported browsers/features at <a href="http://kangax.github.com/es5-compat-table/">http://kangax.github.com/es5-compat-table/</a>.


### HTML5

JavaScript is a general-purpose programming language. That's why ECMAScript specification does not tell a word about browsers. 

The browser stuff is described by a family of <a href="http://www.w3.org/TR/html5/">HTML5</a> standards.

The official <a href="http://www.w3.org/DOM/DOMTR">W3.org DOM specifications</a> are large, but extremely valuable. Use them as a reference. 

The searching combo <b>"something site:w3.org"</b> helps for DOM and Events-related questions. 

The only problem with W3 is that it describes how it should be, not how it is. 


## More?

Please write your general coding tips in comments.

