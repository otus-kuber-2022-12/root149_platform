# root149_platform
root149 Platform repository
описание проделанных работ
0. то что вылезло :-)
  0.1. стр 5 git push --- не отработает, нужно git push --set-upstream origin kubernetes-prepare, тк данного бранча пока нету (если его напилить ручками, запулить в локальный реп, то все, всеравно не пойдет)
  0.2. git push --set-upstream origin kubernetes-prepare, и все равно не заработает. гитхаб отключил авторизацию по логину/паролю
      Username for 'https://github.com': root149
      Password for 'https://root149@github.com': 
      remote: Support for password authentication was removed on August 13, 2021.
      remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
      fatal: Authentication failed for 'https://github.com/otus-kuber-2022-12/root149_platform.git/'
      в общем виде все ответы тут
        https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git
      выдержка
        1. ставим githubcli всесте со всем мусором от гитхаба
        2. ставим Git Credential Manager (мусора по меньше)
        3. настраиваем авторизацию по ssh ключам
      я иду по пути 2
   0.3. подготовлены и настроены minikube,docker,git
   0.4. взглянул на k9s очень интересный интерфейс к k8s 
1. подготовлен Dockerfile для web приложения
  1.1 тк за основу взят чистый nginx то пришлось подкорректировать права на запись в директории /var 
  1.2 тк произведена смена порта и пути по умолчанию подкорректирован файл default.conf

2. произведена подготовка манифееста/yaml файла для запуска микросервиса в kuberbetes
  2.1. добавлены дополнительные описания вольюмов
  2.2. добавлены описания init контейнера, рабочая нагрузка и init контейнер связаны между собой через подготовленный вольюм в п.2.1.
3. выполнено задание со *, в параметрах старта контейнера требовалось указать переменные (адреса остальных микросервисов в составе приложения)
