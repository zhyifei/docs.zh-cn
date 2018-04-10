---
title: “锁定”语句（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a>“锁定”语句（C# 参考）
`lock` 关键字将语句块标记为关键部分，方法是获取给定对象的互斥锁，执行语句，然后释放该锁。 以下示例包含一个 `lock` 语句。  
  
```csharp  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
```  
  
 有关详细信息，请参阅[线程同步](../../programming-guide/concepts/threading/thread-synchronization.md)。  
  
## <a name="remarks"></a>备注  
 `lock` 关键字可确保当一个线程位于代码的关键部分时，另一个线程不会进入该关键部分。 如果其他线程尝试进入锁定的代码，则它将一直等待（即被阻止），直到该对象被释放。  
  
 [线程](../../programming-guide/concepts/threading/index.md)一节讨论了线程处理。  
  
 `lock` 关键字在块的开始处调用 <xref:System.Threading.Monitor.Enter%2A>，而在块的结尾处调用 <xref:System.Threading.Monitor.Exit%2A>。 如果 <xref:System.Threading.Thread.Interrupt%2A> 中断正在等待输入 `lock` 语句的线程，将引发 <xref:System.Threading.ThreadInterruptedException>。  
  
 通常，应避免锁定 `public` 类型，否则实例将超出代码的控制范围。 常见的结构 `lock (this)`、`lock (typeof (MyType))` 和 `lock ("myLock")` 违反此准则：  
  
-   如果可以公开访问实例，将出现 `lock (this)` 问题。  
  
-   如果可以公开访问 `lock (typeof (MyType))`，将出现 `MyType` 问题。  
  
-   由于进程中使用同一字符串的任何其他代码都将共享同一个锁，因此出现 `lock("myLock")` 问题。  
  
 最佳做法是定义 `private` 对象来进行锁定，或者定义 `private static` 对象变量来保护所有实例所共有的数据。  
  
 在 `lock` 语句的正文中不能使用 [await](../../../csharp/language-reference/keywords/await.md) 关键字。  
  
## <a name="example"></a>示例  
 下面演示在 C# 中使用未锁定的线程的简单示例。  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>示例  
 下例使用线程和 `lock`。 只要 `lock` 语句存在，语句块就是关键部分并且 `balance` 永远不会是负数。  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [线程处理](../../programming-guide/concepts/threading/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [语句关键字](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [互锁操作](../../../standard/threading/interlocked-operations.md)  
 [AutoResetEvent](../../../standard/threading/autoresetevent.md)  
 [线程同步](../../programming-guide/concepts/threading/thread-synchronization.md)
