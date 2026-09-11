# 継承とインターフェース

## この章で学ぶこと

- 継承とは何かを理解する
- インターフェースとは何かを理解する
- extendsとimplementsの違いを理解する
- TERASOLUNAやSpringで利用される理由を理解する


## 継承とは

継承（Inheritance）とは、既存のクラスの機能を引き継いで新しいクラスを作る仕組みである。

例)

```text
Employee
├─ 社員番号
└─ 名前
```

↓

```text
Manager
├─ 社員番号
├─ 名前
└─ 部署
```

ManagerはEmployeeの機能を引き継ぐことができる。


## 継承の書き方

継承には extends を利用する。

例)

```java
public class Employee {

    String employeeId;

    String name;

}
```

```java
public class Manager
        extends Employee {

    String department;

}
```


## 継承による機能の利用

親クラス

```java
public class Employee {

    public