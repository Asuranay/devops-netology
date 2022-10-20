# Игнор лист

# .terraform директорию
**/.terraform/*

# .tfstate файлы с данным разрешением
*.tfstate
*.tfstate.*

# Crash.log и все фалы в названии которых в начале есть Crash и с разрешением .log 
crash.log
crash.*.log

# разрешение файлов .tfvars и .tfvars.json
*.tfvars
*.tfvars.json

# override.tf и override.tf.json файлы и файлы в конце название которых содержит _override.tf и _override.tf.json
override.tf
override.tf.json
*_override.tf
*_override.tf.json

# файл terraform.rc и файлы с разрешением .terraformrc
.terraformrc
terraform.rc