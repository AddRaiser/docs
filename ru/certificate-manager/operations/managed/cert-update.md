# Обновление сертификата

{{ certificate-manager-name }} запускает процедуру обновления сертификата за 30 дней до окончания срока действия сертификата. Статус сертификата изменится на `Renewing`.

Чтобы обновить сертификат от Let's Encrypt<sup>®</sup>:

{% list tabs %}

- Консоль управления

    1. В [консоли управления]({{ link-console-main }}) выберите каталог, в котором будет создан сертификат.
    1. В списке сервисов выберите **{{ certificate-manager-name }}**.
    1. Выберите в списке сертификат в статусе `Renewing`, который необходимо обновить.
    1. В открывшемся окне в блоке **Проверка прав на домены** будет указана информация для прохождения процедуры проверки прав. Подробнее читайте в разделе [{#T}](../../concepts/challenges.md).
    1. После успешного прохождения проверки прав на домен, статус проверки домена в блоке **Проверка прав на домены** изменится на `Valid`.
    1. После того, как статус проверки прав всех доменов изменится на `Valid`, сертификат будет выпущен и перейдет в статус `Issued`. 

{% endlist %}