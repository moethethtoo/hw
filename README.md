# hw
create table helpdesk
(HD_Category varchar2(8),
HD_Year number,
HD_Ticker_No number,
HD_Title varchar2(30),
constraint HelpDesk_PK primary key (HD_Category, HD_Year, HD_Ticker_No));

create table PORTS
(PORT_ID number,
PORT_NAME varchar2(20),
COUNTRY varchar2(40),
CAPACITY number,
constraint PORT_PK primary key (PORT_ID));

create table SHIPS
(SHIP_ID number,
SHIP_NAME varchar2(20),
HOME_PORT_ID number,
constraint SHIPS_PORTS_FK foreign key (HOME_PORT_ID)
references PORTS (PORT_ID));

insert into helpdesk values ('IT',2023,111,'IT_Support');
select * from helpdesk;
commit;
insert into ports values (1,'PN','Myanmar',2);
select *  from ports;
insert into ships values (1,'SHIP1',1);
select * from ships;
commit;

delete from ports where port_id = '1';
desc ships;
drop table ships;
drop table ports;
truncate table ports;
