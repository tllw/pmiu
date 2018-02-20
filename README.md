# PMIU (Android) упражнения и задачи

## Изисквания и препоръки

* Всички задачи се предават като линк към github проект
* Кодът да следва Android style guidelines (https://google.github.io/styleguide/javaguide.html)
* Към проектите да бъдат включени тестове (unit и функционални). Espresso (https://developer.android.com/training/testing/espresso/index.html)
* Кодът ще бъде проверяван за плагиатсво
* Използването на Dependency injection (Dagger2 - https://github.com/google/dagger) и View bindings (Butter knife - http://jakewharton.github.io/butterknife/) ще се поощрява
* Препоръчва се използването на Java 8 (вместо базовия Java 6) синтаксис и механизми : lambdas, method references, type annotations и т.н.

## Упражнения

### 1. Структура на андроид проект. Структура на AndroidManifest и gradle. Включване на външни библиотеки.
   Да се разработи приложение, което зарежда растерен графичен файл от URL и го прилага на ImageView. Да се използва Picasso (https://github.com/square/picasso). *Bonus:* да се реализира Callback известяващ при зараждане на графичния файл (успешно и неуспешно).
   
---

### 2. Андроид activity клас, намерения (Intent-и). Предаване на параметри чрез намерения.
Да се реализира приложение, в което в първо activity се въвежда информация за PhoneBookEntry (name, phone, type). Създава се PhoneBookEntry, което сериализирано се подава чрез intent на второ activity. Второто activity визуализира PhoneBookEntry-то. *Bonus:* Да се имплементира Parcelable interface, който да се използва в intenta, вместо сериализация.

---

### 3. Lifecycle на андроид activity. Стартиране на активити за резултат. Използване на log и debug-ер. 
Да се създаде абстрактен клас **BaseActivity**, с protected член TextView **logTextView**. Нека BaseActivity наследи (Override) всички lifecycle методите на Activity (onStart(), onResume(), etc) и за всеки от тях логва текущата команда едновременно в logcat(Log.d) и в logTextView (hint: използвайте append()).

Да се създадат две активитита **MainActivity** и **SecondActivity**, които наследяват BaseActivity (hint: погрижете се за инстанцирането на logTextView и разрешето скролирането му – *android:scrollbars = "vertical"*). Създайте аналогични lifecycle методи и за двете (hint: не забравяйте super call). 

**Да се създадат следните *layouts* съответно за MainActivity и SecondActivity.**

   ![layouts](https://github.com/tllw/pmiu/blob/master/exercise3/activities.png)
   
   * Нека бутонът *Start Second For Result* стартира второто активити за резултат.
   * Нека бутонът *Return* връща като резултат стойността NumberResult.
   * Нека бутонът *Finish* финишира второто активити. 
   * Нека всички изпълнени команди (включая startActivityForResult и резултата) се логват с подходящ текст в *logTextView* и в *logcat*.
   
---
   
### 4. Събития (Event listeners). Navigation drawer menu. 
**4.A** Да се създаде приложение със странична *Navigation drawer* навигация. Нека приложението има две activity-та, като в navigation drawer менюто има връзки към двете активитита (*hint: иползвайте базов активити клас за обработката на onOptionsItemSelected*).

**4.B** Нека първото activity е изградено от Fab бутон и линеен лейаут (**linear layout**). Нека при натискането на Fab бутона от потребителя към layout-а се прибавя нов бутон (Button X, където X е поредността на бутона). Нека при натискането на всеки един бутон се показва *AlertDialog* с текст “Button X clicked” и действие OK, което затваря диалога.

**4.C** Нека второто активити съдържа TextEdit и TextView. Нека да се имплементира TextWatcher (*hint: textEdit.addTextChangedListener() *), така че всяка промяна на стойността на TextEdit полето веднага да бъде отразявана в TextView елемента (*hint:* onTextChanged()). 

*Bonus:* нека всички OnXXXListeners се заменят с Java 8 lambda functions. 

## Курсови задачи

1.	Да се реализира приложение "Прогноза за времето", което при въведена локация да визуализира в подходящ стил прогноза на времето. Програмата да действа като асинхронен **REST** клиент на HTTP API. За реализация на заявките и десериализация на JSON да се използва **Retrofit** (https://github.com/square/retrofit). 

2.	Да се реализира **CRUD** телефон указател, като се използва **MVVM** или **MVP** архитектура. Да се изберат подходящите структури данни и проектират подходящите обекти за репрезентиране на указателя и неговите елементи. Да се използват **Android Architecture Components** - ViewModel и LiveData.

3.	Да се проектира **CRUD** фитнес дневник (таблици: дни, видове упражнения, програми), чиито данни се съхраняват в sqlite база данни. Да се използва **Room** за абстракция на базата данни. 

4.	Да се реализира известната игра Snake (змия). 

5.	Да се реализира програма "GPS локатор", в която **background service** переодично проверява текущото разстояние до зададен обект (дефиниран от GPS координати, например 43.2228918, 27.9345786) и уведомява **activity**, което го показва на потребителя. Да се реализира функционалност, която позволява имплицитно опресняване на разстоянието. 

6.	Да се проектира **CRUD** to-do приложение. Като всички UI функционалности, както и комуникацията между Model и View сe базират на **ReactiveX observables**. Да се използва **RxJava2-Android**.
