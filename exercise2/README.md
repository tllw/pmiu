Activity и Intent

# Андроид activity клас
Един от основните компоненти за създаване на визуален интерфейс в Android приложенията е Activity. Често е свързано с отделен екран или прозореца на приложението. Всяко Activity е обект от класа android.app.Activity, която предоставя основната функционалност за всички дейности. В приложението MainActivity наследява класа AppCompatActivity чрез който наследява класа Activity.

Достъпването на ресурси от layout в Activity става с метода findViewById който приема id на ресурс.

# Intent
 Intent е обект-съобщение, което се използва за да се извика действие от друг компонент на системата
Видове:
Експлицитни интенти - задават кой компонент конкретно искат да се стартира
Intent i = new Intent(this, NewActivity.class);
Имплицитни интенти - задават само какво трябва да може компонента, който се стартира
Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE)

Предаване на данни към Activity
intent.putExtra("objectName", obj);

Прочитане на данни
getIntent().getSerializableExtra("objectName");

**Задачи**
Съставете приложения с три Аctivity.
Първото Аctivity съдържа поле за въвеждане на име и бутон, при натискане на бутона името да се предаде към второто Аctivity.
Второто Аctivity съдържа поле за показване на името от първото Аctivity и полета за въвеждане на Години, Адрес, Град, Дата за раждане (от класа People) и бутон, при натискане на бутона обекта People да се предаде към третото Аctivity.
Третото Аctivity визуализира обекта People.
Упътване: Да се използва Parcelable interface, за полетата с цифрова стойност да се активира клавиатура само с цифри.
Бонус: Добавете бутон в третото Аctivity, който да отваря Google Map с карта центрирана върху адреса.
