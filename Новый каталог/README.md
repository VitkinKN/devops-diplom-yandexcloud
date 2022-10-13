# Deploy сайта в проекте Wordpress на целевой хост

## Настройка Variables GitLab 
В разделе `GitLab Project > Settings > CI/CD > Variables` создаем переменные:
 - **`STAGE_SERVER_IP`** – содержит IP-адрес целевого сервера. Этот IP-адрес используется GitLab Runner для установления SSH-подключения к целевому серверу.
 - **`STAGE_SERVER_USER`** — содержит пользователя, используемого при открытии сеанса SSH.
 - **`STAGE_ID_RSA`** – содержит закрытый ключ SSH, используемый во время сеанса SSH.\
 ![img](../Images/gitlab_variables.png)
## Подготовка GitLab к автоматическому развертыванию
1. Создаем наш проект wordpress.
2. Загружаем в него наш файл `.gitlab-ci.yml` и папку с темой `progect`.\
![img](../Images/gitlab_rep.png)
3. При необходимости меняем значение **`WORDPRESS_THEME_NAME`** в файле `.gitlab-ci.yml` на название той темы, которую хотим поставить.
3. Подготавливаем `Runner` для работы с нашем проектом.

После завершения настройки, GitLab CI/CD автоматически развернет новую тему для WordPress.
 - **Развёрнутый сайт на хосте**

![img](../Images/gitlab_pipeline.png)

 - **Измененная тема на нашем сайте Wordpress**

![img](../Images/change_themes.png)

Все действия при выполнении CI/CD, описаны в комментариях в файле `.gitlab-ci.yml`.
