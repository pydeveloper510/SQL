# SQL
SQL Experience

https://m.blog.naver.com/islove8587/220605402338

## change compare type to column's type
SELECT * FROM TABLE_PRODUCT
WHERE UNDERLYING_TICKER=CONVERT(CHAR(20), 'AAPL US EQUITY')


# Change Password
Tools/User manager   ctrl + u


insert into on duplicate key update

# Install mysql_oracle 5.7.9

1. 
먼저 vcredist_x64.exe(x86)을 설치한다.
높은 버젼이 설치되여 있다면 설치 안해도 된다.

2. 
환경변수설정을 한다.
win + R control 입력 시스템 ->고급시스템설정 ->고급탭의 환경변수설정을 누른다.
(N)을 누르고 PATH에 설치하려는 MYSQL의 위치를 지정해준다.

3. 
win + R notepad 입력 my.ini 파일을 생성한다. (my1.ini)
(인코딩 옵션을 ANSI, ASCII로 지정하지 않고 UTF-8 로 지정하면 에러가 나올수 있음)
이화일에 다음과 같은 설정을 지정한다.
basedir = D:/Work/mysql
datador = D:/Work/mysql/data
port = 3306

(data안에 파일이 생기지 않으면 다음 옵션을 추가한다)
innodb_flush_method = normal

4.
win + X
명령프롬프트를 관리자권한으로 실행한다.

D:\Work\web\mysql>cd bin

D:\Work\web\mysql\bin>mysqld --install mysql_oracle
Service successfully installed.

D:\Work\web\mysql\bin>cd..

D:\Work\web\mysql>cd ..

D:\Work\web>cd mysql

D:\Work\web\mysql>mysql_start.bat

D:\Work\web\mysql>net start mysql_oracle
The mysql_oracle service is starting.
The mysql_oracle service was started successfully.

5. 
win + R를 누르고 services.msc 를 입력하고 mysql_oracle 을 실행한다.
mysql -u root -p
입력후 .err에서 찾은 기존 암호를 입력한다. 
(설치시 임의의 암호 설정 기존암호 찾는 방법 아래에 첨부)
set password = '1111'; 으로 사용자지정암호를 설정한다.
sqlyog 에서 사용자가 지정한 암호를 입력하고 들어가 편집할수 있다.


*** mysql_start.bat 시 에러가 나오는 경우 

1. mysql 홀더안의 data 홀더 내용을 전부 삭제
2. bin> mysqld --initialize
3. cd .. 
4. mysql_start.bat

my.ini 화일 인코딩 옵션 다시 확인할것
cmd 창을 관리자권한으로 실행하여야 한다.  ***
