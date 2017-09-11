---
title: "“锁定”语句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00dcbb9feec11587265bf61667d91c2c1598065b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="da3ed-102">“锁定”语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="da3ed-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="da3ed-103">`lock` 关键字将语句块标记为关键部分，方法是获取给定对象的互斥锁，执行语句，然后释放该锁。</span><span class="sxs-lookup"><span data-stu-id="da3ed-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="da3ed-104">以下示例包含一个 `lock` 语句。</span><span class="sxs-lookup"><span data-stu-id="da3ed-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="da3ed-105">有关详细信息，请参阅[线程同步](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)。</span><span class="sxs-lookup"><span data-stu-id="da3ed-105">For more information, see [Thread Synchronization](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da3ed-106">备注</span><span class="sxs-lookup"><span data-stu-id="da3ed-106">Remarks</span></span>  
 <span data-ttu-id="da3ed-107">`lock` 关键字可确保当一个线程位于代码的关键部分时，另一个线程不会进入该关键部分。</span><span class="sxs-lookup"><span data-stu-id="da3ed-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="da3ed-108">如果其他线程尝试进入锁定的代码，则它将一直等待（即被阻止），直到该对象被释放。</span><span class="sxs-lookup"><span data-stu-id="da3ed-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="da3ed-109">[线程](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)一节讨论了线程处理。</span><span class="sxs-lookup"><span data-stu-id="da3ed-109">The section [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) discusses threading.</span></span>  
  
 <span data-ttu-id="da3ed-110">`lock` 关键字在块的开始处调用 <xref:System.Threading.Monitor.Enter%2A>，而在块的结尾处调用 <xref:System.Threading.Monitor.Exit%2A>。</span><span class="sxs-lookup"><span data-stu-id="da3ed-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="da3ed-111">如果 <xref:System.Threading.Thread.Interrupt%2A> 中断正在等待输入 `lock` 语句的线程，将引发 <xref:System.Threading.ThreadInterruptedException>。</span><span class="sxs-lookup"><span data-stu-id="da3ed-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="da3ed-112">通常，应避免锁定 `public` 类型，否则实例将超出代码的控制范围。</span><span class="sxs-lookup"><span data-stu-id="da3ed-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="da3ed-113">常见的结构 `lock (this)`、`lock (typeof (MyType))` 和 `lock ("myLock")` 违反此准则：</span><span class="sxs-lookup"><span data-stu-id="da3ed-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="da3ed-114">如果可以公开访问实例，将出现 `lock (this)` 问题。</span><span class="sxs-lookup"><span data-stu-id="da3ed-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="da3ed-115">如果可以公开访问 `lock (typeof (MyType))`，将出现 `MyType` 问题。</span><span class="sxs-lookup"><span data-stu-id="da3ed-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="da3ed-116">由于进程中使用同一字符串的任何其他代码都将共享同一个锁，因此出现 `lock("myLock")` 问题。</span><span class="sxs-lookup"><span data-stu-id="da3ed-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="da3ed-117">最佳做法是定义 `private` 对象来进行锁定，或者定义 `private static` 对象变量来保护所有实例所共有的数据。</span><span class="sxs-lookup"><span data-stu-id="da3ed-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="da3ed-118">在 `lock` 语句的正文中不能使用 [await](../../../csharp/language-reference/keywords/await.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="da3ed-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da3ed-119">示例</span><span class="sxs-lookup"><span data-stu-id="da3ed-119">Example</span></span>  
 <span data-ttu-id="da3ed-120">下面演示在 C# 中使用未锁定的线程的简单示例。</span><span class="sxs-lookup"><span data-stu-id="da3ed-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 <span data-ttu-id="da3ed-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="da3ed-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="da3ed-122">示例</span><span class="sxs-lookup"><span data-stu-id="da3ed-122">Example</span></span>  
 <span data-ttu-id="da3ed-123">下例使用线程和 `lock`。</span><span class="sxs-lookup"><span data-stu-id="da3ed-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="da3ed-124">只要 `lock` 语句存在，语句块就是关键部分并且 `balance` 永远不会是负数。</span><span class="sxs-lookup"><span data-stu-id="da3ed-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 <span data-ttu-id="da3ed-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="da3ed-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="da3ed-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="da3ed-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da3ed-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da3ed-127">See Also</span></span>  
 <span data-ttu-id="da3ed-128"><xref:System.Reflection.MethodImplAttributes></span><span class="sxs-lookup"><span data-stu-id="da3ed-128"><xref:System.Reflection.MethodImplAttributes></span></span>   
 <span data-ttu-id="da3ed-129"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="da3ed-129"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="da3ed-130">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="da3ed-131">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="da3ed-132">[线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span><span class="sxs-lookup"><span data-stu-id="da3ed-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span></span>  
 <span data-ttu-id="da3ed-133">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="da3ed-134">[语句关键字](../../../csharp/language-reference/keywords/statement-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-134">[Statement Keywords](../../../csharp/language-reference/keywords/statement-keywords.md) </span></span>  
 <span data-ttu-id="da3ed-135">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="da3ed-135">@System.Threading.Monitor</span></span>   
 <span data-ttu-id="da3ed-136">[互锁操作](../../../standard/threading/interlocked-operations.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-136">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) </span></span>  
 <span data-ttu-id="da3ed-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span><span class="sxs-lookup"><span data-stu-id="da3ed-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span></span>  
 [<span data-ttu-id="da3ed-138">线程同步</span><span class="sxs-lookup"><span data-stu-id="da3ed-138">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)

