---
sourcePath: ru/tracker/api-ref/concepts/entities/comments/patch-comment.md
---
# Редактировать комментарий

Запрос позволяет внести изменения в комментарий [сущности](../about-entities.md).

## Формат запроса {#query}

Перед выполнением запроса [получите доступ к API](../../access.md).

Чтобы изменить комментарий сущности, используйте HTTP-запрос с методом `PATCH`. Параметры запроса передаются в его теле в формате JSON.

```json
PATCH /{{ ver }}/entities/<тип_сущности>/<идентификатор_сущности>/comments
Host: {{ host }}
Authorization: OAuth <OAuth-токен>
{{ org-id }}

{
  "text": "<текст_комментария>",
  "summonees": ["<логины_или_идентификаторы_призванных>"]
}
```

{% include [headings](../../../../_includes/tracker/api/headings.md) %}

{% include [resource](../../../../_includes/tracker/api/resource-entity-comment.md) %}

{% cut "Параметры запроса" %}

**Дополнительные параметры**

Параметр | Описание | Тип данных
-------- | -------- | ----------
isAddToFollowers | Добавить автора комментария в наблюдатели. Значение по умолчанию — `true`. | Логический
notify | Уведомлять пользователей, которые указаны в полях **Автор**, **Ответственный**, **Участники**, **Заказчики** и **Наблюдатели**. Значение по умолчанию — `true`. | Логический
notifyAuthor | Уведомлять автора изменений. Значение по умолчанию — `false`. | Логический
expand | Дополнительная информация, которая будет включена в ответ: <ul><li>`all` — все;</li><li>`attachments` — HTML-разметка комментария;</li><li>`attachments` — вложенные файлы;</li><li>`reactions` — реакции на комментарий.</li></ul> | Строка

{% endcut %}

{% cut "Параметры тела запроса" %}

Тело запроса содержит информацию, необходимую для изменения комментария:

**Дополнительные параметры**

Параметр | Описание | Тип данных
----- | ----- | -----
text | Текст комментария. | Строка
attachmentIds | Список [идентификаторов вложений](../../issues/temp-attachment.md). | Массив строк
summonees | Идентификаторы или логины призванных пользователей. | Массив объектов или строк
maillistSummonees | Список рассылок, призванных в комментарии. | Массив строк

{% endcut %}

> Пример: Редактировать комментарий
>
> - Используется HTTP-метод PATCH.
> - Изменяется текст комментария: «Измененный текст комментария».
> - Изменяется список призванных в комментарии.
> ```
> PATCH /v2/entities/project/<идентификатор_проекта>/comments/31
> Host: {{ host }}
> Authorization: OAuth <OAuth-токен>
> {{ org-id }}
> 
> {
>    "text": "<измененный_текст_комментария>",
>    "summonees": ["<логин_или_идентификатор_пользователя_1>", "<логин_или_идентификатор_пользователя_2>"]
> }
> ```

## Формат ответа {#answer}

{% list tabs %}

