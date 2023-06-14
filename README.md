# Object_JAVA
[Class Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html) `java.lang.Object`

В корне иерархии всех классов находится класс `java.lang.Object`, который является наиболее общим из всех классов. java.lang.Object является прародителем (суперклассом) всех объектов. 
Это начальный класс, из которого произведены все остальные классы. Методы, определенные в `Object`, очень важны, так как они появляются в каждом экземпляре каждого класса по всей Java.


### Особенности:
* Каждый класс имеет класс Object в качестве суперкласса (неявно).
* Все объекты, включая массивы, наследуют методы этого класса.
* Объектами не являются лишь простые типы: числа, символы и логические значения.

## Методы класс Object.

* `clone()` - Создает и возвращает копию этого объекта. `protected Object`

* `equals(Object obj)` - Указывает, является ли какой-либо другой объект «равным» этому. `boolean`

```
public boolean equals(Object obj)
Указывает, является ли какой-либо другой объект "равным" этому.

Метод `equals` реализует(implements ) отношение эквивалентности для ненулевых ссылок на объекты:

	* Это рефлексивно: для любого ненулевого ссылочного значения `x`, `x.equals(x)` должно возвращать `true`.

	* Это симметрично: для любых ненулевых ссылочных значений `x и y, x.equals(y)` должно возвращать `true` тогда и только тогда, когда `y.equals(x)` возвращает true.

	* Это транзитивно: для любых ненулевых ссылочных значений `x, y и z, если x.equals(y)` возвращает `true`, а `y.equals(z)` возвращает `true`, то `x.equals(z)` должен возвращать значение true.

	* Это согласовано: для любых ненулевых ссылочных значений x и y многократные вызовы `x.equals(y)` последовательно возвращают `true` или последовательно возвращают `false`, при условии, что информация, используемая при сравнении объектов `equals`, не изменена.

	* Для любого ненулевого ссылочного значения x, x.equals(null) должно возвращать значение false.

Метод `equals` для `class Object` реализует наиболее точное из возможных отношений эквивалентности объектов; то есть для любых ненулевых ссылочных значений x и y этот метод возвращает true тогда и только тогда, когда x и y ссылаются на один и тот же объект (x == y имеет значение true)..

Обратите внимание, что обычно необходимо переопределять метод `hashCode` всякий раз, когда этот метод переопределяется, чтобы сохранить общий контракт для метода `hashCode`, в котором указано, что равные объекты должны иметь равные хэш-коды.

Параметры:
obj - эталонный объект, с которым выполняется сравнение.
Возвращается:
истинно, если этот объект совпадает с аргументом obj; ложно в противном случае.
```

* `finalize()` - Вызывается сборщиком мусора для объекта, когда сборщик мусора определяет, что больше нет ссылок на объект. `protected void`

* `getClass()` - возвращает объект типа Class (описание класса объекта). `Class<?>`

```
public final Class<?> getClass()
Возвращает класс времени выполнения этого Object. Возвращаемый Class object — это объект заблокированный  static synchronized методами представляемого класса.

Фактический тип результата — Class<? extends |X|> where |X| стирание статического типа выражения, для которого getClass вызывается. Например, в этом фрагменте кода приведение не требуется:

Number n = 0;
Class<? extends Number> c = n.getClass();

Возвращает:
Объект Class, представляющий класс среды выполнения этого объекта.
```


* `hashCode()` - возвращает уникальный идентификатор объекта(). `int`

```
public int hashCode()
Возвращает значение хэш-кода для объекта. Этот метод поддерживается для хеш-таблиц, таких как предоставленные HashMap.

Общий контракт hashCode:
	* Всякий раз, когда он вызывается для одного и того же объекта более одного раза во время выполнения Java-приложения, метод hashCode должен последовательно возвращать одно и то же целое число, при условии, что информация, используемая при сравнении equals для объекта, не изменяется. Это целое число не обязательно должно оставаться неизменным от одного выполнения приложения к другому выполнению того же приложения.

	* Если два объекта равны в соответствии с методом `equals(Object)`, то вызов метода `hashCode` для каждого из двух объектов должен привести к одинаковому целочисленному результату.

	* Не требуется, чтобы, если два объекта были неравными в соответствии с `equals`(java.lang.Object) метод, затем вызов метода `hashCode` для каждого из двух объектов должен приводить к различным целочисленным результатам. Однако программист должен знать, что получение различных целочисленных результатов для неодинаковых объектов может повысить производительность хэш-таблиц.

Насколько это разумно практично, метод hashCode, определенный `class Object`, возвращает различные целые числа для различных объектов. (Обычно это реализуется путем преобразования внутреннего адреса объекта в целое число, но язык программирования Java™ не требует такого способа реализации.)

Возвращается:
значение хэш-кода для этого объекта.
```


* `notify()` - возобновляет (уведомляет) один из потоков, вызвавших метод wait() на этом же объекте. `void`

* `notifyAll()` - возобновляет (уведомляет) все потоки, вызвавшие метод wait() на этом же объекте.

* `toString()` - возвращает представление объекта в виде строки. `String`

* `wait()` - Заставляет текущий поток ожидать, пока другой поток не вызовет notify() метод или notifyAll() метод для этого объекта. `void`

* `wait(long timeout)` - Заставляет текущий поток ожидать, пока другой поток не вызовет notify() метод или notifyAll() метод для этого объекта, или пока не истечет указанное количество времени. `void`

* `wait(long timeout, int nanos)` - Заставляет текущий поток ожидать, пока другой поток не вызовет notify()метод или notifyAll()метод для этого объекта, или какой-либо другой поток не прервет текущий поток, или пока не истечет определенное количество реального времени. `void`










