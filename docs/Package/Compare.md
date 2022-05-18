# Zenet


> name ```Compare```

> type ```static class```

> path ```Zenet/Package/Compare.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Compare" It is a class that transposes some functions to
data comparison and "Compare.Bytes(byte[], byte[])" compares if both data has the same value.
```


##### Español 🇪🇸
```
"Zenet->Compare" Es una clase que transpone algunas funciones a
comparación de datos y "Compare.Bytes(byte[], byte[])" compara si ambos datos tienen el mismo valor.
```


##### 中国人 🇨🇳
```
“Zenet->Compare” 它是一个将一些函数转换为
数据比较和 "Compare.Bytes(byte[], byte[])" 比较两个数据是否具有相同的值。
```


##### 日本 🇯🇵
```
「Zenet->Compare」 いくつかの機能をに置き換えたクラスです
データ比較と「Compare.Bytes（byte []、byte []）」は、両方のデータの値が同じかどうかを比較します。
```


##### Português 🇵🇹
```
"Zenet->Compare" É uma classe que transpõe algumas funções para
comparação de dados e "Compare.Bytes(byte[], byte[])" compara se ambos os dados tem o mesmo valor.
```


## Namespace

```csharp
using Zenet.Package;
```

## Sample usage


#### Sample 1 - Compare bytes
```csharp
using System;
using Zenet.Package;

byte[] data1 = new byte[] { 10, 20, 30 };
byte[] data2 = new byte[] { 10, 20, 30 };
byte[] data3 = new byte[] { 05, 10, 15 };

bool compare1 = Compare.Bytes(data1, data2);     // compare bytes
bool compare2 = Compare.Bytes(data2, data3);     // compare bytes

Console.WriteLine(compare1);                     // output: True
Console.WriteLine(compare2);                     // output: False

```


#### Sample 2 - Compare byte
```csharp
using System;
using Zenet.Package;

byte data1 = 10;
byte data2 = 10;
byte data3 = 20;

bool compare1 = Compare.Byte(data1, data2);      // compare bytes
bool compare2 = Compare.Byte(data2, data3);      // compare bytes

Console.WriteLine(compare1);                     // output: True
Console.WriteLine(compare2);                     // output: False

```


#### Sample 2 - Compare int
```csharp
using System;
using Zenet.Package;

int data1 = 1000;
int data2 = 1000;
int data3 = 2000;

bool compare1 = Compare.Int(data1, data2);       // compare bytes
bool compare2 = Compare.Int(data2, data3);       // compare bytes

Console.WriteLine(compare1);                     // output: True
Console.WriteLine(compare2);                     // output: False

```


#### Sample 3 - Compare string
```csharp
using System;
using Zenet.Package;
  
string data1 = "zeloot";
string data2 = "zeloot";
string data3 = "zenet";

bool compare1 = Compare.String(data1, data2);    // compare bytes
bool compare2 = Compare.String(data2, data3);    // compare bytes

Console.WriteLine(compare1);                     // output: True
Console.WriteLine(compare2);                     // output: False

```
