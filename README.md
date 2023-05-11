# Задача 1
Опишите кратко, в чём основное отличие полной (аппаратной) виртуализации, паравиртуализации и виртуализации на основе ОС.
# Ответ:
#### 1. При полной виртуализации виртуальные машины позволяют выполнять инструкции с запуском неизмененной ОС полностью изолированным способом.
При паравиртуализации виртуальная машина не реализует полную изоляцию ОС, а скорее предоставляет другой API, который используется, когда ОС подвергается изменениям.
#### 2.Полная виртуализация использует двоичную трансляцию и прямой подход в качестве метода операций.
Паравиртуализация использует гипервызовы во время компиляции для выполнения операций.
#### 3.Полная виртуализация поддерживает все гостевые операционные системы без изменений.
При паровиртуализации гостевая операционная система должна быть модифицирована, и только несколько операционных систем поддерживают ее.
#### 4.При полной виртуализации гостевая операционная система будет выполнять аппаратные вызовы.
При паравиртуализаци, используя драйверы, гостевая операционная система будет напрямую взаимодействовать с гипервизором.

# Задача 2 
Выберите один из вариантов использования организации физических серверов в зависимости от условий использования.
Организация серверов:
- физические сервера, - тип 1
- паравиртуализация,  - тип 2
- виртуализация уровня ОС. - тип 3

Условия использования:
- высоконагруженная база данных, чувствительная к отказу;
- различные web-приложения;
- Windows-системы для использования бухгалтерским отделом;
- системы, выполняющие высокопроизводительные расчёты на GPU.
Опишите, почему вы выбрали к каждому целевому использованию такую организацию.
#### Ответ:
1: Высоконагруженная база данных, чувствительная к сбоям:
Для этого сценария рекомендуется использовать виртуальную машину типа 1(физические сервера), также известную как гипервизор с открытым исходным кодом.;
Виртуальные машины типа 1/ запускаются непосредственно на физическом оборудовании без необходимости в операционной системе хоста. Они обеспечивают высокую;
производительность и/ надежность,что крайне важно для высоконагруженной базы данных, чувствительной к сбоям.
2: Различные веб-приложения:
Для размещения веб-приложений может подойти виртуальная машина типа 2 (паравиртуализация) или традиционное решение для виртуализации. Виртуальные машины типа 2\
работают поверх основной операционной системы\
3: Системы Windows для бухгалтерии: \
Виртуализация на уровне операционной системы, также известная как контейнеризация, может быть использована для рабочей нагрузки типа 3, включающей системы Windows для бухгалтерии. Контейнеры обеспечивают облегченную виртуализацию, позволяя нескольким изолированным экземплярам операционной системы запускаться на одном хосте.\
Он хорошо подходит для сценариев, где требуется несколько экземпляров одной и той же операционной системы\
4: Системы, выполняющие высокопроизводительные вычисления на графическом процессоре:
Для рабочих нагрузок, связанных с высокопроизводительными вычислениями на графическом процессоре, рекомендуется использовать виртуальную машину типа 1 \
(физические сервера) с возможностями сквозного доступа на графическом процессоре. Это обеспечивает прямой доступ к графическому процессору из виртуальной машины.

# Задача 3
Выберите подходящую систему управления виртуализацией для предложенного сценария. Детально опишите ваш выбор.
Сценарии:
1.100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно Windows based-инфраструктура, требуется реализация программных балансировщиков нагрузки, репликации данных и автоматизированного механизма создания резервных копий.
#### Ответ: Для этого сценария популярной и многофункциональной системой управления виртуализацией является VMware vSphere. Он предоставляет комплексные возможности управления виртуальными машинами, включая подготовку, мониторинг и автоматизацию. vSphere поддерживает виртуальные машины как Linux, так и Windows, что позволяет эффективно управлять всей инфраструктурой и контролировать ее.
2.Требуется наиболее производительное бесплатное open source-решение для виртуализации небольшой (20-30 серверов) инфраструктуры на базе Linux и Windows виртуальных машин.
#### Ответ: Инфраструктура, в основном, на базе Windows, требует программных средств балансировки нагрузки, репликации данных и автоматического резервного копирования.
Для этого сценария Microsoft Hyper-V является подходящим выбором. Hyper-V - это собственный гипервизор для Windows, предоставляющий надежные возможности виртуализации. Он хорошо интегрируется с экосистемой Windows и предлагает такие функции, как балансировка нагрузки программного обеспечения, репликация данных и интеграция резервного копирования с такими инструментами, как Windows Server Backup. Hyper-V также поддерживает виртуальные машины как Linux, так и Windows.
3. Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации Windows-инфраструктуры.
#### Ответ: : Бесплатное, максимально совместимое и производительное решение для виртуализации небольшой инфраструктуры на базе виртуальных машин Linux и Windows.
В этом случае хорошо подойдет Proxmox VE (виртуальная среда). Proxmox VE - это платформа виртуализации с открытым исходным кодом, которая сочетает в себе KVM (виртуальную машину на основе ядра) для виртуализации Linux и QEMU для виртуализации Windows. Он предлагает удобный веб-интерфейс управления и поддерживает такие функции, как оперативная миграция, высокая доступность, резервное копирование и восстановление и многое другое.
4.Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах Linux.
#### Ответ: Рабочая среда для тестирования программных продуктов на нескольких дистрибутивах Linux.
Для создания среды тестирования в нескольких дистрибутивах Linux вы можете рассмотреть возможность использования VirtualBox. VirtualBox - это бесплатная платформа виртуализации с открытым исходным кодом, которая поддерживает различные операционные системы, включая дистрибутивы Linux.
Он предоставляет возможность создавать виртуальные машины и управлять ими в целях тестирования и предлагает такие функции, как моментальные снимки, сетевые опции и простую настройку

# Задача 4
Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких систем управления виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков и проблем. Если бы у вас был выбор, создавали бы вы гетерогенную среду или нет? Мотивируйте ваш ответ примерами.
#### Ответ: Сложность: Управление несколькими платформами виртуализации создает сложности с точки зрения администрирования, мониторинга и устранения неполадок. Каждая платформа может иметь свои собственные интерфейсы управления, параметры конфигурации и требования к совместимости. Такая сложность может привести к увеличению административных накладных расходов и потенциальной путанице для ИТ-персонала.
Навыки и обучение: Работа с несколькими платформами виртуализации требует опыта и знаний в каждой системе.
Интеграция и совместимость: Различные платформы виртуализации могут иметь разный уровень взаимодействия и совместимости. Это может препятствовать плавной интеграции виртуальных машин на разных платформах, влияя на распределение ресурсов, оперативную миграцию и управление рабочей нагрузкой.

Чтобы минимизировать риски и проблемы в гетерогенной среде виртуализации, можно предпринять следующие меры:
-Стандартизация: Установите общие стандарты и лучшие практики для различных платформ виртуализации, чтобы упростить управление и свести к минимуму сложность. Это\
включает в себя согласованные соглашения об именовании, сетевые конфигурации и процедуры развертывания.
-Мониторинг и отчетность: Внедрите централизованные решения для мониторинга и отчетности, которые могут обеспечить видимость всей гетерогенной среды виртуализации.\
Если есть выбор, создание однородной среды виртуализации (с использованием единой системы управления виртуализацией), как правило, предпочтительнее гетерогенной среды. Это упрощает управление, снижает сложность и оптимизирует операции.
