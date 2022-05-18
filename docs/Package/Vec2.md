# Zenet


> name ```Vec2```

> type ```class```

> path ```Zenet/Package/Vec2.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Vec2" It is a form of vector2 encoding. This only makes sense when used with
"Zenet.Package.Package2" as it creates and retrieves a byte[] Vector2
```


##### Español 🇪🇸
```
"Zenet->Vec2" Es una forma de codificación vector2. Esto solo tiene sentido cuando se usa con
"Zenet.Package.Package2" ya que crea y recupera un byte[] Vector2
```


##### 中国人 🇨🇳
```
“Zenet->Vec2” 它是vector2编码的一种形式。 这仅在与
“Zenet.Package.Package2”一起使用时才有意义，因为它会创建和检索 byte[] Vector2
```


##### 日本 🇯🇵
```
「Zenet->Vec2」 これは、vector2エンコーディングの形式です。 これは、
「Zenet.Package.Package2」と一緒に使用した場合にのみ意味があります。これは、byte[]Vector2を作成および取得するためです。
```


##### Português 🇵🇹
```
"Zenet->Vec2" É uma forma de codificação vector2. Isso só faz sentido quando usado com 
"Zenet.Package.Package2", pois cria e recupera um Vector2 de byte[]
```


## Namespace

```csharp
using Zenet.Package;
```

## Sample usage


#### Sample 1 - Create Vec2
```csharp
using System;
using Zenet.Package;

Vec2 position1 = new Vec2();      // X=0, Y=0
Vec2 position2 = new Vec2(1, 2);  // X=1, Y=2

Console.WriteLine(position2.X);   // output: 1
Console.WriteLine(position2.Y);   // output: 2

```


#### Sample 2 - Convert Vec2 to byte[]
```csharp
using System;
using Zenet.Package;

Vec2 position = new Vec2(1, 2);  // X=1, Y=2

byte[] array = Vec2.ToBytes(position);

```


#### Sample 3 - Convert byte[] to Vec2
```csharp
using System;
using Zenet.Package;

#region Vec2 to byte[]

Vec2 position = new Vec2(1, 2);  // X=1, Y=2
byte[] array = Vec2.ToBytes(position);

#endregion

#region byte[] to Vec2

Vec2 other = Vec2.ToVec2(array); 

#endregion

```