- Запрос выполнен успешно

  {% include [answer-200](../../../../_includes/tracker/api/answer-200.md) %}

  Тело ответа содержит информацию о комментарии в формате JSON.

  ```json  
  {
      "self": "{{ host }}/v2/entities/project/6586d6fee2b9ef74********/comments/31", 
      "id": 31, 
      "longId": "65a1ba7b46b9746d********", 
      "text": "Измененный текст комментария.", 
      "createdBy": {
          "self": "{{ host }}/v2/users/19********",
          "id": "19********",
          "display": "Имя Фамилия",
          "cloudUid": "ajeppa7dgp53********",
          "passportUid": "15********"
      },
      "updatedBy": {
          "self": "{{ host }}/v2/users/19********",
          "id": "19********",
          "display": "Имя Фамилия",
          "cloudUid": "ajeppa7dgp53********",
          "passportUid": "15********"
      }, 
      "createdAt": "2024-01-12T22:17:31.176+0000", 
      "updatedAt": "2024-01-12T22:17:31.176+0000", 
      "summonees": [
          {
              "self": "{{ host }}/v2/users/19********",
              "id": "19********",
              "display": "Имя Фамилия",
              "cloudUid": "ajeppa7dgp53********",
              "passportUid": "15********"
          },
          {
              "self": "{{ host }}/v2/users/19********",
              "id": "19********",
              "display": "Имя Фамилия",
              "cloudUid": "ajeppa7dgp32********",
              "passportUid": "12********"
          }
      ],
      "maillistSummonees" : [
          {
              "self" : "{{ host }}/v2/maillists/usertest@test.ru",
              "id" : "usertest@test.ru",
              "display" : "Рассылка от Ивана"
   } 
  ], 
      "version": 1, 
      "type": "standard", 
      "transport": "internal"
  }
  ```

  {% cut "Параметры ответа" %}

  Параметр | Описание | Тип данных
  ----- | ----- | -----
  self | Ссылка на объект комментария. | Строка
  id | Идентификатор комментария. | Число
  longId | Идентификатор комментария в виде строки. | Строка
  text | Текст комментария. | Строка
  textHtml | HTML-разметка комментария. | Строка
  attachments | Вложения. | Строка
  [createdBy](#created-by) | Объект с информацией о создателе комментария. | Объект
  [updatedBy](#updated-by) | Объект с информацией о сотруднике, внесшем последнее изменение в комментарий. | Объект
  createdAt | Дата и время создания комментария в формате:<br/>``` YYYY-MM-DDThh:mm:ss.sss±hhmm ```. | Строка
  updatedAt | Дата и время обновления комментария в формате:<br/>``` YYYY-MM-DDThh:mm:ss.sss±hhmm ```. | Строка
  summonees | Список вызываемых в комментарии пользователей. | Список объектов
  maillistSummonees | Список рассылок, призванных в комментарии. | Список объектов
  version | Версия комментария. Каждое изменение комментария увеличивает номер версии. | Число
  type | Тип комментария:<ul><li>`standart` — отправлен через интерфейс {{ tracker-name }};</li><li>`incoming` — создан из входящего письма;</li><li>`outcoming` — создан из исходящего письма.</li></ul> | Строка
  transport | Способ добавления комментария:<ul><li>`internal` — через интерфейс {{ tracker-name }};</li><li>`email` — через письмо.</li></ul> | Строка

  **Поля объекта** `createdBy` {#created-by}

  Параметр | Описание | Тип данных
  ----- | ----- | -----
  self | Адрес ресурса API, который содержит информацию о пользователе. | Строка
  id | Идентификатор пользователя. | Число
  display | Отображаемое имя пользователя. | Строка
  cloudUid | Уникальный идентификатор пользователя в {{ org-full-name }}. | Строка
  passportUid | Уникальный идентификатор аккаунта пользователя в организации {{ ya-360 }} и Яндекс ID. | Строка
        
  **Поля объекта** `updatedBy` {#updated-by}

  Параметр | Описание | Тип данных
  ----- | ----- | -----
  self | Адрес ресурса API, который содержит информацию о пользователе. | Строка
  id | Идентификатор пользователя. | Число
  display | Отображаемое имя пользователя. | Строка
  cloudUid | Уникальный идентификатор пользователя в {{ org-full-name }}. | Строка
  passportUid | Уникальный идентификатор аккаунта пользователя в организации {{ ya-360 }} и Яндекс ID. | Строка

  {% endcut %}  

- Запрос выполнен с ошибкой

  Если запрос не был успешно обработан, API возвращает ответ с кодом ошибки:

  {% include [error-400](../../../../_includes/tracker/api/answer-error-400.md) %}
  
  {% include [error-404](../../../../_includes/tracker/api/answer-error-404.md) %}
  
  {% include [error-422](../../../../_includes/tracker/api/answer-error-422.md) %}

{% endlist %}