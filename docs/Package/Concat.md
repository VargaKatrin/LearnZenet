# Zenet


> name ```Cancat```

> type ```static class```

> path ```Zenet/Package/Concat.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Cancat" It is used to concatenate multiple data of type "string and byte[]",
takes infinite list of data as parameter
```


##### Español 🇪🇸
```
"Zenet->Cancat" Se utiliza para concatenar múltiples datos de tipo "cadena y byte []",
toma una lista infinita de datos como parámetro
```


##### 中国人 🇨🇳
```
“Zenet->Cancat” 用于连接多个“字符串和字节[]”
类型的数据，以无限的数据列表为参数
```


##### 日本 🇯🇵
```
「Zenet->Cancat」 これは、「string and byte []」
タイプの複数のデータを連結するために使用され、パラメーターとしてデータの無限のリストを取ります
```


##### Português 🇵🇹
```
"Zenet->Cancat" Ele é usado para concatenar vários dados do tipo "string and byte[]",
leva uma lista infinita de dados como parâmetro
```


## Namespace

```csharp
using Zenet.Package;
```

## Sample usage


#### Sample 1 - Cancat string
```csharp
using System;
using Zenet.Package;

string concats = Concat.String("Hello", " ", "World", " ", ".", ".", ".");    // add concats
Console.WriteLine(concats);                                                   // output: Hello World ...

```


#### Sample 2 - Cancat bytes
```csharp
using System;
using Zenet.Package;

byte[] data1 = new byte[] { 1, 2 };
byte[] data2 = new byte[] { 3, 4 };
byte[] data3 = new byte[] { 5, 6 };

byte[] concats = Concat.Bytes(data1, data2, data3);   // add concats

#region SHOW DATA

    string join = "";

    foreach(byte value in concats)
    {
        join += $"{value}";
    }

    Console.WriteLine(join);                   		    // output: 123456

#endregion

```
