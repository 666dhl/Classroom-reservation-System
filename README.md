# 教室预约系统

## 1.教室框架

### 1.1 系统简介

* 学校现有几个规格不同的教室，由于使用时经常出现"撞车"现象,现开发一套教室预约系统，解决这一问题。
* ![image-20220209164317065](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/ff794569671915b16d6e86bfbd91e1e.png)

#### 1.1.1 身份简介

分别有三种身份使用该程序

* **学生代表**：申请使用教室
* **教师**：审核学生的预约申请
* **管理员**：给学生、教师创建账号/清空预约

#### 1.1.2 教室简介

教室总共有3间

* 1号教室   --- 最大容量20人
* 2号教室   --- 最多容量50人
* 3号教室   --- 最多容量100人

#### 1.1.3 申请简介

* 申请的订单每周由管理员负责清空。
* 学生可以预约未来一周内的教室使用，预约的日期为周一至周五，预约时需要选择预约时段（上午、下午）
* 教师来审核预约，依据实际情况审核预约通过或者不通过

#### 1.1.4 系统具体需求

* 首先进入登录界面，可选登录身份有：
  * 学生代表
  * 老师
  * 管理员
  * 退出
* 每个身份都需要进行验证后，进入子菜单
  * 学生需要输入 ：学号、姓名、登录密码
  * 老师需要输入：职工号、姓名、登录密码
  * 管理员需要输入：管理员姓名、登录密码
* 学生具体功能
  * 申请预约    ---   预约教室
  * 查看自身的预约    ---  查看自己的预约状态预约   ---   查看全部预约信息以及预约状态
  * 取消预约    ---   取消自身的预约，预约成功或审核中的预约均可取消
  * 注销登录    ---   退出登录
* 教师具体功能
  * 查看所有预约   ---   查看全部预约信息以及预约状态
  * 审核预约    ---   对学生的预约进行审核
  * 注销登录    ---   退出登录
* 管理员具体功能
  * 添加账号    ---   添加学生或教师的账号，需要检测学生编号或教师职工号是否重复
  * 查看账号    ---   可以选择查看学生或教师的全部信息
  * 查看教室    ---   查看所有教室的信息
  * 清空预约    ---   清空所有预约记录
  * 注销登录    ---   退出登录

![cabf84d26b646b916ed75912390369e](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/cabf84d26b646b916ed75912390369e.png)

### 1.2 系统模型

#### 1.2.1 main()函数

![08531d42860f7aefa44782d03495b2c](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/08531d42860f7aefa44782d03495b2c.png)

![45cac1aae68c089c2d86ba60b1b13a1](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/45cac1aae68c089c2d86ba60b1b13a1.png)

#### 1.2.2 学生

![b49b6d1db86c07ed578e028bc35ce5e](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/b49b6d1db86c07ed578e028bc35ce5e.png)

#### 1.2.2 老师

![6fb25fe69b932d54f9dc77c767b3ad3](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/6fb25fe69b932d54f9dc77c767b3ad3.png)

#### 1.2.3 管理者

![e3ade13a70834fe50f450ccdf7464d2](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/e3ade13a70834fe50f450ccdf7464d2.png)

## 2.详细注释

详细的源码讲解请看注释

## 3.特性

1.不同角色赋予不同的功能，通过对虚函数的重写实现了不同展示菜单等。

2.通过饿汉单例模式创建预约清单对象，避免对预约清单类的反复创建。

3.通过加入类的组合的方式，降低继承父类内部细节对子类可见，以及对父类的方法更改（如增加一个参数）子类也需要进行更改的高耦合的缺点。

## 4.编译及测试

```
编译过程：
1.git clone https://github.com/666dhl/Classroom-reservation-System.git
2.cd Classroom-Reservation-System/include
3.g++ -o main main.cpp student.cpp teacher.cpp manager.cpp orderFile.cpp 
4../main
```

测试

![4d3c69fcda9e879473ebe1e65d04657](https://github.com/666dhl/Classroom-reservation-System/blob/main/images/4d3c69fcda9e879473ebe1e65d04657.png)

