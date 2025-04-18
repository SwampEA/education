# Задания Кирилла Эдуардовича

<details><summary>Задание 1</summary>

```
# Local .terraform directories
**/.terraform/*
Локальные каталоги .terraform

# .tfstate files
*.tfstate
*.tfstate.*
Игнорирует все файлы с расширением .tfstate.
Игнорирует все файлы, которые начинаются с .tfstate. и имеют любое расширение после точки.

# Crash log files
crash.log
crash.*.log
Игнорирует файлы crash.log и игнорирует файлы которые начинаются на crash. и заканчиваются на .log

# Exclude all .tfvars files, which are likely to contain sensitive data, such as
# password, private keys, and other secrets. These should not be part of version 
# control as they are data points which are potentially sensitive and subject 
# to change depending on the environment.
*.tfvars
*.tfvars.json
# Исключите все файлы .tfvars, которые могут содержать конфиденциальные данные, такие как
# пароли, закрытые ключи и другие секреты. Они не должны быть частью управления версиями 
#, поскольку они являются потенциально конфиденциальными данными и могут 
# изменяться в зависимости от среды.
игнорировать все файлы с расширением .tfvars .tfvars.json

# Ignore override files as they are usually used to override resources locally and so
# are not checked in
override.tf
override.tf.json
*_override.tf
*_override.tf.json
# Игнорируйте файлы переопределения, поскольку они обычно используются для локального переопределения ресурсов и поэтому не регистрируются
игнорировать файлы, а также их расширения override.tf override.tf.json 

# Ignore transient lock info files created by terraform apply
.terraform.tfstate.lock.info
# Игнорировать временные файлы информации о блокировке, созданные terraform apply.
игнорировать файл .terraform.tfstate.lock.info

# Include override files you do wish to add to version control using negated pattern
# !example_override.tf
# Включите файлы переопределений, которые вы хотите добавить в систему контроля версий, используя отрицающий шаблон
исключает игнорирование example_override.tf

# Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
# example: *tfplan*
# Включите файлы tfplan, чтобы игнорировать результаты выполнения команды: terraform plan -out=tfplan
файлы с расширением или именем tfplan игнорируются 

# Ignore CLI configuration files
.terraformrc
terraform.rc
# Игнорировать конфигурационные файлы CLI 
игнорировать файлы .terraformrc и terraform.rc
```

</details>

<details><summary>Задание 2</summary>

#### Cклонировал репозиторий с исходным кодом [terraform](https://github.com/hashicorp/terraform.git) 
---
Какому тегу соответствует коммит `85024d3`?
-
командой `git show 85024d3` нашел нужный тег

```
85024d3100 (tag: v0.12.23) v0.12.23
```
Сколько родителей у коммита `b8d720`? Напишите их хеши.
-

помощью команды `git show b8d720` нахожу 2 родительских коммита следовательно это мержкоммит 

```
56cd7859e0 perent 1
9ea88f22fc perent 2
```

Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами `v0.12.23 и v0.12.24`.
-
командой `git log --oneline v0.12.23 v0.12.24`
```
33ff1c03bb (tag: v0.12.24) v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
```

Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы)
-
командой `git log -S"func providerSource"` нашел коммиты в которых были добавлены или удалены строки, содержащие `func providerSource`
```
5af1e6234ab6da412fb8637393c5a17a1b293663
8c928e83589d90a031f811fae52a81be7153e82f
```
С помощью команды `git show` нахожу добавленую строку `func providerSource(services *disco.Disco)` в первом коммите `8c928e83589d90a031f811fae52a81be7153e82f`

Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.
-
командой `git log --oneline -S"globalPluginDirs"` нахожу коммиты в которых изменения функции `globalPluginDirs`
```
7c4aeac5f3
65c4ba7363
125eb51dc4
22c121df86 
7c7e5d8f0a 
35a058fb3d
c0b1761096
8364383c35 
```

Кто автор функции `synchronizedWriters`?
-
Чтобы найти автора функции нам нужен коммит с созданием функции`synchronizedWriters` 
Нахожу коммиты с изменениями этой функции `git log --oneline -S"synchronizedWriters"`
``` 
bdfea50cc8 remove unused
fd4f7eb0b9 remove prefixed io
5ac311e2a9 main: synchronize writes to VT100-faker on Windows
```
смотрю первый коммит и нахожу автора и его функцию `git show 5ac311e2a9`
`Author: Martin Atkins <mart@degeneration.co.uk>`

</details>

<details><summary>Задание 3 (Работа в тенрминале. Лекция 1)</summary>

### [Задание 3 Работа в терминале](https://github.com/netology-code/sysadm-homeworks/blob/devsys10/03-sysadmin-01-terminal/README.md)

Какой переменной можно задать длину журнала `history`, и на какой строчке `manual` это описывается?
-
В `man bash` описание переменных которая задает длину журнала `history` начинается на строке `3035`
С помощью двух переменных можно настроить длину журнала:
- `HISTSIZE`- опредлеляет, сколько команд сохраняется для текущей сессии
- `HISTFILESIZE` - опредуляет, сколько команд сохраняется в файле истории `~/.bash_history` между сессиями

