1)
Чтоб начать работу с API необходимо получить токен авторизации
Для этого отправляем запрос на `http://corp.csdev.local/1c_api/auth.php`
Содержимо Body
```
[{
    "login":"Логин",
    "password":"Пароль"
}]
```
Получаем json вида
```
{
    "token": "Ваш токен"
}
```
Токен бессрочный

2)
Отправление json со скидками осуществяется по запросу на адресс `http://corp.csdev.local/1c_api/request.php`
Содержимо Body
```
[
  {
    "value": [
      {
        "KontragentGUID": "25e9557a-44d3-21ef-9b4f-00155ddcb000",
        "KontragentName": "ООО СИСОФТ ВОЛГОГРАД",
        "GorodGUID": "25e9557a-45d3-21ef-9b4f-00155ddcb000",
        "GorodName": "ВОЛГОГРАД",
        "KontragentИНН": "3443016270",
        "KontragentKPP": "344401001",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "SkidkaProc": 15
      },
      {
        "KontragentGUID": "25e9757a-44d3-21ef-9b4f-00155ddcb000",
        "KontragentName": "ООО СИСОФТ ВОРОНЕЖ",
        "GorodGUID": "25e9557a-45d3-21ef-9b4f-00155ddcb000",
        "GorodName": "ВОЛГОГРАД",
        "KontragentИНН": "3444076270",
        "KontragentKPP": "344401001",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "SkidkaProc": 25
      },
      {
        "KontragentGUID": "25e9957a-4483-21ef-9b4f-00155ddcb000",
        "KontragentName": "ООО СИСОФТ ИВАНОВО",
        "GorodGUID": "25e9557a-45d3-21ef-9b4f-00155ddcb000",
        "GorodName": "ВОРОНЕЖ",
        "KontragentИНН": "3444016270",
        "KontragentKPP": "344401001",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "SkidkaProc": 15
      }
    ],
    "token": "991391EA-7175-4C44-80B2-1C6BD6D78FF7"
  }
]
```
Не забываем указывать токен авторизации
Если все хорошо - получаем json вида
```
{'end' => 'Ok'}
```
Главное в json указать KontragentName ; GruppaNomName ; SkidkaProc
Скидка дается на раздел конкреному партнеру

3)
Обновление цен на товары осуществяется по запросу на адресс `http://corp.csdev.local/1c_api/pricelist.php`

Содержимо Body
```
[
  {
    "value": [
      {
        "NomenklaturaGUID": "25e9557a-44d3-11ef-9b4f-00155ddcb000",
        "NomenklaturaName": "Право на использование программного обеспечения AutomatiCS (2011 v.3.x, дилерская локальная лицензия (1 год))",
        "NomenklaturaArtikul": "ACS11L-DT-00000000",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "Price": 1488,
        "PriceComment": "Срок действия лицензии 1 год",
        "RegNumber": "855"
      },
      {
        "NomenklaturaGUID": "e4052e19-ade1-11e9-a142-005056c00008",
        "NomenklaturaName": "Право на использование программного обеспечения AutomatiCS (2011 v.3.x, локальная лицензия)",
        "NomenklaturaArtikul": "ACS11L-CU-00000000",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "Price": 796000,
        "PriceComment": "Обязательно приобретение подписки на обновления",
        "RegNumber": "855"
      },
      {
        "NomenklaturaGUID": "67b35582-c5b8-11e1-8104-000c29628f88",
        "NomenklaturaName": "Право на использование программного обеспечения AutomatiCS (2011 v.3.x, сетевая лицензия, серверная часть)",
        "NomenklaturaArtikul": "ACS11N-CU-00000000",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "Price": 796000,
        "PriceComment": "Поставка включает модуль защиты от несанкционированного доступа. Обязательно приобретение подписки на обновления",
        "RegNumber": "855"
      },
      {
        "NomenklaturaGUID": "3a169743-dd93-11ec-8445-ac1f6bd6ae4d",
        "NomenklaturaName": "Право на использование программного обеспечения AutomatiCS (2011 v.3.x, сетевая лицензия, доп. место)",
        "NomenklaturaArtikul": "ACS11A-CU-00000000",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "Price": 294300,
        "PriceComment": "Обязательно приобретение подписки на обновления",
        "RegNumber": "855"
      },
      {
        "NomenklaturaGUID": "1a14e480-c10e-11ee-8c0e-6cb3113987fb",
        "NomenklaturaName": "Право на использование программного обеспечения AutomatiCS (2011 v.3.x, локальная лицензия, доп. место)",
        "NomenklaturaArtikul": "ACS11B-CU-00000000",
        "GruppaNomGUID": "73ce5a29-7a53-11ef-a089-9cacae6ad557",
        "GruppaNomName": "AutomatiCS",
        "PodGruppaNomGUID": "73ce5a2a-7a53-11ef-a089-9cacae6ad557",
        "PodGruppaNomName": "AutomatiCS 2011 v.3",
        "Price": 294300,
        "PriceComment": "Обязательно приобретение подписки на обновления",
        "RegNumber": "855"
      }
    ],
    "token": "991391EA-7175-4C44-80B2-1C6BD6D78FF7"
  }
]
```

Главное указывать NomenklaturaName; Price ; 
Обратно получаем список
```
Обновили цену у товара у элемента каталога 6360 Цена 1488
Обновили цену у товара у элемента каталога 6374 Цена 796000
Обновили цену у товара у элемента каталога 6371 Цена 796000
Обновили цену у товара у элемента каталога 6372 Цена 294300
Обновили цену у товара у элемента каталога 6373 Цена 294300
```
