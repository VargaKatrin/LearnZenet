# Zenet


> name ```Callback```

> type ```static class```

> path ```Zenet/Network/Callback.cs```


## Utility


##### English 🇺🇸
```
"Zenet->Callback" It is a static class, which (Publish, Emit, Dispatch) event for the API to receive.
the event (Publish, Emit, Dispatch), the Trigger process can be through the one that issued it or a different
process ("Thread") "Also solving the MainThread problem in some cases. like in a game engine"
```


##### Español 🇪🇸
```
"Zenet->Callback" Es una clase estática, que (Publicar, Emitir, Despachar) evento para que reciba la API.
el evento (Publish, Emit, Dispatch), el proceso Trigger puede ser a través del que lo emitió o un proceso 
diferente ("Thread") "También resolviendo el problema de MainThread en algunos casos. Como en un motor de juego"
```


##### 中国人 🇨🇳
```
“Zenet->Callback” 它是一个静态类，API 接收它的（Publish、Emit、Dispatch）事件。 事件（Publish、Emit、Dispatch），
Trigger 进程可以通过发出它的进程或不同的进程（“Thread”）“在某些情况下也解决 MainThread 问题。就像在游戏引擎中一样”
```


##### 日本 🇯🇵
```
「Zenet->Callback」 これは静的クラスであり、APIが受信するイベント（Publish、Emit、Dispatch）です。 イベント（公開、送信、ディスパッチ）、 
トリガープロセスは、それを発行したプロセスまたは別のプロセス（「スレッド」）を介して実行できます。「ゲームエンジンの場合のよう 
に、場合によってはMainThreadの問題も解決します。」
```


##### Português 🇵🇹
```
"Zenet->Callback" É uma classe estática, que (Publica, Emite, Dispacha) evento para a API receber.
o evento (Publica, Emite, Dispacha), o processo Trigger pode ser através daquele que o emitiu ou um processo
diferente ("Thread") "Resolvendo também o problema do MainThread em alguns casos. como em um motor de jogo"
```


## Namespace

```csharp
using Zenet.Network;
```

## Sample usage


#### Sample 1
```csharp
using Zenet.Network;

// All events that api receives will be "Releasing, dispatching, dispatching" through "the same process and on this Thread that published the event"
// Todos los eventos que recibe api serán "Lanzamiento, envío, envío" a través del "mismo proceso y en este hilo que publicó el evento".
// apiが受け取るすべてのイベントは、「イベントを公開したのと同じプロセスで、このスレッド上で」「リリース、ディスパッチ、ディスパッチ」になります。
// api接收到的所有事件都将通过“同一进程和发布事件的线程”进行“释放、调度、调度”
// Todos os eventos que api recebe será "Liberando, despachando, despachando" através "do mesmo processo e neste Thread que publicou o evento"
Callback.Manual = false;
```


#### Sample 2 - On Async "ThreadPool"
```csharp
using Zenet.Network;

// enable unity "machine" manager, zenet callbacks
// habilite el administrador de "máquina" de Unity, devoluciones de llamada de zenet
// ユニティ「マシン」マネージャー、zenetコールバックを有効にする
// 启用统一“机器”管理器，zenet 回调
// permitir o gerenciador de "máquina" da unidade, retornos de chamada do zenet
Callback.Manual = true;

// Docs: https://github.com/zeloot/LearnZenet/
Async.Thread(() =>
{
    // "Releasing, dispatching, resolving" all events. All events that api receives will be "Releasing, dispatching, dispatching" through "this process and this thread"
    // "Liberar, despachar, resolver" todos los eventos. Todos los eventos que recibe api serán "Lanzamiento, envío, envío" a través de "este proceso y este hilo"
    // すべてのイベントを「解放、ディスパッチ、解決」します。 APIが受け取るすべてのイベントは、「このプロセスとこのスレッド」を介した「リリース、ディスパッチ、ディスパッチ」になります
    // “释放、调度、解决”所有事件。 api接收到的所有事件都会通过“这个进程和这个线程”进行“释放、分派、分派”
    // "Liberando, despachando, resolvendo" todos os eventos. Todos os eventos que api recebe será "Liberando, despachando, despachando" através "deste processo e neste Thread"
    while(Callback.Manual)
    {
        Callback.Update();
    }
});
```


