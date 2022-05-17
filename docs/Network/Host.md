# Zenet


> name ```Host```

> type ```class```

> path ```Zenet/Network/Host.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Host" It is an abrastation that facilitates the creation of an endpoint,
using: "string ip & int port", "IPAddress ip & int port", "EndPoint" and "IPendPoint"
as different parameters to create a valid endpoint.
as it makes the backend much easier because it just needs
of a class that abstracts everything. and the data can be
queried or consumed the following properties: "IPAddress", "Port", "AddressFamily" and "IPendPoint"
```


##### Español 🇪🇸
```
"Zenet->Host" Es una abrasión que facilita la creación de un punto final,
usando: "string ip & int port", "IPAddress ip & int port", "EndPoint" y "IPendPoint"
como diferentes parámetros para crear un punto final válido.
ya que hace que el backend sea mucho más fácil porque solo necesita
de una clase que abstrae todo. y los datos pueden ser
consultó o consumió las siguientes propiedades: "IPAddress", "Port", "AddressFamily" y "IPendPoint"
```


##### 中国人 🇨🇳
```
“Zenet->Host” 这是一种促进端点创建的磨损，
使用：“string ip & int port”、“IPAddress ip & int port”、“EndPoint”和“IPendPoint”
作为不同的参数来创建一个有效的端点。
因为它使后端更容易，因为它只需要
抽象一切的类。 并且数据可以是
查询或消费了以下属性：“IPAddress”、“Port”、“AddressFamily”和“IPendPoint”
```


##### 日本 🇯🇵
```
「Zenet->Host」これは、エンドポイントの作成を容易にするアブレーションです。
使用：「stringip＆int port」、「IPAddress ip＆int port」、「EndPoint」、「IPendPoint」
有効なエンドポイントを作成するためのさまざまなパラメータとして。
必要なだけなので、バックエンドがはるかに簡単になります
すべてを抽象化するクラスの。 そしてデータはすることができます
次のプロパティを照会または消費しました：「IPAddress」、「Port」、「AddressFamily」、および「IPendPoint」
```


##### Português 🇵🇹
```
"Zenet->Host" É uma abrastacao que facilita a criação de um endpoint,
utilizando: "string ip & int port", "IPAddress ip & int port", "EndPoint" e "IPEndPoint"
como parâmetros diferentes para criar um endpoint válido.
pois isso torna o backend muito mais fácil porque ele só precisa
de uma classe que abstraia tudo. e os dados pode ser
consultado ou consumido as seguintes propriedade: "IPAddress", "Port", "AddressFamily" e "IPEndPoint"
```


## Namespace

```csharp
using Zenet.Network;
```

## Sample usage


#### Sample 1
```csharp
using System;
using Zenet.Network;

Host host = new Host("0.0.0.0", 80);

Console.WriteLine($"port: {host.Port}");         // output: 80
Console.WriteLine($"address: {host.IPAddress}"); // output: 0.0.0.0 
Console.WriteLine($"family: {host.Family}");     // output: -
Console.WriteLine($"endpoint: {host.EndPoint}"); // output: 0.0.0.0:80
```


#### Sample 2 - Using IPAddress/Port
```csharp
using System;
using System.Net;
using Zenet.Network;

Host host = new Host(IPAddresss.Any, 80);        // IPAddress.Any is 0.0.0.0
Console.WriteLine(host);                         // output: 0.0.0.0:80
```


#### Sample 2 - Using EndPoint
```csharp
using System;
using System.Net;
using Zenet.Network;

EndPoint endpoint = new IPEndPoint(IPAddress.Any, 80);  // IPAddress.Any is 0.0.0.0
Host host = new Host(endpoint);
Console.WriteLine(host);                                // output: 0.0.0.0:80
```


#### Sample 2 - Using IPEndPoint
```csharp
using System;
using System.Net;
using Zenet.Network;

IPEndPoint endpoint = new IPEndPoint(IPAddress.Parse("127.0.0.1"), 80);
Host host = new Host(endpoint);
Console.WriteLine(host);                         // output: 127.0.0.1:80
```
