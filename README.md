#＃＃＃环境安装搭建

# setting pyenv
brew install pyenv

# list all version
pyenv install --list

# install python 3.6.3
pyenv install 3.6.3

# install pyenv-virtualenv
brew install pyenv-virtualenv

# add shell cmd to your profile，只用加一次，如果之前加过就不用再添加了
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"

# create virtualenv（onepage是虚拟环境的名称）
pyenv virtualenv 3.6.3 onepage

# activate onepage env
pyenv activate onepage

# deactivate
pyenv deactivate



### Init database local
# Insert
CREATE USER "onepage" WITH PASSWORD 'password'
GRANT ALL ON onepage.* TO 'onepage'@'localhost';
CREATE DATABASE "onepage"

# install pkg
pip install -r requirements.txt

#查看安装的django版本
python -m django --version

# create mysql table
python manage.py migrate

# run with development setting
python manage.py runserver

# run test with test setting
python manage.py test
