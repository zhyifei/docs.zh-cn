---
title: lock 语句（C# 参考）
description: 'lock 关键字用于线程处理中 '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931188"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="a0a07-103">lock 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a0a07-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="a0a07-104">`lock` 关键字将语句块标记为关键部分，方法是获取给定对象的互斥锁，执行语句，然后释放该锁。</span><span class="sxs-lookup"><span data-stu-id="a0a07-104">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="a0a07-105">以下示例包含一个 `lock` 语句。</span><span class="sxs-lookup"><span data-stu-id="a0a07-105">The following example includes a `lock` statement.</span></span>

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

<span data-ttu-id="a0a07-106">有关详细信息，请参阅[线程同步](../../programming-guide/concepts/threading/thread-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a07-106">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="a0a07-107">备注</span><span class="sxs-lookup"><span data-stu-id="a0a07-107">Remarks</span></span>

<span data-ttu-id="a0a07-108">`lock` 关键字可确保当一个线程位于代码的关键部分时，另一个线程不会进入该关键部分。</span><span class="sxs-lookup"><span data-stu-id="a0a07-108">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="a0a07-109">如果其他线程尝试进入锁定的代码，则它将一直等待（即被阻止），直到该对象被释放。</span><span class="sxs-lookup"><span data-stu-id="a0a07-109">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>

<span data-ttu-id="a0a07-110">[线程](../../programming-guide/concepts/threading/index.md)一节讨论了线程处理。</span><span class="sxs-lookup"><span data-stu-id="a0a07-110">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>

<span data-ttu-id="a0a07-111">`lock` 关键字在块的开始处调用 <xref:System.Threading.Monitor.Enter%2A>，而在块的结尾处调用 <xref:System.Threading.Monitor.Exit%2A>。</span><span class="sxs-lookup"><span data-stu-id="a0a07-111">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="a0a07-112">如果 <xref:System.Threading.Thread.Interrupt%2A> 中断正在等待输入 `lock` 语句的线程，将引发 <xref:System.Threading.ThreadInterruptedException>。</span><span class="sxs-lookup"><span data-stu-id="a0a07-112">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>

<span data-ttu-id="a0a07-113">通常，应避免锁定 `public` 类型，否则实例将超出代码的控制范围。</span><span class="sxs-lookup"><span data-stu-id="a0a07-113">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="a0a07-114">常见的结构 `lock (this)`、`lock (typeof (MyType))` 和 `lock ("myLock")` 违反此准则：</span><span class="sxs-lookup"><span data-stu-id="a0a07-114">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>

- <span data-ttu-id="a0a07-115">如果可以公开访问实例，将出现 `lock (this)` 问题。</span><span class="sxs-lookup"><span data-stu-id="a0a07-115">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>

- <span data-ttu-id="a0a07-116">如果可以公开访问 `lock (typeof (MyType))`，将出现 `MyType` 问题。</span><span class="sxs-lookup"><span data-stu-id="a0a07-116">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>

- <span data-ttu-id="a0a07-117">由于进程中使用同一字符串的任何其他代码都将共享同一个锁，因此出现 `lock("myLock")` 问题。</span><span class="sxs-lookup"><span data-stu-id="a0a07-117">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>

<span data-ttu-id="a0a07-118">最佳做法是定义 `private` 对象来进行锁定，或者定义 `private static` 对象变量来保护所有实例所共有的数据。</span><span class="sxs-lookup"><span data-stu-id="a0a07-118">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>

<span data-ttu-id="a0a07-119">在 `lock` 语句的正文中不能使用 [await](await.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="a0a07-119">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="example---threads-without-locking"></a><span data-ttu-id="a0a07-120">示例 - 未锁定的线程</span><span class="sxs-lookup"><span data-stu-id="a0a07-120">Example - Threads without locking</span></span>

<span data-ttu-id="a0a07-121">下面演示在 C# 中使用未锁定的线程的简单示例：</span><span class="sxs-lookup"><span data-stu-id="a0a07-121">The following sample shows a simple use of threads without locking in C#:</span></span>

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a><span data-ttu-id="a0a07-122">示例 - 使用锁定的线程</span><span class="sxs-lookup"><span data-stu-id="a0a07-122">Example - Threads using locking</span></span>

<span data-ttu-id="a0a07-123">下例使用线程和 `lock`。</span><span class="sxs-lookup"><span data-stu-id="a0a07-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="a0a07-124">只要 `lock` 语句存在，语句块就是关键部分并且 `balance` 永远不会是负数：</span><span class="sxs-lookup"><span data-stu-id="a0a07-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number:</span></span>

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="a0a07-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a0a07-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a0a07-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0a07-126">See also</span></span>

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [<span data-ttu-id="a0a07-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a0a07-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="a0a07-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a0a07-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a0a07-129">线程处理</span><span class="sxs-lookup"><span data-stu-id="a0a07-129">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
- [<span data-ttu-id="a0a07-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a0a07-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a0a07-131">语句关键字</span><span class="sxs-lookup"><span data-stu-id="a0a07-131">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="a0a07-132">互锁操作</span><span class="sxs-lookup"><span data-stu-id="a0a07-132">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="a0a07-133">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="a0a07-133">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)
- [<span data-ttu-id="a0a07-134">线程同步</span><span class="sxs-lookup"><span data-stu-id="a0a07-134">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)