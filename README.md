UML диаграммы для сервиса доставки еды. Сервис сотрудничает с несколькими ресторанами, которые выставляют свое меню на сайте доставки еды. Сервис отвечает за работу с клиентами и с курьерами(в его задачи входит только доставка заказа), задача ресторана - приготовить заказ и передать его курьеру. Коммуникация между ними происходит за счёт менеджеров, которые контролируют весь процесс выполнения заказа. Они и являются главными сотрудниками сервиса.
Процесс создания заказа: пользователь выбирает понравившиеся ему ресторан, по меню выбирает блюда для заказа, вводит личные данные (ФИО, адрес и номер телефона), далее производит оплату. После оплаты ресторан начинает готовить. После завершения приготовления собирает заказ и передаёт его курьеру. Тот доставляет его на указанный ранее клиентом адрес.

диаграмма деятельности:
Система обработки заказа начинается со входа пользователя в приложение. Система предоставляет список ресторанов, далее, после выбора клиента, предоставляет меню ресторана. Если пользователь не смог определиться с выбором блюд система возвращает его к списку предприятий, иначе высылает запрос на ввод личных данных. Далее производится оплата заказа(если оплата не прошла, то клиента возвращают на предыдущий шаг).  Система оправляет заказ в ресторан, начинает отслеживать статус заказа(в обработке рестораном/готовится/готов/передан в доставку) и передает данные по нему курьеру. Далее отслеживает доставку. После доставки закрывает заказ и архивирует его. Система обработки заказа окончена.

диаграмма классов:
На диаграмме представлены 5 классов - пользователь, менеджер, курьер, ресторан, банк, а также модуль приготовления заказа. Разберем систему на примере класса менеджер. Его поля - ID (внутренний номер в системе, который является публичным), его методы: обработка заказа, контроль за приготовлением заказа, контроль доставки заказа. Менеджер взаимосвязан с классом пользователь (каждый пользователь связан только с одним менеджером, но менеджер может быть связан с 1 и более пользователями), с классом курьер (каждый курьер связан только с одним менеджером, но менеджер может быть связан с 1 и более курьерами), с классом ресторан(каждый ресторан связан с 1 и более менеджерами, менеджер связан с 1 и более ресторанами).


