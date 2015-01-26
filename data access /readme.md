#mysql

* 1. brew를 통한 설치 
http://blog.saltfactory.net/121


* 2. path 찾아서 path 셋팅해주기 
echo $PATH
export PATH=$PATH:/usr/local/mysql/bin
export PATH=$PATH:/usr/local/Cellar/mysql/5.6.22/bin 
(사람 마다 다를수 있음 찾아야 될듯함) 




* 3. mysql 시작하기

mysql.server start

mysql.server stop  - 안쓸대 중지 시키기


* 4. 패스워드 변경하기

$ mysqladmin -u root -p password new-password
위의 방법은 쉘에서 바로 실행하면 되지만, 암호가 히스토리에 남을수 있기 때문에 권하지 않습니다.

update문을 이용하여 root 암호 설정
 $ mysql -u root mysql

 mysql> update user set password = password('new-password') where user = 'root';
 mysql> flush privileges;
