依據官方對object reference的說法
https://www.php.net/manual/en/language.oop5.references.php

> A PHP reference is an alias, which allows two different variables to write to the same value. In PHP, an object variable doesn't contain the object itself as value. It only contains an object identifier which allows object accessors to find the actual object. When an object is sent by argument, returned or assigned to another variable, the different variables are not aliases: they hold a copy of the identifier, which points to the same object.

PHP的參照是一種 alias ，讓不同的變數可以修改同個值
但php的物件變數，並不是真正的包含物件自己本身，只是包含一個識別符指向實際物件
當參照一個物件時，他只是一個識別符的複本並指向同個物件



引用: https://tw511.com/a/01/4341.html

1、變數1=變數2=物件 會建立物件的2個獨立參照，但是他們指向的還是同一個物件，所以還是會互相影響

2、變數1=&變數2 只會建立物件的一個參照,因為它們使用同一個物件參照

3、一個物件有沒有用，就要看它是否完全沒有被參照了，如果沒有任何變數參照它，它就真的沒用了，
   才會被銷毀，進而它的解構函式才會得以執行

4、變數1=clone 變數2=物件，不會建立物件的新參照，而是仿造了一個新的該物件，具有該物件通用的屬性和方法

參考:
https://ithelp.ithome.com.tw/articles/10191972  
https://mt116.blogspot.com/2017/08/php-references.html  
