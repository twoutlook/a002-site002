# a002-site002

## on local dev
pip freeze > requirements.txt


## on server site
pip install -r requirements.txt 




### 第一次部署時 
cd /home/demo/site001
./manage.py migrate
./manage.py createsuperuser


### 部署時必要的權限設置
sudo chmod 710 /home/demo
sudo chmod 664 /home/demo/site002/db.sqlite3

sudo chown :apache /home/demo/site002
sudo chown :apache /home/demo/site002/db.sqlite3


### 更新時重起 Apache
#sudo systemctl stop httpd
sudo systemctl restart httpd
sudo systemctl status httpd

##
ALLOWED_HOSTS = ['*']


## Github remember password
https://help.github.com/en/articles/caching-your-github-password-in-git NOT WORKING


https://help.github.com/en/articles/connecting-to-github-with-ssh


## working Github remember password
git config --global credential.helper store


# before collectstatic
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')# a002-site002
