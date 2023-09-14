
### 图形化ansible页面管理工具,ansible-tower,部署ansible-tower服务器必须内存大于4G，否则会失败.

```javascript
cd /root
wget https://releases.ansible.com/ansible-tower/setup-bundle/ansible-tower-setup-bundle-3.8.6-2.tar.gz
cd /root/ansible-tower-setup-bundle-3.8.6-2
vi inventory
admin_password='AdminPassword'
pg_database='awx'
pg_username='awx'
pg_password='PgStrongPassword'
```

### 部署

```javascript
cd /root/ansible-tower-setup-bundle-3.8.6-2
bash setup.sh
```

### 替换本git仓库里面的licensing.py文件到/var/lib/awx/venv/awx/lib/python3.6/site-packages/awx/main/utils 目录下.
```javascript
cp ./licensing.py /var/lib/awx/venv/awx/lib/python3.6/site-packages/awx/main/utils/licensing.py
```

### 重启，并登录

```javascript
ansible-tower-service restart


http://localhost
user: admin
passwd: AdminPassword
```
