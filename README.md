<h1>FDS</h1>

<h3>Базовий приклад</h3>

+ :file_folder: app
  + :file_folder: routes 
  + :file_folder: analytics 
+ :file_folder: pages
  + :file_folder: home
  + :file_folder: about
  + :file_folder: user
    + :file_folder: ui
    + :file_folder: api
    + :page_facing_up: index
  + :file_folder: settings
+ :file_folder: widgets
  + :file_folder: pagination
  + :file_folder: slider
+ :file_folder: features
  + :file_folder: cart
  + :file_folder: search
+ :file_folder: entities
  + :file_folder: post
  + :file_folder: catalogItem
+ :file_folder: shared
  + :file_folder: ui
  + :file_folder: api
  + :file_folder: assets

> Папки всередині `📁 pages` називаються слайсами. Вони ділять шар по домену (у разі, сторінкам).

> Папки всередині `📁 app`, `📁 shared` та `📁 pages/user` називаються сегментами, і вони ділять слайси (або шари) за технічним призначенням, тобто для того, для чого призначений код.

<h3>Шари</h3>

___
<img src="https://github.com/CumMbILLI/FSD/blob/main/src/shared/assets/Nesting.png?raw=true" width=80% class="position: absolute">

+ **Розділяється рівень.** Містить різні ресурси для повторного використання, які залежать від функціонування бізнес-логіки.
+ **Відмінні приклади таких елементів** - інструменти для роботи з UI, допоміжні функції, логери.
+ **Рівень об'єктів.** Він містить бізнес-об'єкти, специфічні для проекту. Наприклад, User, Payments, Products тощо.
+ **Рівень фіч.** Містить користувацькі історії. Код, цінний з погляду бізнесу. Наприклад, ChangePassword, MakePayment, BuyProduct.
+ **Рівень віджетів.** Містить компоненти, з яких складаються об'єкти та фічі. Наприклад, UserSettings, PaymentsList, ProductsList.
+ **Рівень сторінок.** Містить сторінки програми. Це композиційний рівень, що збирається з об'єктів, фіч та віджетів.
+ **Рівень процесів.** Містить складні внутрішньосторінкові сценарії, наприклад, механізми автентифікації та капчу.
+ **Рівень програми.** Містить настройки програми, стилі та провайдери. Наприклад, withAuth.

<h3>Зрізи</h3>

___

```py
├── app/
|   # Шар композиції програми
|   # Містить лише абстрактну логіку ініціалізації та статичні ресурси – 
|   # отже, не містить жодних зрізів
|
├── pages/
|   # Зрізи, що реалізують повні уявлення для цієї програми
|   ├── home/
|   ├── sign-up/
|
├── widgets/
|   # Зрізи, що реалізують різні комбінації абстрактних та/або бізнес-блоків з
|   # нижчих шарів, для надання ізольованих атомарних фрагментів інтерфейсу
|   # користувача
|   ├── pagination/
|   ├── slider/
|
├── features/
|   # Зрізи, що реалізують користувальницькі сценарії; зазвичай тут доводиться
|   # оперувати бізнес-об'єктами
|   ├── createPost
|   ├── cart
|
├── entities/
|   # Зрізи, що реалізують бізнес-блоки в термінах того, яка бізнес-логіка 
|   # програми спрацює
|   ├── catalogItem
|   ├── post
|
├── shared/
|   # Цей шар – набір абстрактних сегментів
|   # Це означає, що на ньому неприпустимі будь-які бізнес-блоки або логіка,
|   # що стосується бізнесу
```

