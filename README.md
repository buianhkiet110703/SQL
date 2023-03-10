# The table structure is as follows :
![image](https://user-images.githubusercontent.com/110837675/212323928-120f0473-7d88-4bef-85ca-afbab466228d.png)
![image](https://user-images.githubusercontent.com/110837675/212324165-3173bba9-35f2-4caf-85e2-f6aa6c711e37.png)
![image](https://user-images.githubusercontent.com/110837675/212324274-254a80d4-37a7-4602-bfa8-88298acfa453.png)

# Write query language:

```php
USE D4E14
CREATE TABLE KHACHHANG(
    MAKH CHAR(4) primary key,
    HOTEN VARCHAR(40),
    DCHI VARCHAR(50),
    SODT VARCHAR(20),
    NGSINH DATETIME,
    NGDK DATETIME,
    DOANHSO MONEY 
)

CREATE TABLE NHANVIEN(
    MANV CHAR(4) PRIMARY KEY,
    HOTEN VARCHAR (40),
    SODT VARCHAR (20),
    NGVL DATETIME
)
CREATE TABLE SANPHAM(
    MASP CHAR(4) PRIMARY KEY,
    TENSP VARCHAR(40),
    DVT VARCHAR(20),
    NUOCSX VARCHAR(40),
    GIABAN MONEY
)
CREATE TABLE HOADON(
    SOHD INT PRIMARY KEY,
    NGHD DATETIME,
    MAKH CHAR(4) references KHACHHANG (MAKH),
    MANV CHAR(4) references NHANVIEN (MANV),
    TRIGIA MONEY
)
CREATE TABLE CTHD(
    SOHD INT REFERENCES HOADON (SOHD),
    MASP CHAR(4) REFERENCES SANPHAM (MASP),
    SL INT
)
insert into KHACHHANG VALUES ('KH01','NGUYEN VAN A','731 TRAN HUNG DAO, Q5, TPHCM','08823451','10/22/1960','10/22/1960',13000000)

insert into KHACHHANG values ('KH02','Tran Ngoc Han','23/5, Nguyen Trai, Q 5, Tp HCM','0908256478','04/03/1974','07/30/2006',280000)

insert into KHACHHANG values ('KH03','Tran Ngoc Linh','45, Nguyen Canh Chan, Q 1, Tp HCM','0938776266','06/12/1980','08/05/2006',3860000)

insert into KHACHHANG values ('KH04','Tran Minh Long','50/34 Le Dai Hanh, Q 10, Tp HCM','0917325476','03/09/1965','10/02/2006',250000)

insert into KHACHHANG values ('KH05','Le Nhat Minh','34, Truong Dinh, Q 3, Tp HCM','08246108','03/10/1950','10/28/2006',21000)

insert into KHACHHANG values ('KH06','Le Hoai Thuong','227, Nguyen Van Cu, Q 5, Tp HCM','08631738','12/31/1981','11/24/2006',915000)

insert into KHACHHANG values ('KH07','Nguyen Van Tam','32/3, Tran Binh Trong, Q 5, Tp HCM','0916783565','04/06/1971','12/01/2006',12500)

insert into KHACHHANG values ('KH08','Phan Thi Thanh','45/2, An Duong Vuong, Q 5, Tp HCM','0938435756','01/10/1971','12/13/2006',365000)

insert into KHACHHANG values ('KH09','Le Ha Vinh','873, Le Hong Phong, Q 5, Tp HCM','08654763','09/03/1979','01/14/2007',70000)

insert into KHACHHANG values ('KH10','Ha Duy Lap','34/34B, Nguyen Trai, Q 1, Tp HCM','08768904','05/02/1983','01/16/2007',67500)

insert into NHANVIEN values ('NV01','Nguyen Nhu Nhut','0927345678','04/13/2006')

insert into NHANVIEN values ('NV02','Le Thi Phi Yen','0987567390','04/21/2006')

insert into NHANVIEN values ('NV03','Nguyen Van B','0997047382','04/27/2006')

insert into NHANVIEN values ('NV04','Ngo Thanh Tuan','0913758498','06/24/2006')

insert into NHANVIEN values ('NV05','Nguyen Thi Truc Thanh','0918590387','07/20/2006')

insert into SANPHAM values ('BC01','But chi','cay','Singapore',3000)
insert into SANPHAM values ('BC02','But chi','cay','Singapore',5000)
insert into SANPHAM values ('BC03','But chi','cay','Viet Nam',3500)
insert into SANPHAM values ('BC04','But chi','hop','Viet Nam',30000)
insert into SANPHAM values ('BB01','But bi','cay','Viet Nam',5000)
insert into SANPHAM values ('BB02','But bi','cay','Trung Quoc',7000)
insert into SANPHAM values ('BB03','But bi','hop','Thai Lan',100000)
insert into SANPHAM values ('TV01','Tap 100 giay mong','quyen','Trung Quoc',2500)
insert into SANPHAM values ('TV02','Tap 200 giay mong','quyen','Trung Quoc',4500)
insert into SANPHAM values ('TV03','Tap 100 giay tot','quyen','Viet Nam',3000)
insert into SANPHAM values ('TV04','Tap 200 giay tot','quyen','Viet Nam',5500)
insert into SANPHAM values ('TV05','Tap 100 trang','chuc','Viet Nam',23000)
insert into SANPHAM values ('TV06','Tap 200 trang','chuc','Viet Nam',53000)
insert into SANPHAM values ('TV07','Tap 100 trang','chuc','Trung Quoc',34000)
insert into SANPHAM values ('ST01','So tay 500 trang','quyen','Trung Quoc',40000)
insert into SANPHAM values ('ST02','So tay loai 1','quyen','Viet Nam',55000)
insert into SANPHAM values ('ST03','So tay loai 2','quyen','Viet Nam',51000)
insert into SANPHAM values ('ST04','So tay ','quyen','Thai Lan',55000)
insert into SANPHAM values ('ST05','So tay mong','quyen','Thai Lan',20000)
insert into SANPHAM values ('ST06','Phan viet bang','hop','Viet Nam',5000)
insert into SANPHAM values ('ST07','Phan khong bui','hop','Viet Nam',7000)
insert into SANPHAM values ('ST08','Bong bang','cai','Viet Nam',1000)
insert into SANPHAM values ('ST09','But long','cay','Viet Nam',5000)
insert into SANPHAM values ('ST10','But long','cay','Trung Quoc',7000)

insert into HOADON values (1001,'07/23/2006','KH01','NV01',320000)
insert into HOADON values (1002,'08/12/2006','KH01','NV02',840000)
insert into HOADON values (1003,'08/23/2006','KH02','NV01',100000)
insert into HOADON values (1004,'09/01/2006','KH02','NV01',180000)
insert into HOADON values (1005,'10/20/2006','KH01','NV02',3800000)
insert into HOADON values (1006,'10/16/2006','KH01','NV03',2430000)
insert into HOADON values (1007,'10/28/2006','KH03','NV03',510000)
insert into HOADON values (1008,'10/28/2006','KH01','NV03',440000)
insert into HOADON values (1009,'10/28/2006','KH03','NV04',200000)
insert into HOADON values (1010,'11/01/2006','KH01','NV01',5200000)
insert into HOADON values (1011,'11/04/2006','KH04','NV03',250000)
insert into HOADON values (1012,'11/30/2006','KH05','NV03',21000)
insert into HOADON values (1013,'12/12/2006','KH06','NV01',5000)
insert into HOADON values (1014,'12/31/2006','KH03','NV02',3150000)
insert into HOADON values (1015,'01/01/2007','KH06','NV01',910000)
insert into HOADON values (1016,'01/01/2007','KH07','NV02',12500)
insert into HOADON values (1017,'01/02/2007','KH08','NV03',35000)
insert into HOADON values (1018,'01/13/2007','KH08','NV03',330000)
insert into HOADON values (1019,'01/13/2007','KH01','NV03',30000)
insert into HOADON values (1020,'01/14/2007','KH09','NV04',70000)
insert into HOADON values (1021,'01/16/2007','KH10','NV03',67500)
insert into HOADON values (1022,'01/16/2007',null,'NV03',7000)
insert into HOADON values (1023,'01/17/2007',null,'NV01',330000)

insert into CTHD values (1001,'TV02',10)
insert into CTHD values (1001,'ST01',5)
insert into CTHD values (1001,'BC01',5)
insert into CTHD values (1001,'BC02',10)
insert into CTHD values (1001,'ST08',10)
insert into CTHD values (1002,'BC04',20)
insert into CTHD values (1002,'BB01',20)
insert into CTHD values (1002,'BB02',20)
insert into CTHD values (1003,'BB03',10)
insert into CTHD values (1004,'TV01',20)
insert into CTHD values (1004,'TV02',20)
insert into CTHD values (1004,'TV03',20)
insert into CTHD values (1004,'TV04',20)
insert into CTHD values (1005,'TV05',50)
insert into CTHD values (1005,'TV06',50)
insert into CTHD values (1006,'TV07',20)
insert into CTHD values (1006,'ST01',30)
insert into CTHD values (1006,'ST02',10)
insert into CTHD values (1007,'ST03',10)
insert into CTHD values (1008,'ST04',8)
insert into CTHD values (1009,'ST05',10)
insert into CTHD values (1010,'TV07',50)
insert into CTHD values (1010,'ST07',50)
insert into CTHD values (1010,'ST08',100)
insert into CTHD values (1010,'ST04',50)
insert into CTHD values (1010,'TV03',100)
insert into CTHD values (1011,'ST06',50)
insert into CTHD values (1012,'ST07',3)
insert into CTHD values (1013,'ST08',5)
insert into CTHD values (1014,'BC02',80)
insert into CTHD values (1014,'BB02',100)
insert into CTHD values (1014,'BC04',60)
insert into CTHD values (1014,'BB01',50)
insert into CTHD values (1015,'BB02',30)
insert into CTHD values (1015,'BB03',7)
insert into CTHD values (1016,'TV01',5)
insert into CTHD values (1017,'TV02',1)
insert into CTHD values (1017,'TV03',1)
insert into CTHD values (1017,'TV04',5)
insert into CTHD values (1018,'ST04',6)
insert into CTHD values (1019,'ST05',1)
insert into CTHD values (1019,'ST06',2)
insert into CTHD values (1020,'ST07',10)
insert into CTHD values (1021,'ST08',5)
insert into CTHD values (1021,'TV01',7)
insert into CTHD values (1021,'TV02',10)
insert into CTHD values (1022,'ST07',1)
insert into CTHD values (1023,'ST04',6)

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) do ???Trung Quoc??? s???n xu???t.*/
SELECT MASP, TENSP
from SANPHAM
WHERE NUOCSX ='Trung Quoc'

/*In ra danh s??ch c??c s???n ph???m (MASP, TENSP) c?? ????n v??? t??nh l?? ???cay???, ???quyen???.*/
SELECT MASP,TENSP
from SANPHAM
WHERE DVT in ('cay','quyen')

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) c?? m?? s???n ph???m b???t ?????u l?? ???B??? v?? k???t th??c l?? ???01???.*/
SELECT MASP,TENSP
from SANPHAM
WHERE MASP LIKE 'B%01'

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) do ???Trung Qu???c??? s???n xu???t c?? gi?? t??? 30.000 ?????n 40.000.*/
SELECT MASP,TENSP
FROM SANPHAM
WHERE NUOCSX='Trung Quoc' AND GIABAN BETWEEN 30000 and 40000

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) do ???Trung Quoc??? ho???c ???Thai Lan??? s???n xu???t c?? gi?? t??? 30.000 ?????n 40.000.*/
SELECT MASP,TENSP
from SANPHAM
WHERE NUOCSX IN('Trung Quoc','Thai Lan') and GIABAN BETWEEN 3000 and 40000

/*In ra c??c s??? h??a ????n, tr??? gi?? h??a ????n b??n ra trong ng??y 1/1/2007 v?? ng??y 2/1/2007.*/
SELECT SOHD,TRIGIA
from HOADON
WHERE NGHD IN ('01/01/2007','01/02/2007')

/*In ra c??c s??? h??a ????n, tr??? gi?? h??a ????n trong th??ng 1/2007, s???p x???p theo ng??y (t??ng d???n) v?? tr??? gi?? c???a h??a ????n (gi???m d???n).*/
SELECT SOHD,TRIGIA
from HOADON
WHERE YEAR(NGHD)= '2007' AND MONTH(NGHD)= '01'
ORDER BY NGHD asc , TRIGIA DESC

/*In ra danh s??ch c??c kh??ch h??ng (MAKH, HOTEN) ???? mua h??ng trong ng??y 1/1/2007.*/
SELECT KHACHHANG.MAKH,HOTEN
from KHACHHANG JOIN HOADON ON KHACHHANG.MAKH=HOADON.MAKH
WHERE NGHD= '01/01/2007'

/*In ra s??? h??a ????n, tr??? gi?? c??c h??a ????n do nh??n vi??n c?? t??n ???Nguyen Van B??? l???p trong ng??y 28/10/2006.*/
SELECT SOHD, TRIGIA
from HOADON join NHANVIEN on HOADON.MANV=NHANVIEN.MANV
WHERE HOTEN ='Nguyen Van B' AND NGHD= '10/28/2006'

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) ???????c kh??ch h??ng c?? t??n ???Nguyen Van A??? mua trong th??ng 10/2006.*/
SELECT SANPHAM.MASP,TENSP
from KHACHHANG, SANPHAM,HOADON,CTHD
WHERE (KHACHHANG.MAKH=HOADON.MAKH) AND(SANPHAM.MASP=CTHD.MASP) and (HOADON.SOHD=CTHD.SOHD) AND HOTEN= 'Nguyen Van A' AND YEAR(NGHD)='2006' AND MONTH(NGHD)='10'

/*T??m c??c s??? h??a ????n ???? mua s???n ph???m c?? m?? s??? ???BB01??? ho???c ???BB02???.*/
SELECT DISTINCT HOADON.SOHD
from HOADON JOIN CTHD ON HOADON.SOHD=CTHD.SOHD
WHERE MASP ='BB01' OR MASP='BB02'

/*T??m c??c s??? h??a ????n ???? mua s???n ph???m c?? m?? s??? ???BB01??? ho???c ???BB02???, m???i s???n ph???m mua v???i s??? l?????ng t??? 10 ?????n 20.*/
SELECT distinct SOHD
from CTHD
WHERE (MASP ='BB01' OR MASP='BB02') AND SL BETWEEN 10 and 20

/*T??m c??c s??? h??a ????n mua c??ng l??c 2 s???n ph???m c?? m?? s??? ???BB01??? v?? ???BB02???, m???i s???n ph???m mua v???i s??? l?????ng t??? 10 ?????n 20.*/
SELECT SOHD
FROM CTHD A
WHERE MASP = 'BB02' AND A.SL BETWEEN 10 AND 20 AND EXISTS (
	SELECT SOHD 
	FROM CTHD B
	WHERE MASP = 'BB01' AND A.SOHD = B.SOHD AND B.SL BETWEEN 10 AND 20
	)

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) do ???Trung Quoc??? s???n xu???t ho???c c??c s???n ph???m ???????c b??n ra trong ng??y 1/1/2007.*/
SELECT TENSP,MASP
from SANPHAM
WHERE NUOCSX='Trung Quoc' or MASP IN (select CTHD.MASP from HOADON join CTHD on HOADON.SOHD=CTHD.SOHD where NGHD ='01/01/2007')

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) kh??ng b??n ???????c.*/
SELECT A.MASP , TENSP
FROM SANPHAM A
WHERE NOT EXISTS (
	SELECT MASP
	FROM CTHD B
	WHERE A.MASP = B.MASP
	)
/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) kh??ng b??n ???????c trong n??m 2006.*/
SELECT SANPHAM.MASP,SANPHAM.TENSP
from SANPHAM
WHERE MASP not IN ( select MASP from CTHD join HOADON on CTHD.SOHD=HOADON.SOHD where YEAR(NGHD)='2006')

/*In ra danh s??ch c??c s???n ph???m (MASP,TENSP) do ???Trung Quoc??? s???n xu???t kh??ng b??n ???????c trong n??m 2006.*/
SELECT MASP,TENSP
from SANPHAM
WHERE MASP not IN (select CTHD.MASP from CTHD join HOADON on CTHD.SOHD=HOADON.SOHD where YEAR(NGHD)='2006') AND NUOCSX='Trung Quoc'

/*T??m s??? h??a ????n ???? mua t???t c??? c??c s???n ph???m do Singapore s???n xu???t.*/
select SOHD
from HOADON 
where not  exists ( 
			select MASP
			from SANPHAM
			where nuocsx= 'Singapore' and not exists (
				select SOHD
				from CTHD 
				where HOADON.sohd=CTHD.sohd and CTHD.masp=SANPHAM.masp) )
--ho???c l??m c??ch kh??c 
SELECT SOHD,TENSP, COUNT(TENSP)
from CTHD join SANPHAM ON CTHD.MASP=SANPHAM.MASP
WHERE NUOCSX='Singapore'
GROUP BY SOHD,TENSP
HAVING COUNT(TENSP)=(SELECT COUNT(TENSP)
from SANPHAM
WHERE NUOCSX='Singapore')

/*C?? bao nhi??u h??a ????n kh??ng ph???i c???a kh??ch h??ng ????ng k?? th??nh vi??n mua?*/
SELECT COUNT(*) AS SOHOADONKHONGPHAIDOTHANHVIENMUA
FROM HOADON
WHERE MAKH IS NULL

/*C?? bao nhi??u s???n ph???m kh??c nhau ???????c b??n ra trong n??m 2006.*/
SELECT COUNT(distinct MASP)
FROM CTHD JOIN HOADON ON CTHD.SOHD=HOADON.SOHD
WHERE YEAR(NGHD)='2006'

/*Cho bi???t tr??? gi?? h??a ????n cao nh???t, th???p nh???t l?? bao nhi??u ?*/
SELECT MAX(TRIGIA),MIN(TRIGIA)
from HOADON
/*Tr??? gi?? trung b??nh c???a t???t c??? c??c h??a ????n ???????c b??n ra trong n??m 2006 l?? bao nhi??u?*/
SELECT AVG(TRIGIA)
from HOADON
WHERE YEAR(NGHD)='2006'

/*T??nh doanh thu b??n h??ng trong n??m 2006.*/
SELECT SUM(TRIGIA)
from HOADON
WHERE YEAR(NGHD)='2006'

/*T??m s??? h??a ????n c?? tr??? gi?? cao nh???t trong n??m 2006.*/
SELECT SOHD
from HOADON
WHERE TRIGIA >= all (select MAX(TRIGIA) from HOADON  WHERE YEAR(NGHD)='2006')

/*T??m h??? t??n kh??ch h??ng ???? mua h??a ????n c?? tr??? gi?? cao nh???t trong n??m 2006.*/
SELECT HOTEN
from HOADON JOIN KHACHHANG on HOADON.MAKH=KHACHHANG.MAKH
WHERE TRIGIA >= all (select MAX(TRIGIA) from HOADON  WHERE YEAR(NGHD)='2006')

/*In ra danh s??ch 3 kh??ch h??ng (MAKH, HOTEN) c?? doanh s??? cao nh???t.*/
SELECT top 3  MAKH,HOTEN
from KHACHHANG
ORDER BY DOANHSO DESC

/*In ra danh s??ch c??c s???n ph???m (MASP, TENSP) c?? gi?? b??n b???ng 1 trong 3 m???c gi?? cao nh???t.*/
SELECT MASP ,TENSP
FROM SANPHAM
WHERE GIABAN IN (
	SELECT TOP 3 GIABAN
	FROM SANPHAM
	ORDER BY GIABAN DESC)

/*In ra danh s??ch c??c s???n ph???m (MASP, TENSP) do ???Thai Lan??? s???n xu???t c?? gi?? b???ng 1 trong 3 m???c gi?? cao nh???t (c???a t???t c??? c??c s???n ph???m).*/
SELECT MASP ,TENSP
FROM SANPHAM
WHERE GIABAN IN (
	SELECT TOP 3 GIABAN
	FROM SANPHAM
	ORDER BY GIABAN DESC) AND NUOCSX='Thai Lan'

/*In ra danh s??ch c??c s???n ph???m (MASP, TENSP) do ???Trung Quoc??? s???n xu???t c?? gi?? b???ng 1 trong 3 m???c gi?? cao nh???t (c???a s???n ph???m do ???Trung Quoc??? s???n xu???t).*/
SELECT MASP ,TENSP
FROM SANPHAM
WHERE GIABAN IN (
	SELECT TOP 3 GIABAN
	FROM SANPHAM
    WHERE NUOCSX='Trung Quoc'
	ORDER BY GIABAN DESC) AND NUOCSX='Trung Quoc'

/** In ra danh s??ch 3 kh??ch h??ng c?? doanh s??? cao nh???t (s???p x???p theo ki???u x???p h???ng).*/
select MAKH,HOTEN, RANK() OVER(ORDER BY DOANHSO)
from KHACHHANG

/*T??nh t???ng s??? s???n ph???m do ???Trung Quoc??? s???n xu???t.*/
select count(MASP)
from SANPHAM
WHERE NUOCSX='Trung Quoc'

/*T??nh t???ng s??? s???n ph???m c???a t???ng n?????c s???n xu???t.*/
SELECT COUNT(*), NUOCSX
from SANPHAM
group BY NUOCSX

/*V???i t???ng n?????c s???n xu???t, t??m gi?? b??n cao nh???t, th???p nh???t, trung b??nh c???a c??c s???n ph???m*/
select NUOCSX, MAX(GIABAN) AS max_price, MIN(GIABAN) as min_price, AVG(GIABAN) AS avg_price 
from SANPHAM
GROUP BY NUOCSX

/*T??nh doanh thu b??n h??ng m???i ng??y.*/
SELECT NGHD , SUM(TRIGIA) AS DOANHTHU
FROM HOADON
GROUP BY NGHD

/*T??nh t???ng s??? l?????ng c???a t???ng s???n ph???m b??n ra trong th??ng 10/2006*/
SELECT TENSP, SUM(SL) AStong_sl   
from SANPHAM JOIN CTHD ON SANPHAM.MASP=CTHD.MASP
             JOIN HOADON ON HOADON.SOHD=CTHD.SOHD
WHERE MONTH(NGHD)='10' AND YEAR(NGHD)='2006'
GROUP BY TENSP

/*T??nh doanh thu b??n h??ng c???a t???ng th??ng trong n??m 2006*/
SELECT MONTH(NGHD), SUM(TRIGIA)
from HOADON
WHERE YEAR(NGHD)='2006'
GROUP BY MONTH(NGHD)

/*T??m h??a ????n c?? mua ??t nh???t 4 s???n ph???m kh??c nhau*/
SELECT SOHD 
FROM CTHD
GROUP BY SOHD
HAVING COUNT(DISTINCT MASP) > 4

/*T??m h??a ????n c?? mua 3 s???n ph???m do ???Viet Nam??? s???n xu???t (3 s???n ph???m kh??c nhau)*/
SELECT SOHD
from CTHD join SANPHAM on CTHD.MASP=SANPHAM.MASP
WHERE NUOCSX='Viet Nam'
group BY SOHD
HAVING COUNT(distinct CTHD.MASP)=3

/*T??m kh??ch h??ng (MAKH, HOTEN) c?? s??? l???n mua h??ng nhi???u nh???t*/
SELECT  KHACHHANG.MAKH
FROM HOADON JOIN KHACHHANG ON HOADON.MAKH = KHACHHANG.MAKH
GROUP BY KHACHHANG.MAKH , HOTEN
ORDER BY COUNT(*) DESC

/*Th??ng m???y trong n??m 2006, doanh s??? b??n h??ng cao nh???t ?*/
SELECT SUM(TRIGIA),MONTH(NGHD)
from HOADON
WHERE YEAR(NGHD)='2006'
GROUP BY MONTH(NGHD)
ORDER BY SUM(TRIGIA) DESC

/*T??m s???n ph???m (MASP, TENSP) c?? t???ng s??? l?????ng b??n ra th???p nh???t trong n??m 2006*/
SELECT MASP 
FROM HOADON JOIN CTHD ON HOADON.SOHD = CTHD.SOHD
WHERE YEAR (NGHD) = 2006
GROUP BY MASP
ORDER BY SUM(SL) ASC

/**M???i n?????c s???n xu???t, t??m s???n ph???m (MASP,TENSP) c?? gi?? b??n cao nh???t.*/

SELECT NUOCSX,MASP,MAX(GIABAN)
from SANPHAM
GROUP BY NUOCSX,MASP,TENSP
HAVING MAX(GIABAN) >=ALL (SELECT MAX(GIABAN) FROM SANPHAM S WHERE SANPHAM.NUOCSX=S.NUOCSX GROUP by NUOCSX)


/*T??m n?????c s???n xu???t s???n xu???t ??t nh???t 3 s???n ph???m c?? gi?? b??n kh??c nhau.*/
SELECT NUOCSX
from SANPHAM
GROUP BY NUOCSX
HAVING COUNT(distinct GIABAN)>=3

/**Trong 10 kh??ch h??ng c?? doanh s??? cao nh???t, t??m kh??ch h??ng c?? s??? l???n mua h??ng nhi???u nh???t.*/
SELECT TOP 1 MAKH ,HOTEN 
FROM (
		SELECT TOP 10 KHACHHANG.MAKH , KHACHHANG.HOTEN , COUNT(HOADON.MAKH) AS SL
		FROM  KHACHHANG JOIN HOADON ON KHACHHANG.MAKH = HOADON.MAKH
		GROUP BY KHACHHANG.MAKH , KHACHHANG.DOANHSO , KHACHHANG.HOTEN
		ORDER BY KHACHHANG.DOANHSO DESC
		) KH
ORDER BY SL DESC
```
