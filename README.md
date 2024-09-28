# generation_of_Ukrainian_language_tests
Програма для генерації тестів за типами речень
Типи речень, які може визначати програма:
'Просте', 'Односкладне', 'Означено-особове', 'Неозначено-особове', 'Узагальнено-особове', 'Безособове', 
'Двоскладне', 'Називне', 'Складносурядне', 'Складнопідрядне', 'Складне', 'Складне безсполучникове'

Структура:
app.py - файл, який пускає програму

Arial-BoldMT.ttf, ArialMT.ttf - файли зі шрифтами

utils -> doc_with_functions.py - основний файл з функціями 

templates -> html

from_textes - папка, з якої беруться тексти для аналізу

typed_sentanses - папка, у яку записуються файли за типізацією речень

bin_place_testa_here - папка, у яку створюватимуться файли, з якої вони передаватимуться користувачам


Виклик: 

1) вручну:
   pip install requirements.txt
   у utils -> doc_with_functions.py у функцію main передаєте шлях до файлу типу .docs з обраним вами текстом
   у get_list_of_exersize передаєте ліст з типами речень, тести до яких хочете згенерувати
   результат get_list_of_exersize передаєте в create_pdf
   Зачекайте, на жаль, це не дуже швидко
   у папці bin_place_testa_here згенерується файл з датою генерації

2) через сайт:
   обрати одного з авторів, к-ть тестів у документів, а також типи речень
   зачекати допоки файл завантажиться на ваш комп'ютер


Приніцип роботи коду:

Зчитуємо файл
Пропускаємо його через stanza
Для кожного достатньо довгого речення створюємо екземпляр класу, визначаємо його тип
Записуємо речення за типами у файл

Отримуємо дані про к-ть тестів, а такод їх типи
Генеруємо пропорцію можливих співвідношень інших варіантів відповідей у тесті
Відповідно до співвідношення. витягуємо з файлів потрібну к-ть речень
Генеруємо тест
