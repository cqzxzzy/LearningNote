# Go学习笔记

#### **2019/01/07**

##### Json的处理

```
例如：{
	"get_time": "2019-01-07",
	"news": [{
		"newsname": "Beijing_VPN",
		"newsurl": "127.0.0.10"
	}, {
		"newsname": "Beijing_VPN",
		"newsurl": "127.0.0.10"
	}]
}
```

- **1.声明结构体**
    含有string, float64, string, nil等变量类型
    使用tag  `json:"get_time"`是小写的首字母同样能够输出

```
    type NewsMessage struct {
	PostTime string `json:"get_time"`
	NewsList []News `json:"news"`
}

type News struct {
	NewsName string `json:"newsname"`
	NewsUrl   string  `json:"newsurl"`
}
```

- **2.解析Json**
    使用Unmarshal()函数：
    > func Unmarshal(data []byte, v interface{}) error

```
func main() {
	s := NewsMessage{}
	str := []byte(`
{
	"get_time": "2006-01-02",
	"news": [{
		"newsname": "TEST1",
		"newsurl": "127.0.0.1"
	}, {
		"newsname": "TEST2",
		"newsurl": "127.0.0.2"
	}]
}`)

	json.Unmarshal(str, &s)
	fmt.Println(s)

```

- **3.构造Json**
    使用Marshal()函数：
    > func Marshal(v interface{}) ([]byte, error)

```
func main() {
    var json_file NewsMessage
    json_file.PostTime = time.Now().Format("2006-01-02")
    json_file.NewsList = append(json_file.NewsList, News{NewsName: "Golang",NewsUrl: "www.golang.org"})

    json_fin, err := json.Marshal(json_file)
    if err != nil {
        fmt.Println("json err:", err)
    }
 }
```

#### **2019/01/05**
##### 变量声明：
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

##### 流程控制：

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

##### 函数：
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

##### 结构体

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
