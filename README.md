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
+ :file_folder: shared
  + :file_folder: ui
  + :file_folder: api
  + :file_folder: assets

> Папки всередині `📁 pages` називаються слайсами. Вони ділять шар по домену (у разі, сторінкам).

> Папки всередині `📁 app`, `📁 shared` та `📁 pages/user` називаються сегментами, і вони ділять слайси (або шари) за технічним призначенням, тобто для того, для чого призначений код.

<h3>Вкладеність</h3>

___
![Nesting][src/shared/assets/nesting.png]