Что делает директива `ignoreboth` в bash?
-
`HISCONTROL=ignoreboth` - игнорировать и дубликаты, и команды с пробелом

В каких сценариях использования применимы скобки `{}`, на какой строчке `man bash` это описано?
-
строчка 901 в `man bash` `brace Expansion`
`{}` Расширение фигурных скобок служит: 
- генерации последовательности `{1..10}`
- комбинирование строк `file{1,2,3}.txt`
- вложенные скобки `{a,b{1,2},c}`

С учётом ответа на предыдущий вопрос подумайте, как создать однократным вызовом touch 100 000 файлов. Получится ли аналогичным образом создать 300 000 файлов? Если нет, то объясните, почему.
-
с помощью команды `touch file {1..100000}.txt` можно будет создать 100000 файлов, но 300 уже не получится, так как ограничение на последовательное создание файлов не даст это сделать и получим 
`bash: /usr/bin/touch: Argument list too long`

В man bash поищите по /\[\[. Что делает конструкция `[[ -d /tmp ]]`?
-
- `[[ ... ]]` — это условное выражение в Bash, которое возвращает true (0) или false (1) в зависимости от результата проверки.
- `-d` — это оператор, который проверяет, является ли указанный путь директорией.
- `/tmp` — это путь, который проверяется.

Сделайте так, чтобы в выводе команды type -a bash первым стояла запись с нестандартным путём, например, bash is... Используйте знания о просмотре существующих и создании новых переменных окружения, обратите внимание на переменную окружения PATH.
Другие строки могут отличаться содержимым и порядком. В качестве ответа приведите команды, которые позволили вам добиться указанного вывода, или соответствующие скриншоты.
- 
скопировал бинарный файл `bash` в дерикторию `/tmp/new_path_directory/bash`
добавил переменную в PATH `export PATH=/tmp/new_path_directory:$PATH`
и проверил `type -a bash` первым в списке новая дериктория с переменной 

Чем отличается планирование команд с помощью `batch` и `at`?
-
- `at` выполняет команду в указанное время
- `batch` выполняет задачи, когда нагрузка на систему становится низкой
</details>


<details><summary>Задание 4 (Работа в тенрминале. Лекция 2)</summary>

### [Задание 4 Работа в терминале. Лекция 2](https://github.com/netology-code/sysadm-homeworks/blob/devsys10/03-sysadmin-02-terminal/README.md)

Какого типа команда `cd`? Попробуйте объяснить, почему она именно такого типа: опишите ход своих мыслей и поясните, если считаете, что она могла бы быть другого типа.
-
Команда `cd` shell builtin, встроенная командная оболочка и она не использует стандартные потоки ввода-вывода stdin/stdout/stderr

1. Не выводит данные 
2. `cd` изменяет текущую рабочую директорию процесса shell, а не передаёт данные через потоки
3. Ошибки cd выводятся в stderr

Какая альтернатива без pipe для команды `grep <some_string> <some_file> | wc -l`?
-
можно заменить командой `grep <some_string> -c <some_file>` добавив флаг `-с`

Какой процесс с PID 1 является родителем для всех процессов в вашей виртуальной машине Ubuntu 20.04?
-
Родителем всех процессов является `systemd(1)` или `/sbin/init splash`

Как будет выглядеть команда, которая перенаправит вывод stderr ls на другую сессию терминала?
-
`ls /несуществующая_дериктория" 2> /dev/pts/"номер терминала"` номер терминала узнаем `tty`
цифра `2` перед перенаправлением, направит `stderr` на другой терминал
`1` направит `stdout`
`&`направит `stdout` и `stderr`

Получится ли одновременно передать команде файл на stdin и вывести её stdout в другой файл? Приведите работающий пример.
-
grep "текст" < input.txt > matches.txt
греп ищет текст в файле input.txt и результаты поиска сохраняет в matches.txt

Получится ли, находясь в графическом режиме, вывести данные из PTY в какой-либо из эмуляторов TTY? Сможете ли вы наблюдать выводимые данные?
-

Получится 

- открываем виртуальную консоль ctrl+alt+F2...F12
- можно передать выводимые данные с PTY на TTY `echo "hello from PTY" > /dev/tty2`

Выполните команду `bash 5>&1`. К чему она приведёт? Что будет, если вы выполните `echo netology > /proc/$$/fd/5`? Почему так происходит?
-
командой `bash 5>&1` я создаю дочерний процесс bash `5>` и связываю его с stdout shell `&1`
`echo netology > /proc/$$/fd/5` эта команда выводит мне вывод команды `echo netology` таким образом проверил работоспособность

Получится ли в качестве входного потока для pipe использовать только stderr команды, не потеряв отображение stdout на pty?
Напоминаем: по умолчанию через pipe передаётся только stdout команды слева от | на stdin команды справа. Это можно сделать, поменяв стандартные потоки местами через промежуточный новый дескриптор, который вы научились создавать в предыдущем вопросе.
-
`ls несуществющий_файл существующий_файл | grep "no such`
вывод stdout существующего файла на терминале не отображается
чтобы оставить stdout на PTY поменяем потоки местами через новый дескриптор 5
`ls несуществующий_файл существующий_файл 5>&1 1>&2 2>&5 | grep "No such"` тогда stdout останется 

