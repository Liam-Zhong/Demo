+++
title = '关于sql'
date = 2024-05-30T16:54:25+08:00
math = true                                 # enable KaTeX math typesetting for a specific page
draft = false
comments = true

+++

```sql
/*==============================================================*/
/* DBMS name:      MySQL 5.0                                    */
/* Created on:     5/30/2024 4:50:58 PM                         */
/*==============================================================*/


drop table if exists bookshop;

drop table if exists address;

drop table if exists goumaishuji;

drop table if exists guke;

/*==============================================================*/
/* Table: bookshop                                                    */
/*==============================================================*/
create table bookshop
(
   BookShopNO           char(6) not null,
   BookShopName         varchar(30),
   Bookshopadd          varchar(60),
   city                 varchar(20),
   sheng                varchar(20),
   code                 char(6),
   primary key (BookShopNO)
);

/*==============================================================*/
/* Table: address                                                    */
/*==============================================================*/
create table address
(
   AddressType       char(2) not null,
   CustomerID           varchar(10),
   Add1                 varchar(50),
   Add2                 varchar(50),
   city                 varchar(20),
   State                varchar(15),
   code                 char(6),
   primary key (AddressType)
);

/*==============================================================*/
/* Table: goumaishuji                                                  */
/*==============================================================*/
create table goumaishuji
(
   BookShopNO           char(6) not null,
   CustomerID           varchar(10) not null,
   primary key (BookShopNO)
);

/*==============================================================*/
/* Table: guke                                                    */
/*==============================================================*/
create table guke
(
   CustomerID           varchar(10) not null,
   AccountBalanceDecimal decimal(10,2),
   FirstName         varchar(10),
   LastName          varchar(20),
   CompanyName       varchar(40),
   primary key (CustomerID)
);

alter table address add constraint FK_xuanke foreign key (CustomerID)
      references guke (CustomerID) on delete restrict on update restrict;

alter table goumaishuji add constraint FK_goumaishuji foreign key (BookShopNO)
      references bookshop (BookShopNO) on delete restrict on update restrict;

alter table goumaishuji add constraint FK_goumaishuji2 foreign key (CustomerID)
      references guke (CustomerID) on delete restrict on update restrict;


```

在Windows11、Power Designer 16中导出上述sql文件时，会将一些键值打上引号，继而引发sql命令行操作报错，去掉之后正常。
