### 建立本地软件库(一般在没有网络的情况下)
https://www.digitalocean.com/community/tutorials/how-to-set-up-and-use-yum-repositories-on-a-centos-6-vps
 
> * 1. /etc/yum.repos.d/
 
> * 2. 编辑 repo文件，指向 myrepository
 
> * 3. createrepo /myrepository
 
> * 4. put rpm files to myrepository
 
> * 5. yum install xxx.rpm
