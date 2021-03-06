## 数组

数组是编程语言的基础数据结构之一，也是几乎所有语言自带的数据结构，有效使用数组是程序员基本功之一。在使用数组的时候，我们必须了解几个数组的常识。

 - 数组有两种，一种是数字索引数组或叫做无键名索引，索引从默认以数字作为索引0，1，2，3......; 一种叫做字符索引数组或叫键名索引，以字符串作为索引，需要定义键名。有些语言将其统一对待，有些语言将其分开对待
 - 数组的索引，一般来说从0开始。 
 - 数组在强类型语言中，使用前需要定义大小，不可动态增减数组大小；而在弱类型语言中，无需定义大小，可以动态增减大小。
 - 强类型语言数组数组每个成员的类型必须一致；弱类型语言的数组，成员类型不必一致
 - 而大部分语言中，数组是引用传值；有某些语言中，数组是赋值传值。
 - unshift为从数组开头放入，push为从数组最后放入，shift取出数组的第一个值，pop从取出数组的最后一个值。
 - 数组有两部分组成，一个叫做键（key），一个叫做值（值）;键在数组中是唯一的，用于在数组中定位。
 - 数组长度为其中值的数量，可以获取;数组最后一个成员位置一般是长度减1

-----------------
###分语言介绍


#### JavaScript数组
JavaScript的数组是动态数组，无需定义大小和类型。如果需要所有数组是同一类型，必须进行检查。

变量是**引用传递**。

在JavaScript中键名索引数组就是类，或是以类的形式出现的。JavaScript能把类和键名索引数组统一起来是其特有的特色。所以有键名数组和无键名数组在JavaScript是两个不同的概念。所以一些数组方法无法使用比如php, push, unshift和shift

``` javascript
   var list=[];//定义一个空变量
   
   var list=["apple","banana",3,4,{"a":"1"}];//类型混合的无键名变量
   var value=list[1];//索引1的值，value赋值为banana
   list.length//5，告知数组大小
   
   var list1=[];
   var list2=[];
   list1 === list2 // false, 引用传值，内存位置不同
	
   var list= [1,2,3,4,5];
   var value=list.pop();//list等于 [1,2,3,4] value等于5
   var value=list.shift();//list等于 [2,3,4] value等于1
   list.unshift(0);//list等于 [0,2,3,4] 
   list.push(6);//list等于 [0, 2, 3, 4, 6]

   var list = {}//定义一个空键名变量
   var list = {"one":1,"two":"2"}//定义一个键名变量
   var value = list["two"]//索引two的值，value赋值为"2"

```

#### PHP的数组

PHP的数组是动态数组，无需定义大小和类型。如果需要所有数组是同一类型，必须进行检查。

变量是**赋值传递**。

在PHP中，有键名数组和无键名数组是统一的数组类型，相同对待。无键名索引以数字作为键名。但也因为如此，数组长度减1并不是数组最后一个索引位置。

``` php
	$list = []; 
	$list = ["apple","banana",3,4,["a"=>"1"],"two"=>"2"];//类型混合变量
	$list[] = "abc"//增加一个"abc"的值
	$list[1] //"banana"
	$list["two"] //"2"

	$list1=[1,2];
	$list2=[1,2];
	var_dump($list1===$list2);//true,赋值引用，数组定义相同就是相等。


    $list= [1,"two"=>2,3,4,5];
    $value=array_pop($list);//$list等于 [1,"two"=>2,3,4] $value等于5
    $value=array_shift($list);//$list$list等于 ["two"=>2,3,4] $value等于1
    array_unshift($list,0);//$list等于 [0,"two"=>2,3,4]
    array_push($list,6);//$list等于 [0,"two"=>2,3,4,6]
    count($list);//5，告知数组大小


```


-------------------
### 数组使用方法

#### 数组赋值

```javascript
//JavaScript
var  list = [];//空数组
var  list = ["one",2,"three",4,{'a':'apple'}];//混合类型的数组
list[3]="three"
var  list = {"one":1,"two":"2"};//键值数组
list["three"]="3";

```


```php
//PHP
$list = [];//空数组
$list = ["one",2,"three",4,["a"=>"apple"]];//混合类型的数组
$list = ["one"=>1,"two"=>"2"];//键值数组
$list[3]="three";
$list["three"]="3";

```

#### 数组操作

```javascript
//JavaScript
  var list= [1,2,3,4,5];
  var value=list.pop();//list等于 [1,2,3,4] value等于5
  var value=list.shift();//list等于 [2,3,4] value等于1
  list.unshift(0);//list等于 [0,2,3,4] 
  list.push(6);//list等于 [0, 2, 3, 4, 6]

```

```php
//PHP

  $list= [1,"two"=>2,3,4,5];
  $value=array_pop($list);//$list等于 [1,"two"=>2,3,4] $value等于5
  $value=array_shift($list);//$list$list等于 ["two"=>2,3,4] $value等于1
  array_unshift($list,0);//$list等于 [0,"two"=>2,3,4]
  array_push($list,6);//$list等于 [0,"two"=>2,3,4,6]
```


#### 数组大小

```javascript
//JavaScript
  var list= [1,2,3,4,5];
  list.length//5，告知数组大小

```

```php
//PHP

  $list= [1,"two"=>2,3,4,5];
  count($list);//5，告知数组大小
```

#### 数组比较

```javascript
//JavaScript
  var list1=[];
  var list2=[];
  list1 === list2 // false, 引用传值，内存位置不同

```

```php
//PHP

  $list1=[1,2];
  $list2=[1,2];
  $list1===$list2;//true,赋值引用，数组定义相同就是相等。
```