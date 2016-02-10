# Axcient SaasOps Support Tools

Tools to make Customer Support, Customer Satisfaction, and SaaS Operations teams more efficient

### Open Source Dependences (bundled in code)

[![Bootstrap](https://img.shields.io/badge/bootstrap-3.3.6-green.svg)](http://getbootstrap.com/)
[![Bootstrap Table](https://img.shields.io/badge/bootstrap--table-1.10.0-blue.svg)](https://github.com/wenzhixin/bootstrap-table)
[![Bootstrap Select](https://img.shields.io/badge/bootstrap--select-1.9.4-blue.svg)](https://github.com/silviomoreto/bootstrap-select)
[![Bootstrap Datepicker](https://img.shields.io/badge/bootstrap--datepicker-1.6.0-blue.svg)](https://github.com/eternicode/bootstrap-datepicker)
[![Font Awesome](https://img.shields.io/badge/Font Awesome-4.5.0-green.svg)](http://fortawesome.github.io/Font-Awesome/)
[![Jquery](https://img.shields.io/badge/Jquery-2.2.0-green.svg)](https://jquery.com/)
[![TCPDF](https://img.shields.io/badge/TCPDF-6.2.11-blue.svg)](http://sourceforge.net/projects/tcpdf/files/)
[![PHPMailer](https://img.shields.io/badge/PHPMailer-5.2.14-blue.svg)](https://github.com/PHPMailer/PHPMailer)

### Installation

You need the following packages installed on whatever machine will be running the tools:

```
$ apt-get install apache2 mysql php5 php5-xcache
```

Clone repo from source
```sh
$ git clone ssh://git@gitlab.ninebladeimages.com:erichardson/axcient-support-tools.git
```

### Table Creation scripts:
Requests
```sql
CREATE TABLE `requests` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `date` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `requestor` tinyint(4) DEFAULT NULL,
  `site` tinytext NOT NULL,
  `svcid` varchar(5) NOT NULL,
  `namespace` tinytext,
  `assettag` varchar(16) DEFAULT NULL,
  `serialnumber` char(17) DEFAULT NULL,
  `partner` tinytext,
  `enduser` tinytext,
  `dest_method` tinyint(4) DEFAULT NULL,
  `app_flags` tinyint(4) DEFAULT NULL,
  `offsite_flags` tinyint(4) DEFAULT NULL,
  `app_wiped_by` mediumint(9) DEFAULT NULL,
  `app_wiped_date` timestamp NULL DEFAULT '0000-00-00 00:00:00',
  `off_wiped_by` mediumint(9) DEFAULT NULL,
  `off_wiped_date` timestamp NULL DEFAULT '0000-00-00 00:00:00',
  PRIMARY KEY (`id`)
)
```

Sites
```sql
 CREATE TABLE `sites` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `site_name` varchar(60) NOT NULL,
  PRIMARY KEY (`id`)
)
```

Users
```sql
CREATE TABLE `users` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` tinytext,
  `role` varchar(10) DEFAULT NULL,
  `active` tinyint(1) DEFAULT 1,
  PRIMARY KEY (`id`)
)
```

### Note: 
Signature images should be saved as [firstname]sig.png, as the Certificate of Destruction code will look for [name]sig.png.  Ex: evansig.png, altonsig.png, etc.
### Todo's

 - Todo
