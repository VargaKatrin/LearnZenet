# Zenet


> name ```Async```

> type ```class```

> path ```Zenet/Network/Async.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Async" is used to run a "System.Action" in
background ie it uses " System.Threading.ThreadPool"
to perform heavy tasks or choking
outside the main "Thread".
```


##### Español 🇪🇸
```
"Zenet.Async" se utiliza para ejecutar un "System.Action" en
fondo, es decir, utiliza " System.Threading.ThreadPool"
para realizar tareas pesadas o asfixia
fuera del "hilo" principal.
```


##### 中国人 🇨🇳
```
“Zenet->Async”用于运行“System.Action”
背景，即它使用“System.Threading.ThreadPool”
执行繁重的任务或窒息
在主“线程”之外。
```


##### 日本 🇯🇵
```
「Zenet->Async」は、「System.Action」を実行するために使用されます
背景、つまり「System.Threading.ThreadPool」を使用します
重い仕事や窒息を実行するには
メインの「スレッド」の外側。
```


##### Português 🇵🇹
```
"Zenet->Async" é usando para rodar uma "System.Action" em background
ou seja ela usa " System.Threading.ThreadPool" para executar tarefas pessadas
ou bloqueante fora da "Thread" principal.
```


## Namespace

```csharp
using Zenet.Network;
```

## Sample usage


#### Sample 1
```csharp
using Zenet.Network;

Async.Thread(() =>
{
    Console.WriteLine("hello world, on background");
});
```


#### Sample 2
```csharp
using Zenet.Network;

void Callback()
{
    Console.WriteLine("hello world, on background");
}

Async.Thread(Callback);
```


#### Sample 3
```csharp
using System.Threading;
using Zenet.Network;

void Callback(int delay)
{
    System.Threading.Thread.Sleep(delay);
    Console.WriteLine("hello world, on background");
}

Async.Thread(() => Callback(50));

Async.Thread(() =>
{
    Callback(10);
    Callback(20);
});
```
