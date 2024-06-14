Код библиотек, пригодных для использования в сторонних приложениях (например, /pkg/mypubliclib). Другие проекты будут импортировать эти библиотеки, ожидая их автономной работы, поэтому стоит подумать дважды, прежде чем класть сюда какой-нибудь код. Обратите внимание, что использование директории internal - более оптимальный способ гарантировать что ваши внутренние пакеты, не будут импортированы, потому что это обеспечивает сам Go. Директория /pkg - всё еще хороший путь дать понять, что код в этой директории могут безопасно использовать другие. Статья I'll take pkg over internal в блоге Трэвиса Джеффери (Travis Jeffery) предоставляет хороший обзор директорий pkg и internal и когда есть смысл их использовать.

Это так же способ группировать код на Go в одном месте, когда ваша корневая директория содержит множество не относящихся к Go компонентов и директорий, что позволит облегчить работу с разными инструментами Go (как упомянуто в этих выступлениях: Best Practices for Industrial Programming с GopherCon EU 2018, GopherCon 2018: Kat Zien - How Do You Structure Your Go Apps и GoLab 2018 - Massimiliano Pippi - Project layout patterns in Go).

Ознакомьтесь с директорией /pkg, если хотите увидеть, какие популярные репозитории используют этот макет для организации проекта. Это часто используемый макет, но он не общепринятый, а некоторые в сообществе Go и вовсе не рекомендует его использовать.

Вы можете не использовать эту директорию, если проект совсем небольшой и добавление нового уровня вложенности не несет практического смысла (разве что вы сами этого не хотите). Подумайте об этом, когда ваша корневая директория начинает слишком сильно разрастаться, особенно, если у вас много компонентов, написанных не на Go.