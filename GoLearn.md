# **Go学习笔记**

#### **2019/01/05**
- 变量声明：

```
    var var_name var_type

    just like :
    var i int
    i = 10    
    or:
    i := 10

    const CONST = 3                 //常量定义

    var ArrayList = [3]int{1,2,3}  //数组定义（指定长度）
    or:
    var ArratList = [...]int{1,2,3}

    var SliceList = []int{1,2,3}     //切片定义（不指定长度）
    //切片操作：
    SliceList = append (SliceList, 4)//添加
```

- 流程控制：

```
    if i {
        //code
    } else {
        //code
    }

    for index , n := range numberlist {
        fmt.PrintIn(index, n)
    }
```

- 函数：

```
    func ExFunc(typename string, typename int) （int， error)     {
        return max, nil     //nil用于返回错误类型    
    }//返回值为Int的函数

    or:
    func ExFunc1(name1, name2, name3 string) (max int) {
        //name1, name2, name3均为string类型
        return //返回max
   }

```

- 结构体

```
type Name struct{
    ID uint
    TIME string
    age int
}//大写表示公有，小写表示私有

type Mixname struct{
    Name //与Name结构体组合
    NICKNAME string
}

```
