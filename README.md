# A sandbox repository for Prototype

The project build supports building with JDK [11..17] and produces the byte-code compatible with `Java 11`.
Download [Java 17](https://www.oracle.com/java/technologies/downloads/#java17) prior to using this repository.

---

## Git

This project uses `Git` as a Version Control System (VCS).
Download and install the latest version of [Git](https://git-scm.com/download/) prior to using this repository.

### Clonning a repository

Following assumes that the respository accessed via SSH and SSH access credentials already configured.
```
git clone 
```

### Updating a repository

Regularly, the repository updates are to be done using `pull` with an additional `--rebase` flag as following:
```
git pull --rebase
```

---

## Build

This repository uses `Gradle` to organize the builds.
[Gradle](https://gradle.org/install/) does not need to be installed prior to using the repository,
it will be downloaded automatically during the build.

### Build steps

To build and package the sources:
```(Gradle)
gradlew clean assemble
```

To build the sources and tests, but not to run tests:
```(Gradle)
gradlew clean build testClasses -x test
```

To build and package the sources, build and run tests:
```(Gradle)
gradlew clean build -Dorg.gradle.parallel=false
```

### Test steps

To run unit tests:
```(Gradle)
gradlew test -Dorg.gradle.parallel=false
```

### Tracking third-party dependencies
This can be tracked per-project basis as following:
```(Gradle)
gradlew :<project>:dependencies --configuration runtimeClasspath
```

### Gradle Build Reference

Basic build task dependency reflected at the following diagram:

![Relationships between Gradle tasks](https://docs.gradle.org/current/userguide/img/javaPluginTasks.png)

For more information check: [Gradle Java Plugin Reference](https://docs.gradle.org/current/userguide/java_plugin.html)

---

## BitBucket

### Editing a file

You’ll start by editing this README file to learn how to edit a file in Bitbucket.

1. Click **Source** on the left side.
2. Click the README.md link from the list of files.
3. Click the **Edit** button.
4. Delete the following text: *Delete this line to make a change to the README from Bitbucket.*
5. After making your change, click **Commit** and then **Commit** again in the dialog. The commit page will open and you’ll see the change you just made.
6. Go back to the **Source** page.

### Creating a file

Next, you’ll add a new file to this repository.

1. Click the **New file** button at the top of the **Source** page.
2. Give the file a filename of **contributors.txt**.
3. Enter your name in the empty file space.
4. Click **Commit** and then **Commit** again in the dialog.
5. Go back to the **Source** page.

Before you move on, go ahead and explore the repository. You've already seen the **Source** page, but check out the **Commits**, **Branches**, and **Settings** pages.

### Next steps

Now that you're more familiar with your Bitbucket repository, go ahead and add a new file locally. You can [push your change back to Bitbucket with SourceTree](https://confluence.atlassian.com/x/iqyBMg), or you can [add, commit,](https://confluence.atlassian.com/x/8QhODQ) and [push from the command line](https://confluence.atlassian.com/x/NQ0zDQ).

---


# Домашнее задание GIT

#### Адрес репозитория: [https://github.com/m65v19/git_task_01/](https://github.com/m65v19/git_task_01/) ####
<h6>Делал: Климин Василий, МЕНА-130701</h6>

### Задание №0

![Результат](docs/mynameandemail.png "Уже сконфигурировано")

### Задание №1

![Часть1](docs/01-k.png "Всё не влезло, прошу прощения")
![Часть2](docs/02-k.png "Всё не влезло, прошу прощения")

***Pull Request №1*** [https://github.com/m65v19/git_task_01/pull/1](https://github.com/m65v19/git_task_01/pull/1)

***Pull Request №2*** [https://github.com/m65v19/git_task_01/pull/2](https://github.com/m65v19/git_task_01/pull/2)

---
Отвечая на доп. вопрос ***"Какие операции нужно совершить, если не использовать Pull Request (полный
набор команд от начала и до конца)?"***

Ответ: Можно переключиться на ветку Main и сделать merge изменений:
```bash
git checkout main
git merge 
task1-name 
git push
```

### Задание №2

![Часть1](docs/01-k2.png "Всё не влезло, прошу прощения")
![Часть2](docs/02-k2.png "Всё не влезло, прошу прощения")

***Beтвь №1*** [https://github.com/m65v19/git_task_01/tree/task2-klimin](https://github.com/m65v19/git_task_01/tree/task2-klimin)

***Beтвь №2*** [https://github.com/m65v19/git_task_01/tree/task2-ovakimyan](https://github.com/m65v19/git_task_01/tree/task2-ovakimyan)

---
Отвечая на вопросы 
1. ***Объяснить почему не удалось запушить ветку***

![pic1](docs/merge%20conflict.png "Обратите внимания на вывод комманды git push")

Контекст: Перед пушем ветви, было необходимо совершить сл. шаги:
1. Создать свою ветку, сделать ***commit*** с новым файлом и совершить ***push***
2. ***checkout*** на ветвь ***main***, ***commit*** и ***push*** любого изменения
3. Вернуться на свою ветвь и выполнить ***rebase*** от ветви ***main***

Процедура ***rebase*** представляет из себя операцию накладывания найденных коммитов поверх других.
В данном случае мы ответвились от основной ветви ***main*** и от последнего на тот момент коммита продолжили работу в новой ветке ***new branch***.
При этом же, совершили изменения в ***main*** уже после разветвления, соответственно ***main*** уже указывала на новый коммит. Локальный ***main*** не совпадал с указателем в удалённом репозитории.

![explanation](docs/explanation.jpg "Код в локальном репозитории оказался несовместим с кодом в удалённом репозитории.
")

Код в локальном репозитории оказался несовместим с кодом в удалённом репозитории.


2. ***Найти способы запушить ветку без лишних изменений, т.е. не должно появиться ни одного лишнего коммита (подсказка: есть два способа)***

Решение №1

```bash
git pull
git push
```

Решение №2: Сделать ***merge*** веток.

### Задание №3

***Beтвь с заданием*** [https://github.com/m65v19/git_task_01/tree/task3-klimin](https://github.com/m65v19/git_task_01/tree/task3-klimin)

Задание было выполнено в интерактивном режме, используя[^1].
```bash
git rebase -i
```

![img1](docs/01-k3.png)
![img2](docs/02-k3.png)

[^1]: Не удивляйтесь двойному ***revert***. Было интересно посмотреть.


    
