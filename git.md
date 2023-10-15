git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a

git config --global init.defaultBranch main

ssh -T git@github.com

Скорей всего у вас origin ведет на https, такое может быть, если вы проект клонили через
git clone https://github.com/somerepo
а не через
git clone git@github.com:somerepo
Проверьте через
git remote -v
Сменить можно через
git remote set-url origin git@github.com:somerepo
Ответ написан более трёх лет назад
