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


 


