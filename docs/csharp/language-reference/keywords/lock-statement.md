---
title: "“锁定”语句（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords: lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="94c9a-102">“锁定”语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="94c9a-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="94c9a-103">`lock` 关键字将语句块标记为关键部分，方法是获取给定对象的互斥锁，执行语句，然后释放该锁。</span><span class="sxs-lookup"><span data-stu-id="94c9a-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="94c9a-104">以下示例包含一个 `lock` 语句。</span><span class="sxs-lookup"><span data-stu-id="94c9a-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="94c9a-105">有关详细信息，请参阅[线程同步](../../programming-guide/concepts/threading/thread-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="94c9a-105">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94c9a-106">备注</span><span class="sxs-lookup"><span data-stu-id="94c9a-106">Remarks</span></span>  
 <span data-ttu-id="94c9a-107">`lock` 关键字可确保当一个线程位于代码的关键部分时，另一个线程不会进入该关键部分。</span><span class="sxs-lookup"><span data-stu-id="94c9a-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="94c9a-108">如果其他线程尝试进入锁定的代码，则它将一直等待（即被阻止），直到该对象被释放。</span><span class="sxs-lookup"><span data-stu-id="94c9a-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="94c9a-109">[线程](../../programming-guide/concepts/threading/index.md)一节讨论了线程处理。</span><span class="sxs-lookup"><span data-stu-id="94c9a-109">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>  
  
 <span data-ttu-id="94c9a-110">`lock` 关键字在块的开始处调用 <xref:System.Threading.Monitor.Enter%2A>，而在块的结尾处调用 <xref:System.Threading.Monitor.Exit%2A>。</span><span class="sxs-lookup"><span data-stu-id="94c9a-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="94c9a-111">如果 <xref:System.Threading.Thread.Interrupt%2A> 中断正在等待输入 `lock` 语句的线程，将引发 <xref:System.Threading.ThreadInterruptedException>。</span><span class="sxs-lookup"><span data-stu-id="94c9a-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="94c9a-112">通常，应避免锁定 `public` 类型，否则实例将超出代码的控制范围。</span><span class="sxs-lookup"><span data-stu-id="94c9a-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="94c9a-113">常见的结构 `lock (this)`、`lock (typeof (MyType))` 和 `lock ("myLock")` 违反此准则：</span><span class="sxs-lookup"><span data-stu-id="94c9a-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="94c9a-114">如果可以公开访问实例，将出现 `lock (this)` 问题。</span><span class="sxs-lookup"><span data-stu-id="94c9a-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="94c9a-115">如果可以公开访问 `lock (typeof (MyType))`，将出现 `MyType` 问题。</span><span class="sxs-lookup"><span data-stu-id="94c9a-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="94c9a-116">由于进程中使用同一字符串的任何其他代码都将共享同一个锁，因此出现 `lock("myLock")` 问题。</span><span class="sxs-lookup"><span data-stu-id="94c9a-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="94c9a-117">最佳做法是定义 `private` 对象来进行锁定，或者定义 `private static` 对象变量来保护所有实例所共有的数据。</span><span class="sxs-lookup"><span data-stu-id="94c9a-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="94c9a-118">在 `lock` 语句的正文中不能使用 [await](../../../csharp/language-reference/keywords/await.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="94c9a-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94c9a-119">示例</span><span class="sxs-lookup"><span data-stu-id="94c9a-119">Example</span></span>  
 <span data-ttu-id="94c9a-120">下面演示在 C# 中使用未锁定的线程的简单示例。</span><span class="sxs-lookup"><span data-stu-id="94c9a-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="94c9a-121">示例</span><span class="sxs-lookup"><span data-stu-id="94c9a-121">Example</span></span>  
 <span data-ttu-id="94c9a-122">下例使用线程和 `lock`。</span><span class="sxs-lookup"><span data-stu-id="94c9a-122">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="94c9a-123">只要 `lock` 语句存在，语句块就是关键部分并且 `balance` 永远不会是负数。</span><span class="sxs-lookup"><span data-stu-id="94c9a-123">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="94c9a-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="94c9a-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94c9a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94c9a-125">See Also</span></span>  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [<span data-ttu-id="94c9a-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="94c9a-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="94c9a-127">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="94c9a-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="94c9a-128">线程处理</span><span class="sxs-lookup"><span data-stu-id="94c9a-128">Threading</span></span>](../../programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="94c9a-129">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="94c9a-129">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="94c9a-130">语句关键字</span><span class="sxs-lookup"><span data-stu-id="94c9a-130">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="94c9a-131">互锁操作</span><span class="sxs-lookup"><span data-stu-id="94c9a-131">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="94c9a-132">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="94c9a-132">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="94c9a-133">线程同步</span><span class="sxs-lookup"><span data-stu-id="94c9a-133">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)
