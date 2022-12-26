# ✅Лабораторная работа №3
Цель работы: изучить принципы организации взаимодействия прикладных программ с помощью протоколов электронной почты SMTP и POP3 в режиме симуляции Cisco Packet Tracer.

Индивидуальное задание

Составляем сеть со следующей топологией:
![image](https://user-images.githubusercontent.com/82199938/209545617-e93d82ee-978d-4925-aa17-6a3aea840e9f.png)


 ![image](https://user-images.githubusercontent.com/82199938/209545775-4ae7130b-cdad-4da1-bb3f-2307ee7ad154.png)

Рис. 2. Пример настройки ПК — задание IP-адреса и маски сети
 ![image](https://user-images.githubusercontent.com/82199938/209545788-604eee2b-9051-475f-9eaf-98de0fd6f10c.png)

Рис. 3. Пример настройки ПК — задание IP-адреса DNS-сервера


Настроим DNS-сервер. Сначала подключим службу DNS на сервере 192.168.6.7 и добавим две ресурсных записи: vladislav.ru и nuriev.ru.
 ![image](https://user-images.githubusercontent.com/82199938/209545827-26e59c1a-95f8-4494-b2a5-cade0999d602.png)

Рис. 4. Настройка DNS-сервера

Сконфигурируем почтовый сервер 192.168.6.7 с поддержкой SMTP- и POP3-сервера и создадим учетную запись одного пользователя.
 ![image](https://user-images.githubusercontent.com/82199938/209545842-07575cfe-531e-4093-bd0c-2992d339d45d.png)

Рис. 5. Создание учетной записи пользователя на домене vladislav.ru

Настроим на хосте 192.168.6.2 (PC0) клиент электронной почты:
 ![image](https://user-images.githubusercontent.com/82199938/209546310-b253d778-675c-43f4-ba26-c3e1e1c252a5.png)

Рис. 6. Настройка почтового сервиса на PC0


Аналогично создаем на втором сервере учетную запись на домене nuriev.ru:
 ![image](https://user-images.githubusercontent.com/82199938/209545861-ee837282-429b-4c9a-a802-f003acd5bc98.png)

Рис. 7. Создание учетной записи пользователя на домене nuriev.ru


И настраиваем на втором хосте 192.168.6.3 (PC1) почтовый сервис.
 ![image](https://user-images.githubusercontent.com/82199938/209545877-17bef93b-d2b3-4fc3-a7d4-468302bbd6f6.png)

Рис. 8. Настройка почтового сервиса на PC1


В режиме симуляции настроим отображение в списке событий только пакетов протоколов SMTP и POP3.
 
![image](https://user-images.githubusercontent.com/82199938/209545933-ca3f7422-991f-4cd5-be3b-39650352b669.png)

Рис. 9. Настройка отображаемых в списке событий протоколов
Отправим письмо от vlad к slava:
 ![image](https://user-images.githubusercontent.com/82199938/209545957-05f88d71-cdef-43f3-8007-5ee6e34090a6.png)

Рис. 10. Письмо, отправляемое от vlad к slava

После нажатия кнопки Send начинается отправка письма. PC1 формируется пакет SMTP:
 ![image](https://user-images.githubusercontent.com/82199938/209545962-d4e1c008-a5f2-4098-9d4e-52ad450bab91.png)

Рис. 11. Пакет SMTP, сформированный на хосте 192.168.6.3
Через два коммутатора пакет доходит к серверу 192.168.6.5:
 ![image](https://user-images.githubusercontent.com/82199938/209545985-4a38fb88-7d20-4090-ad46-8841a0a6ba32.png)

Рис. 12. Снимок рабочей области
После этого по тому же пути приходит SMTP-ответ хосту. Содержимое этого пакета показано на рис. 13. Вся история событий приведено на рис. 14.
 ![image](https://user-images.githubusercontent.com/82199938/209546019-a35b628b-65ed-4457-982b-28335a279538.png)

Рис. 13. Содержимое SMTP-ответа хосту 192.168.6.3

![image](https://user-images.githubusercontent.com/82199938/209546048-19f0bdfe-6801-4996-b4b9-b38e4c4a258c.png)

 
Рис. 14. История событий

![image](https://user-images.githubusercontent.com/82199938/209546188-c28ff386-739c-4dc5-b783-d04354fbb76b.png)

Рис. 15. История событий

Изначально сформировавшийся на PC0 пакет POP3:

![image](https://user-images.githubusercontent.com/82199938/209546150-57cd8294-4716-482f-a228-182caae31a1f.png)

 
Рис. 16. Содержимое протокола, сформированного на PC0

Пакет, вернувшийся на хост от сервера, показан на рис. 17:
![image](https://user-images.githubusercontent.com/82199938/209546208-6f6ea3bc-97dc-4d66-9dbc-bce98a5869c3.png)

 
Рис. 17. Ответ сервера хосту-получателю письма


![image](https://user-images.githubusercontent.com/82199938/209546233-c19617d0-5b6e-4dd4-96d4-9266cd376aec.png)



Теперь письмо можно прочитать на хосте PC0:
 
Рис. 18. Полученное письмо
