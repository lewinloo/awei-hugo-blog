---
title: "惊！学了这篇文章，我可以定义数据库了！"
subtitle: ""
date: 2023-01-11T14:00:52+08:00
draft: false
description: "关于数据库 DDL 相关知识"
resources:
- name: "featured-image"
  src: "featured-image.jpg"

tags: ["DDL", "MySQL"]
categories: ["database"]

hiddenFromHomePage: false
hiddenFromSearch: false

# See details front matter: https://fixit.lruihao.cn/theme-documentation-content/#front-matter
---

<!--more-->

## 查询数据库的信息

{{< admonition type=info title="小贴士" open=true >}}
使用该命令即可展示所有的数据库信息
{{< /admonition >}}

```mysql
SHOW DATABASES;
```

## 创建数据库
{{< admonition type=info title="小贴士" open=true >}}
该命令的含义是可创建一个数据库，如果他不存在的情况下。DEFAULT CHARSET utf8mb4 是设置数据库的字符集。COLLATE utf8mb4_general_ci 是设置排序规则。
{{< /admonition >}}

```mysql
CREATE DATABASE IF NOT EXISTS awei DEFAULT CHARSET utf8mb4 COLLATE utf8mb4_general_ci;
```

## 删除数据库
{{< admonition type=info title="小贴士" open=true >}}
该命令的含义是如果 awei 数据库存在则删除，不存在就不会去删除该数据库，避免执行命令报错。
{{< /admonition >}}

```mysql
DROP DATABASE IF EXISTS awei;
```

## 表的创建
首先表的创建我们需要先使用一个数据库的情况下才能去执行创建表的命令。因为一个数据库系统下拥有多个数据库，一个数据库拥有多张表。
执行下面的命令我们可以选择一个数据库：

```mysql
USE awei;
SELECT DATABASE();
```

{{< admonition type=info title="小贴士" open=true >}}
如果需要确定我们选择的数据库，我们可以使用上面第二行命令进行确认
{{< /admonition >}}

接下来我们就可以进行创建表了，下面的例子是创建一个用户表:

```mysql
CREATE TABLE tb_user (
    id INT COMMENT '编号',
    name VARCHAR(50) COMMENT '名称',
    age INT COMMENT '年龄',
    gender VARCHAR(1) COMMENT '性别'
) COMMENT '用户表';
```

{{< admonition type=info title="小贴士" open=true >}}
创建完后，我们可以使用 **SHOW TABLES;** 命令查看 **awei** 数据库的所有表信息；如果想查看表的详细信息则可以使用
 **DESC tb_user;** 命令去查询。
{{< /admonition >}}