#### Sample 3 - On unity
```csharp
using Zenet.Network;

private void Awake()
{
    // enable unity "machine" manager, zenet callbacks
    // habilite el administrador de "máquina" de Unity, devoluciones de llamada de zenet
    // ユニティ「マシン」マネージャー、zenetコールバックを有効にする
    // 启用统一“机器”管理器，zenet 回调
    // permitir o gerenciador de "máquina" da unidade, retornos de chamada do zenet
    Callback.Manual = true;
}

private void Update()
{
    /*
        What this code does is nothing more than something known as "Run On Main Thread". making the unit "manage, spread, dispatch"
        the event using the main thread. with that, our code "manage, spread, dispatch" will be able to interact with unity components since
        it was the "owning thread" that ran it. if you don't do this process, your "foreign code doesn't can handle unit components like: 
        GameObject, UI, Rigidbody", why? simple your code is on a different "Thread" "A different thread is a different process that is a different program"
        so that says the unit will rewrite the "Action" and execute itself by becoming part of the unit execution, with that your action code
        you can manipulate "GameObject, UI, Rigidbody".
    */
    
    /*
      Lo que hace este código no es más que algo conocido como "Ejecutar en hilo principal". haciendo que la unidad "gestione, difunda, despache" el evento
      usando el hilo principal. con eso, nuestro código "Administrar, difundir, enviar" podrá interactuar con los componentes de Unity, ya que fue el "proceso 
      propietario" el que lo ejecutó. si no realiza este proceso, su "código extranjero no puede manejar componentes de unidades como: 
      GameObject, UI, Rigidbody", ¿por qué? Simplemente su código está en un "Subproceso" diferente "Un subproceso diferente es un proceso diferente que es un
      programa diferente" por lo que dice la unidad reescribirá la "Acción" y se ejecutará convirtiéndose en parte de la ejecución de la unidad, con eso su código
      de acción puedes manipular "GameObject, UI, Rigidbody".
    */
  
    /* このコードが行うことは、「メインスレッドで実行」として知られているものにすぎません。ユニットを「管理、拡散、発送」する メインスレッドを使用したイベント。
      それで、私たちのコード 「管理、拡散、ディスパッチ」は、それを実行した「所有スレッド」であったため、Unityコンポーネントと対話できるようになります。
      このプロセスを実行しない場合、「外部コードは実行されません GameObject、UI、Rigidbodyなどのユニットコンポーネントを処理できます。なぜですか？単純なコードは別の
      スレッド」にあります。「別のスレッドは別のプロセスです。別のプログラムです」と言うので、ユニットは 「アクション」を書き直し、その一部になることで自分自身を実行します
      ユニットの実行、それであなたのアクションコード 「GameObject、UI、Rigidbody」を操作できます。
    */
    
    /*
      这段代码所做的无非就是所谓的“在主线程上运行”。使单位“管理、传播、调度” 使用主线程的事件。 这样，我们的代码 “管理、传播、分派”将能够与统一组件进行交互，
      因为它是运行它的“拥有线程”。 如果您不执行此过程，则您的“外来代码不会 可以处理单元组件，例如：GameObject、UI、Rigidbody”，为什么？
      简单你的代码在不同的“线程”上“不同的线程是不同的进程，是一个不同的程序”，所以该单元说 将重写“Action”并通过成为 单元执行，带有你的动作代码 您可以操作“GameObject、UI、Rigidbody”。
    */
    
    /*
      Oque esse codigo faz nada mais e doque algo conhecido como "Run On Main Thread". fazendo com que a unidade "gerencie, espalhe, despache" o evento usando o thread principal.
      com isso, nosso código "manage, spread, dispatch" poderá interagir com os componentes do unity já que foi o "thread proprietário" que o executou. se você não
      fizer esse processo, seu código "estrangeiro não pode manipular componentes de unidade como:  GameObject, UI, Rigidbody", por quê? simples seu código está em um "Thread"
      diferente "Um thread diferente é um processo diferente que é um programa diferente" então isso diz que a unidade reescreverá a "Ação" e se executará tornando-se parte da
      execução da unidade, com isso o seu codigo da ação poderá sim manipular "GameObject, UI, Rigidbody".
    */  
    Callback.Update();
}
```
