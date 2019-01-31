# Android Studio

# Инсталиране на среда за проектиране

Проектирането на Android приложения, изисква използването на среда за проектиране (IDE) и програмния език JAVA, който на свой ред се нуждае от наличието на JDK.

Стандартната среда за проектиране на Android приложения е Android Studio, то е свободно за изтегляне от:
https://developer.android.com/studio/

При инсталирането следваите стъпките в помощника за инсталация.

# Създаване на проект

От началния прозорец избирате "New Android Studio project"

![Android_Studio_NewProject_Screen_1.PNG](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Studio_NewProject_Screen_1.PNG)

Следващата стъпка е да се избере платформата за която ще се проектира приложението и SDK. Всяка платформа и устроиство имат различно SDK затова е необходимо да знаете точките устроиства за които разработвате за да изберете подходящо SDK.

![Android_Studio_NewProject_Screen_1.PNG](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Studio_NewProject_Screen_2.PNG)

Трябва да дадете име и местоположение на проекта, който да са уникални без специялни символи и празно пространство.

![Android_Studio_NewProject_Screen_1.PNG](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Studio_NewProject_Screen_3.PNG)

# Виртуално устройство с Android OS
Емулатора на Android устройства позволява да се тестват и дебъгват приложения преди качването им на реални устройства.

Създаването на Android устройства става с Android Virtual Device (AVD) Manager. По подразбиране има инсталирано едно устройство с последната версия на Android.

Създаването на виртуални устройства става с помощта на помощник за инсталация където се избират размера на дисплея, оперативната и физическата памет на устройството допълнителни сензори от които се нуждаем за тестване на приложението.

# Проблеми при стартирането на емулатора

За ефективна работа с емулатора и Android Studio е необходима минимум 8GB оперативна памет на компютъра за разработка.

За да работи емулатора:

- Трябва да се активира технологията Intel® Virtualization Technology от BOIS или съответния еквивалент AMD Virtualization за AMD процесорите
- Инсталиране на Intel x86 Emulator Accelerator от Android SDK Manager 
![Android_Studio_NewProject_Screen_1.PNG](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_SDK_Manager_1.PNG)
- От AMD Manager отворете виртуалното устройство в режим за редактиране където изключете Use Host GPU и включете Snapshot, по този начин устройството ще се стартира от изображение вместо да се изпълнява всеки път при стартиране.

# Структура на проект
Проектите в Android Studio използва Gradle за изграждане на приложенията. В Gradle скрипта се оказват минималната и целевата версия на Android за които се разработва програмата. Зависимите библиотеки към приложението.

![Android_Gradel_Scrip](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Gradel_Script.PNG)

Във файла AndroidManifest.xml се задава конфигурацията на приложението. Името на приложението, главното активити, иконата и темата на дизайна, разрешения за функциите на телефона до които ще има достъп приложението

![Android_Manifest_JAVA](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Manifest_JAVA_.PNG)

В папката java са клас файловете на приложението.

![Android_Res](https://github.com/theVelislavKolesnichenko/AndroidBasics/blob/master/Wiki/Images/Android_Res.PNG)

Най-важната папка е res. Тя съдържа ресурсите на приложението:

- drawable - съдържа изображенията за различните разделителни способности на екрана
- layout - съдържа оформлението на потребителския интерфейс
- menu - съдържа XML на менюто
- values - различни стойности като текстове, масиви и други
