# Разбор поведения пользователей мобильного приложения.

Мы работаем в стартапе, который продаёт продукты питания. Нужно разобраться, как ведут себя пользователи мобильного приложения.

Изучим воронку продаж. Узнаем, как пользователи доходят до покупки. Сколько пользователей доходит до покупки, а сколько — «застревает» на предыдущих шагах? На каких именно?

После этого исследуем результаты A/A/B-эксперимента. Дизайнеры захотели поменять шрифты во всём приложении, а менеджеры испугались, что пользователям будет непривычно. Договорились принять решение по результатам A/A/B-теста. Пользователей разбили на 3 группы: 2 контрольные со старыми шрифтами и одну экспериментальную — с новыми. Выясним, какой шрифт лучше.

Создание двух групп A вместо одной имеет определённые преимущества. Если две контрольные группы окажутся равны, то мы можем быть уверены в точности проведенного тестирования. Если же между значениями A и A будут существенные различия, это поможет обнаружить факторы, которые привели к искажению результатов. Сравнение контрольных групп также помогает понять, сколько времени и данных потребуется для дальнейших тестов.

**Описание данных**

Каждая запись в логе — это действие пользователя, или событие. 
* EventName — название события;
* DeviceIDHash — уникальный идентификатор пользователя;
* EventTimestamp — время события;
* ExpId — номер эксперимента: 246 и 247 — контрольные группы, а 248 — экспериментальная.

# Вывод

Пользоватители мобильного приложения проходят такие этапы как: 1й шаг - MainScreenAppear (главный экран), 2й - OffersScreenAppear (экран предложения),3й - CartScreenAppear (корзина), 4й - PaymentScreenSuccessful (экран успешной оплаты), так же есть шаг "Tutorial", который является наиболее пропускаемым, только 11,5% пользователей совершали это событие. В процессе исследования удалось выявить, что данные полные только с 1 августа по максимальную дату (7 авг). 

Больше всего пользователей теряем после первого шага (главный экран) около 40%. Это может быть связано с тем, что пользователь не заинтересовался в предлагаемых услугах, либо не разобрался с интерфейсом, а так же выяснили, что на сайт можно прийти из поисковой строки, из рассылки, из пуш уведомления. Также товар в корзину можно отправить с главного экрана и т. д.

По результатам A/A/B-теста выявили, что стат значимой разницы между группами нет. Если компания заинтересована в привлечении и сохранении пользователей, то стоит рассмотреть другие варианты, т.к. изменения шрифта ничего не поменяет.
