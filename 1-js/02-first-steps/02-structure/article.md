# پێکهاتەی کۆد

یەکەم شت کە لێی دەکۆڵینەوە، بنەماکانی بنیاتنانی کۆدە.

## ستەیمێنت

بەیاننامەکان بریتین لە پێکهاتە و فەرمانەکان کە کردارەکان ئەنجام دەدەن.

پێشتر دەستەواژەی `alert('سڵاو,جیهان!')`مان بینیوە کە پەیامی "سڵاو، جیهان!" نیشان دەدات.

دەتوانین چەند فەرمانمان هەبێت لە کۆدەکانماندا. دەربڕینەکان دەتوانرێت بە سێمیکالۆن جیا بکرێتەوە.

بۆ نموونە لێرەدا "سڵاو جیهان" دابەش دەکەین بۆ دوو ئاگادارکردنەوە:

```js run no-beautify
alert('سڵام'); alert('جەهان');
```

دەربڕینەکان بەزۆری لەسەر دێڕی جیاواز دەنووسرێن بۆ ئەوەی کۆدەکە باشتر بخوێنرێتەوە:

```js run no-beautify
alert('سڵام');
alert('جیهان');
```

## نیمچە کۆلۆن [#semicolon]

کاتێک هێڵ شکاندن هەبێت، ڕەنگە لە زۆربەی حاڵەتەکاندا نیمچە کۆلۆنەکە نەهێڵرێت.

ئەمەش کاردەکات:

```js run no-beautify
alert('سڵاو')
alert('جیهان')
```

لێرەدا جاڤاسکڕێپت دێڕشکێنەکە وەک نیمچە کۆلۆنێکی `ناڕاستەوخۆ` لێکدەداتەوە. ئەمەش پێی دەوترێت [خزاندنی نیمچە کۆلۆنی ئۆتۆماتیکی](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion).

**لە زۆربەی حاڵەتەکاندا هێڵی نوێ بە واتای نیمچە کۆلۆن دێت. بەڵام "لە زۆربەی حاڵەتەکاندا" بە مانای "هەمیشە" نایەت!**

حاڵەت هەیە کە هێڵی نوێ بە مانای نیمچە کۆلۆن نییە. بۆ نموونە:

```js run no-beautify
alert(3 +
1
+ 2);
```

کۆدەکە `6` دەردەچێت چونکە جاڤاسکڕێپت لێرەدا نیمچە کۆلۆن ناخاتە ناوەوە.لە ڕووی ئینتێستیڤەوە ڕوونە کە ئەگەر هێڵەکە بە نیشانەی پڵەس `"+"` کۆتایی پێبێت، ئەوە دەربڕینێکی ناتەواوە، بۆیە نیمچە کۆلۆنەکەی ئەوێ هەڵەیە. وە لەم حاڵەتەدا، وەکو مەبەستی خۆی کاردەکات.

**بەڵام دۆخێک هەیە کە جاڤاسکڕێپت ناتوانێت گریمانە بکات کە نیمچە کۆلۆنێک بێت لەو شوێنانەی کە لە ڕاستیدا پێویستی پێیەتی.**

دۆزینەوە و چاککردنی ئەو هەڵانەی کە لەم جۆرە حاڵەتانەدا ڕوودەدەن زۆر ئەستەمە.

````smart header="An example of an error"
ئەگەر کنجکاویت بۆ بینینی نموونەیەکی هەڵەیەکی لەو جۆرە، ئەم کۆدە ببینە:

```js run
alert("Hello");

[1, 2].forEach(alert);
```

هێشتا پێویست ناکات بیر لە مانای کەوانەکانی `"[]"` و `"forEach"` بکەینەوە. دواتر لێیان دەکۆڵینەوە. بۆ ئێستا تەنها ئەنجامی جێبەجێکردنی کۆدەکە لەبیرت بێت: `"Hello"`، پاشان `"1"`، پاشان `"2"` پیشان دەدات.

ئێستا با نیمچە کۆلۆنەکە لە دوای "ئاگادارکردنەوە" لاببەین:

```js run no-beautify
alert("Hello")

[1, 2].forEach(alert);
```

جیاوازی بەراورد بەو کۆدەی سەرەوە تەنها یەک پیتە: نیمچە کۆلۆنەکە لە کۆتایی دێڕی یەکەمدا نەماوە.

ئەگەر ئەم کۆدە جێبەجێ بکەین تەنها یەکەم `"Hello"` پیشان دەدرێت (و هەڵەیەک هەیە، لەوانەیە پێویستت بە کردنەوەی کۆنسۆڵەکە بێت بۆ بینینی). ئیتر ژمارە نەماوە.

ئەمەش لەبەر ئەوەیە کە جاڤاسکڕێپت چاوەڕوانی نیمچە کۆلۆن ناکات پێش کەوانە "[...]". بۆیە کۆدەکانی کۆتا نموونە وەک یەک فرمان مامەڵەی لەگەڵ دەکرێت.

