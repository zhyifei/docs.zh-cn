---
title: 异步编程模式
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249031"
---
# <a name="asynchronous-programming-patterns"></a>异步编程模式

.NET Framework 提供了执行异步操作的三种模式：  
  
- **异步编程模型 (APM)** 模式（即 <xref:System.IAsyncResult> 模式），在该模式下，异步操作需要使用 `Begin` 和 `End` 方法（例如，异步写入操作需要使用 `BeginWrite` 和 `EndWrite` 方法） 不建议新的开发使用此模式。 有关详细信息，请参阅[异步编程模型 (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)。  
  
- **基于事件的异步模式 (EAP)**，这种模式需要 `Async` 后缀，也需要一个或多个事件、事件处理程序委托类型和 `EventArg` 派生类型。 EAP 是在 .NET Framework 2.0 中引入的。 不建议新的开发使用这种模式。 有关详细信息，请参阅[基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)。  
  
- **基于任务的异步模式 (TAP)**，该模式使用单一方法表示异步操作的开始和完成。 TAP 是在 .NET Framework 4 中引入的，并且它是在 .NET Framework 中进行异步编程的推荐使用方法。 C# 中的 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 关键词以及 Visual Basic 语言中的 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 运算符为 TAP 添加了语言支持。 有关详细信息，请参阅[基于任务的异步模式 (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)。  
  
## <a name="comparing-patterns"></a>比较模式  

为了快速比较这三种模式的异步操作方式，请考虑使用从指定偏移量处起将指定量数据读取到提供的缓冲区中的`Read`方法：  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
此方法对应的 APM 将公开 `BeginRead` 和 `EndRead` 方法：  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
对应的 EAP 将公开以下类型和成员的集：  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
对应的 TAP 将公开以下单个 `ReadAsync` 方法：  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
为了全面讨论 TAP、APM 和 EAP，请参阅下一节中提供的链接。  
  
## <a name="related-topics"></a>相关主题

| 标题 | 描述 |
| ----- | ----------- |
| [异步编程模型 (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | 描述使用 <xref:System.IAsyncResult> 接口提供异步行为的旧模型。 不建议新的开发使用此模型。 |
| [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | 描述提供异步行为的基于事件的旧模型。 不建议新的开发使用此模型。 |
| [基于任务的异步模式 (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | 描述基于 <xref:System.Threading.Tasks> 命名空间的新异步模式。 此模型是在 .NET Framework 4 及更高版本中进行异步编程的推荐使用方法。 |

## <a name="see-also"></a>请参阅

- [C# 中的异步编程](~/docs/csharp/async.md)   
- [F# 中的异步编程](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [使用 Async 和 Await 的异步编程 (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/async/index.md)
