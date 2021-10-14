# head-first-go

---

# 命令

使用Go标准格式重新格式化代码

```go
go fmt file.go
```

将原代码文件编译为而二进制文件

```go
go build file.go
```

编译并运行程序，而不保存可执行文件

```go
go run file.go
```

查看版本号

```go
go version
```

# 函数

## 反射

返回参数类型

```go
reflect.TypeOf(val) 
```

## IO

查看文件信息

```go
fileInfo, err := os.Stat("my.txt")
fileInfo.size() // 文件大小
```

从键盘获取文本的“缓冲读取器”

```go
reader := bufio.NewReader(os.Stdin)
intpu := reader.ReadString('\n') // 返回用户输入的所有内容，直到按下<Enter>键为止
```

## 数学

向下取舍为最近的整数

```go
math.Floor(val)
```

随机数

```go
rand.Seed(seconds) // 播种随机数生成器
rand.Intn(100)+1 //1~100 的随机数
```

## 字符串

删除空白字符：

```go
strings.TrimSpace()
```

将字符串转换为数字：

```go
strconv.ParseFloat(需要转换的字符串, 结果的精度位数)

strconv.ParseFloat(input, 64) // 浮点数
strconv.Atoi(val) // 整数
```

在字符串中替换子字符串

```go
replacer := strings.NewReplacer("#", "o") // 返回一个strings.Replacer, 设置每个“#”替换为“o”
replacer.Replace(input) // 调用Replace
```

将每个单词的第一个字母大写

```go
strings.Title("head first go") // Head First Go
```

## 日期

返回一个当前日期和时间的 time.Time

```go
var now time.Time = time.Now()
now.Year() // 返回年份
now.Unix() // 当前日期和时间的整数形式（秒数）
```

# 语法

## 函数

Go允许函数调用返回多个值

## 变量声明

- 短变量声明中只有一个变量必须是新的

- 避免给变量取与类型、函数、或包相同的名称，这会使变量遮盖（覆盖）具有相同名称的内容

- 零值

```go
int 0
float64 0
bool false
string ""
```

## 运算

Go中的数学运算和比较运算 要求包含的值具有相同的类型， 若不是则报错

## 包名与导入路径

Go语言不要求包名和其导入路径有任何关系

但按照惯例，导入路径的最后（或唯一）一段也用作包名

eg:

```go
导入路径      包名
"archive"     archive
"archive/zip" zip
```