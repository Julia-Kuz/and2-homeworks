# Домашнее задание к занятию «2.1. Обработка событий в Android»

В качестве результата пришлите ссылку на ваш GitHub-проект в личном кабинете студента на сайте [netology.ru](https://netology.ru).

**Важно**: ознакомьтесь со ссылками, представленными на главной странице [репозитория с домашними заданиями](../README.md).

**Важно**: если у вас что-то не получилось, то оформляйте Issue [по установленным правилам](../report-requirements.md).

## Как сдавать задачи

1. Откройте ваш проект с предыдущего ДЗ
1. Сделайте необходимые коммиты
1. Сделайте пуш (удостоверьтесь, что ваш код появился на GitHub)
1. Ссылку на ваш проект отправьте в личном кабинете на сайте [netology.ru](https://netology.ru)
1. Задачи, отмеченные, как необязательные, можно не сдавать, это не повлияет на получение зачета (в этом ДЗ все задачи являются обязательными)

## Задача Like, Share

### Легенда

Поскольку вы делаете приложение с гораздо бóльшими функциональными возможностями, чем делают лекторы 🙂, то придётся дописать часть логики (по отношению к лекции).

Напоминаем, ваше приложение должно выглядеть вот так:

![](pic/layout.png)

### Задача

Что нужно сделать:
1. При клике на like должна меняться не только картинка, но и число рядом с ней: лайкаете - увеличивается на 1, дизлайкаете - уменьшается на 1
1. При клике на share должно увеличиваться число рядом (10 раз нажали на share - +10)
1. Добавить логику с тысячами: если количество лайков, share или просмотров перевалило за 999, то должно отображаться 1K и т.д., а не 1000 (при этом предыдущие функции должны работать: если у поста было 999 лайков и вы нажали like, то должно стать 1К, если убрали лайк, то снова 999)

Обратите внимание:
1. 1.1К отображается по достижении 1100
1. После 10К сотни перестают отображаться
1. После 1M сотни тысяч отображаются в формате 1.3M
1. Задумайтесь о том, что стоит это вынести в какую-то функцию, а не хранить эту логику в `Activity`

Опубликуйте изменения в вашем проекте на GitHub. Удостоверьтесь, что apk собирается с помощью GitHub Actions и при установке в эмуляторе приложение работает корректно.

В качестве результата пришлите ссылку на ваш GitHub-проект в личном кабинете студента на сайте [netology.ru](https://netology.ru).

## Задача Parent Child

### Легенда

Исследование поведения системы - достаточно важная часть работы разработчика.

До этого мы устанавливали `OnClickListener` только на один View.

Интересно, что будет, если мы установим разные Listener'ы на View, которые "пересекаются"? Например, на `ConstraintLayout`, который содержит все остальные View и на кнопку `Like`?

### Задача

Что нужно сделать:
1. Установите обработчики `OnClickListener` на `binding.root` и на `binding.like`
1. Поставьте внутрь обработчиков точки остановки
1. Запустите приложение в режиме отладки
1. Кликните на кнопку Like, на кнопку с тремя точками (на ней пока нет обработчика), на текст, на аватар
1. Установите обработчик `OnClickListener` на аватар и кликните на нём снова

В качестве результата пришлите ответы на следующие вопросы в личном кабинете студента на сайте [netology.ru](https://netology.ru):
1. Какой из обработчиков (или оба) сработали при клике на кнопку Like?
1. Сработал ли обработчик на `binding.root` при клике на кнопке с тремя точками?
1. Сработал ли обработчик на `binding.root` при клике на тексте?
1. Сработал ли обработчик на `binding.root` при клике на аватар (до установки на avatar собственного обработчика)?
1. Сработал ли обработчик на `binding.root` при клике на аватар (после установки на avatar собственного обработчика)?

Попробуйте выявить закономерность: когда срабатывает обработчик на контейнере, а когда - нет.

**Важно**: не нужно мёржить эти "тесты" в master и заливать на GitHub.