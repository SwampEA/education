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

