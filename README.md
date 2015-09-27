# Bitcoin-tracker-Ultimate-pro-v1.01-beta
Bitcoin tracker Ultimate pro v1.01 beta 

Требования к проекту

1 Введение

Приложение для Windows Phone 7.1 для отслеживания актуальной информации на рынке BitCoin. 
Название продукта для Marketplace «BitCoin tracker pro Ultimate v1.01 beta». При помощи 
данного приложения пользователь сможет отслеживать последние действия на рынке, курсы на 
популярных биржах, а так же иную полезную информацию, так необходимую пользователям популярной 
криптовалюты. Приложение не поддерживает управления своим биткоин-кошельком, однако и не требует его наличия. 

2 Требования пользователя

2.1 Программные интерфейсы

BitCoin tracker pro Ultimate v1.01 beta использует API-библиотеки сервиса www.blockchain.info 
для реализации: 
- отслеживания последних транзакций и создании новых блоков на рынке биткоин, используя
Websocket API, получая JSON-объекты с ресурса; 
- просмотра блоков основной цепи и истории транзакций каждого блока через API данных Blockchain;
- отслеживания актуальных курсов валют на крупнеших биржах биткоин;
- предоставления данных о кол-ве выпущенных биткоинов на текущий момент;
- расчёта  приблизительного числа биткоинов, находящихся в реальном обращении на рынке 
(биткоинов, не используемых для накопительных целей и «пропавших» биткоинов). 

2.2 Интерфейс пользователя

Приложение будет использовать стандартный шаблон для Windows Phone приложений Windows Phone 
Panorama Application – приложение-панорама, в котором зоны взаимодействия с пользователем также 
разделены на панели, но доступны они через горизонтальную прокрутку; фоновое изображение установлено 
сразу на всю панораму, она имеет общий заголовок, который прокручивается медленнее, чем панели; 
контент соседней панели справа виден при отображении текущей. Например, таким образом  реализованы 
хабы в Windows Phone: People, Marketplace, Pictures, Music+Videos и др. Шаблон использует элемент 
управления Panorama.  

2.3 Характеристики пользователей

Данное приложение ориентировано на пользователей, знакомых с понятием о криптовалюте, и желающих 
ознакомится с её принципами и особенностями. Приложение подразумевает наличие базовых навыков взаимодействия 
со средой Windows Phone (наличие устройства на базе ОС Windows Phone версии 7.1 и выше),  а так же 
знание базовых понятий о рынке криптовалют.

2.4 Предположения и зависимости

- корректная работа BitCoin tracker pro Ultimate v1.01 beta напрямую зависит от работы сервиса 
blockchain.info (актуальности информации на сервисе, функционирования API-библиотек);
- необходимо постоянное и стабильное наличие доступа к сети Интернет. Из этого следует возможность 
подключения устройства к Wi-fi сети с доступом в Интернет, или же наличие sim-карты от оператора, 
предоставляющего услуги передачи данных 2G/3G. 

3 Системные требования

3.1 Функциональные требования

- рабочее пространство приложения представляет собой несколько  панелей, сменяемых через 
горизонтальную прокрутку;
- каждая панель предоставляет определённый список, соответствующий названию панели;
- экран Transactions (Транзакции) предоставляет потоковое представление новых транзакций, 
произошедших с момента начала работы приложения (но не более 150), где каждая новая транзакция 
ставится на вершину списка;
- экран Blocks(Блоки) предоставляет список последних блоков, включённых в основную цепь (кол-во 
блоков выводится за определённый период, который можно задать);
	+ при выборе блока, на экран выводится список транзакций, относящихся к данному блоку;
- экран Info (Инфо) содержит список runtime-пунктов, в которые  при нажатии выводят на экран 
соответствующую названию пункта информацию (пункты: Trading (Биржа), Amount (Денежная масса), 
Bitcoin using (Биткоины в обороте));
	+ Trading (Биржа) – выводит на экран актуальные на момент запроса курсы биткоин на 
	крупнейших биржах биткоин;
	+ Amount (Денежная масса) – выводит на экран кол-во биткоинов, выпущенных на рынок на 
	момент запроса;
	+ Bitcoin using (Биткоины в обороте) – подсчитывает кол-во биткоинов, реально участвующих 
	в торговле на основании транзвкций, проведённых за определённый период. Алгоритм подсчёта: 
		1.	Создаётся массив всех адресов биткоин-кошельков, участвующих в транзакциях за указанный период; 
		2.	Для каждого кошелька высчитывается кол-во средств пришедших-ушедших со счёта;
		3.	Формируется показатель прибыли/убытка для каждого кошелька (кол-во поступивших средств минус кол-во снятых);
		4.	Результатом будет являться сумма всех неотрицательных показателей;

3.2 Нефункциональные требования

3.2.1 АТРИБУТЫ КАЧЕСТВА

- приложение должно быть ориентировано на работу с пользователем, т.е. иметь интуитивный интерфейс, использовать простые понятия и не перегружать визуальное поле слишком большим объёмом информации.
- установочный файл не должен превышать 4-5 Мб для возможности его скачивания при наличии медленного соединения с интернетом, а так же не должно занимать слишком много места в памяти устройства в установленном виде.
- запущенное приложение не должно потреблять слишком много ресурсов устройства, для плавного и не искажённого (не актуального) отображения информации и быстрой навигации по меню.
- реализация системы уведомлений пользователи при наличии сбоев в работе приложения, таких как: внезапное исчезновение доступа к интернету; невозможность получения информации с сервера; ошибка в расчёте или работе приложения.
- реализация распараллеливания выполняемых задач, для минимизации времени простоя приложения (избежание ожидания загрузки данных или расчёта необходимого результата перед выводом его на экран). Фактически система должно «понимать», какую информацию будет необходимо предоставить пользователю, и начинать подготовку таких данных для вывода без непосредственной команды пользователя.
- ограничение работы в фоновом режиме, для экономии трафика и ресурсов устройства. 


