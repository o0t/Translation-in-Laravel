# <p align="center" > Translation-in-Laravel </p>
# <p align="center"> الترجمة في لارافيل </p>



<br><br><br>

##  <p align="center" >  Laravel translation features </p>
<li align="center"> Translate each word in the language assigned to it </li>
<li align="center"> Turn the page from right to left</li>
<li align="center"> The translation is done in one language file</li>
<li align="center"> The translation is done using a file json</li>
<li align="center">  The language is stored in the session</li>
<li align="center">  You can create CSS files for each language </li>


## <p align="center"> ميزات الترجمة في لارافيل   </p>
<li dir="rtl" align="center"> ترجمة كل كلمة باللغة المخصصة لها </li>
<li dir="rtl" align="center"> اقلب الصفحة من اليمين إلى اليسار </li>
<li dir="rtl" align="center"> تتم الترجمة في ملف واحد خاص باللغة </li>
<li dir="rtl" align="center"> تتم الترجمة باستخدام ملف json </li>
<li dir="rtl" align="center"> يتم تخزين اللغة في الجلسة </li>
<li dir="rtl" align="center"> يمكنك إنشاء ملفات CSS لكل لغة </li>


<br><br><br>
<hr>
<br>

 ## [1] - Go to the settings page of the application to add the languages we want    `config/app.php` 
  
  locale : is The main language of the application


###   Add 

 ![لقطة الشاشة 2022-12-15 030646](https://user-images.githubusercontent.com/94997828/207741941-c6a66a4e-59ce-4d1e-80c3-f8351b999670.png)

```bash
  
    /*
    |--------------------------------------------------------------------------
    | Available locales
    |--------------------------------------------------------------------------
    |
    | List all locales that your application works with
    |
    */


    'available_locales' => [
    'English' => 'en',
    'Arabic'  => 'ar',
    'Russian' => 'ru',
    'French' => 'fr',
    ],


```


 ## [2] - Then create a file in the language you want, here I will use the Arabic language `resources/lang/ar.json` 


![image](https://user-images.githubusercontent.com/94997828/207743448-146fd867-b990-4175-9849-8fe068703aee.png)

```bash
    {
    "Welcome": "مرحبا"
    }
```

 ## [3] - Go to the main page to type the word in translation mode `welcome.blade.php` 

 
![image](https://user-images.githubusercontent.com/94997828/207743648-d3300aaf-31e2-4a76-a4e7-e58ef1546897.png)

```bash
    {{__('Welcome')}}
```

 ## [4] - Switching locales in Laravel  `routes/web.php` 
 
 ![image](https://user-images.githubusercontent.com/94997828/207743892-2bae5779-baa1-4f89-b4e7-abaff0d2298d.png)


```bash
   Route::get('lan/{locale?}', function ($locale = null) {
       if (isset($locale) && in_array($locale, config('app.available_locales'))) {
           app()->setLocale($locale);
       }

       return view('welcome');
   });
```

 ## [4] - Create  Middleware  `php artisan make:middleware Localization` 
 
 ![image](https://user-images.githubusercontent.com/94997828/207744116-76dc949f-468d-4127-9458-e7cb699f4835.png)




