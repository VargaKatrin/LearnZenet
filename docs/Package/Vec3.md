# Zenet


> name ```Vec3```

> type ```class```

> path ```Zenet/Package/Vec3.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Vec3" It is a form of vector3 encoding. This only makes sense when used with
"Zenet.Package.Package2" as it creates and retrieves a byte[] Vector3
```


##### Español 🇪🇸
```
"Zenet->Vec3" Es una forma de codificación vector3. Esto solo tiene sentido cuando se usa con
"Zenet.Package.Package2" ya que crea y recupera un byte[] Vector3
```


##### 中国人 🇨🇳
```
“Zenet->Vec3” 它是vector3编码的一种形式。 这仅在与
“Zenet.Package.Package2”一起使用时才有意义，因为它会创建和检索 byte[] Vector3
```


##### 日本 🇯🇵
```
「Zenet->Vec3」 これは、vector3エンコーディングの形式です。 これは、
「Zenet.Package.Package2」と一緒に使用した場合にのみ意味があります。これは、byte[]Vector3を作成および取得するためです。
```


##### Português 🇵🇹
```
"Zenet->Vec3" É uma forma de codificação vector3. Isso só faz sentido quando usado com 
"Zenet.Package.Package2", pois cria e recupera um Vector3 de byte[]
```


## Namespace

```csharp
using Zenet.Package;
```

## Sample usage


#### Sample 1 - Create Vec3
```csharp
using System;
using Zenet.Package;

Vec3 position1 = new Vec3();          // X=0, Y=0, Z=0
Vec3 position2 = new Vec3(1, 2, 3);   // X=1, Y=2, Z=3

Console.WriteLine(position2.X);       // output: 1
Console.WriteLine(position2.Y);       // output: 2
Console.WriteLine(position2.Z);       // output: 3

```


#### Sample 2 - Convert Vec3 to byte[]
```csharp
using System;
using Zenet.Package;

Vec3 position = new Vec3(1, 2, 3);  // X=1, Y=2, Z=3

byte[] array = Vec3.ToBytes(position);

```


#### Sample 3 - Convert byte[] to Vec3
```csharp
using System;
using Zenet.Package;

#region Vec3 to byte[]

Vec3 position = new Vec3(1, 2, 3);  // X=1, Y=2, Z=3
byte[] array = Vec3.ToBytes(position);

#endregion

#region byte[] to Vec3

Vec3 other = Vec3.ToVec3(array); 

#endregion

```