لێرەدا بزوێنەرەکەی چۆنە:

```js run no-beautify
alert("Hello")[1, 2].forEach(alert);
```

سەیرە، ڕاستە؟ یەکگرتنێکی لەو شێوەیە لەم حاڵەتەدا تەنها هەڵەیە. بۆ ئەوەی کۆدەکە بە دروستی کار بکات، پێویستە دوای `"alert"` نیمچە کۆلۆن دابنێین.

ئەمەش دەتوانێت لە بارودۆخی دیکەشدا ڕووبدات.
````

پێشنیار دەکەین نیوە کۆلۆن لە نێوان فرمانەکاندا دابنێیت تەنانەت ئەگەر بە هێڵی نوێ جیا بکرێنەوە. ئەم یاسایە بە شێوەیەکی بەرفراوان لەلایەن کۆمەڵگاوە قبوڵکراوە. با دووبارە تێبینی بکەین -- *دەکرێ* زۆربەی کات نیمچە کۆلۆنەکە نەهێڵرێت. بەڵام سەلامەتترن بۆ بەکارهێنان - بە تایبەت بۆ کەسانی سەرەتایی.

## کۆمێنتەکان [#code-comments]

بە تێپەڕبوونی کات بەرنامەکان ئاڵۆزتر دەبن. زیادکردنی *کۆمێنت* کە ڕوونی بکاتەوە کە کۆدەکە چی دەکات و بۆچی زۆر گرنگە.

دەتوانرێت کۆمێنتەکان لە هەر شوێنێکی سکریپتێکدا دابنرێت. کاریگەرییان لەسەر جێبەجێکردنی نییە چونکە بزوێنەرەکە تەنها پشتگوێیان دەخات.

**کۆمێنتەکانی یەک دێڕ بە دوو کاراکتەری ئێسلەش دەست پێدەکات`//`.**

باقی دێڕەکە بۆچوونێکە. لەوانەیە دێڕێکی تەواو داگیر بکات یان دوای لێدوانێک بێت.

وەک لێرە:
```js run
// This comment occupies a line of its own
alert('Hello');

alert('World'); // This comment follows the statement
```

**سەرنجە فرە هێڵەکان بە هێڵی پێشەوە یا ئێسلەش و ئەستێرە <code>/&#42;</code> دەست پێدەکات و بە ئەستێرە و هێڵی پێشەوە <code>&#42;/</code> کۆتایی دێت.**

Like this:

```js run
/* An example with two messages.
This is a multiline comment.
*/
alert('Hello');
alert('World');
```

ناوەڕۆکی کۆمێنت پشتگوێ دەخرێت، بۆیە ئەگەر کۆدەکە بخەیتە ناو <code>/&#42; ... &#42;/</code>، کارناکات.

هەندێک جار دەتوانێت بەسوود بێت بەشێک لە کۆدەکە بۆ ماوەیەکی کاتی لەکاربخەیت:

```js run
/* Commenting out the code
alert('Hello');
*/
alert('World');
```

```smart header="Use hotkeys!"
لە زۆربەی دەستکاریکەرەکاندا دەتوانرێت دێڕێکی کۆد بکرێتەوە بە فشاردان لەسەر کلیلی گەرمی "key:Ctrl+/" بۆ کۆمێنتێکی تاکە دێڕ و شتێکی وەک "key:Ctrl+Shift+/" - بۆ سەرنجە فرە دێڕییەکان (پارچە کۆدێک هەڵبژێرە ).
بۆ ماک لەبری "key:Ctrl" "key:Cmd" و لەبری "key:Shift" "key:Option" تاقی بکەرەوە.
```

````warn header="Nested comments are not supported!"
"/*...*/" لەوانەیە لە "/*...*/" ی تردا بوونی نەبێت.

ئەم جۆرە کۆدە بە هەڵەیەک شکست دەهێنێت:

```js run no-beautify
/*
  /* nested comment ?!? */
*/
alert( 'World' );
```
````

تکایە دوودڵ مەبن لە کۆمێنتی کۆدەکانتان.

کۆمێنتەکان شوێنپێی گشتی کۆدەکە زیاد دەکەن، بەڵام ئەوە بە هیچ شێوەیەک کێشە نییە. زۆر ئامراز هەیە کە کۆدەکان بچووک دەکەنەوە پێش ئەوەی بڵاوی بکەنەوە بۆ سێرڤەری بەرهەمهێنان. کۆمێنتەکان لادەبەن، بۆیە لە سکریپتە کارکەرەکاندا دەرناکەون. بۆیە کۆمێنتەکان بە هیچ شێوەیەک کاریگەری نەرێنی لەسەر بەرهەمهێنان نییە.

دواتر لە فێرکارییەکەدا بابەتی <info:code-quality> دەبێت کە هەروەها چۆنیەتی نووسینی کۆمێنتی باشتر ڕوون دەکاتەوە.
