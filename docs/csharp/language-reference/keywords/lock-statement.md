---
title: lock 语句（C# 参考）
description: 使用 C# lock 语句同步对共享资源的线程访问
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858351"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="3d0cb-103">lock 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3d0cb-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="3d0cb-104">`lock` 语句获取给定对象的互斥 lock，执行语句 lock，然后释放 lock。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-104">The `lock` statement obtains the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="3d0cb-105">持有 lock 时，持有 lock 的线程可以再次获取并释放 lock。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-105">While a lock is held, the thread that holds the lock can again obtain and release the lock.</span></span> <span data-ttu-id="3d0cb-106">阻止任何其他线程获取 lock 并等待释放 lock。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-106">Any other thread is blocked from obtaining the lock and waits until the lock is released.</span></span>

<span data-ttu-id="3d0cb-107">`lock` 语句具有以下格式</span><span class="sxs-lookup"><span data-stu-id="3d0cb-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="3d0cb-108">其中 `x` 是[引用类型](reference-types.md)的表达式。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="3d0cb-109">它完全等同于</span><span class="sxs-lookup"><span data-stu-id="3d0cb-109">It's precisely equivalent to</span></span>

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

<span data-ttu-id="3d0cb-110">由于该代码使用 [try...finally](try-finally.md) 块，即使在 `lock` 语句的正文中引发异常，也会释放 lock。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="3d0cb-111">在 `lock` 语句的正文中不能使用 [await](await.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d0cb-112">备注</span><span class="sxs-lookup"><span data-stu-id="3d0cb-112">Remarks</span></span>

<span data-ttu-id="3d0cb-113">当同步对共享资源的线程访问时，请锁定专用对象实例（例如，`private readonly object balanceLock = new object();`）或另一个不太可能被代码无关部分用作 lock 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-113">When you synchronize thread access to shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="3d0cb-114">避免对不同的共享资源使用相同的 lock 对象实例，因为这可能导致死锁或锁争用。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="3d0cb-115">具体而言，应避免使用</span><span class="sxs-lookup"><span data-stu-id="3d0cb-115">In particular, avoid using</span></span>

- <span data-ttu-id="3d0cb-116">`this`（调用方可能将其用作 lock），</span><span class="sxs-lookup"><span data-stu-id="3d0cb-116">`this` (might be used by the callers as a lock),</span></span>
- <span data-ttu-id="3d0cb-117"><xref:System.Type> 实例（可以通过 [typeof](typeof.md) 运算符或反射获取），</span><span class="sxs-lookup"><span data-stu-id="3d0cb-117"><xref:System.Type> instances (might be obtained by the [typeof](typeof.md) operator or reflection),</span></span>
- <span data-ttu-id="3d0cb-118">字符串实例，包括字符串文本，</span><span class="sxs-lookup"><span data-stu-id="3d0cb-118">string instances, including string literals,</span></span>

<span data-ttu-id="3d0cb-119">用作 lock 对象。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-119">as lock objects.</span></span>

## <a name="example"></a><span data-ttu-id="3d0cb-120">示例</span><span class="sxs-lookup"><span data-stu-id="3d0cb-120">Example</span></span>

<span data-ttu-id="3d0cb-121">以下示例定义了一个 `Account` 类，该类通过锁定专用的 `balanceLock` 实例来同步对其专用 `balance` 字段的访问。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="3d0cb-122">使用相同的实例进行锁定可确保尝试同时调用 `Debit` 或 `Credit` 方法的两个线程无法同时更新 `balance` 字段。</span><span class="sxs-lookup"><span data-stu-id="3d0cb-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="3d0cb-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3d0cb-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3d0cb-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d0cb-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="3d0cb-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3d0cb-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3d0cb-126">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3d0cb-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3d0cb-127">语句关键字</span><span class="sxs-lookup"><span data-stu-id="3d0cb-127">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="3d0cb-128">互锁操作</span><span class="sxs-lookup"><span data-stu-id="3d0cb-128">Interlocked operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="3d0cb-129">同步基元概述</span><span class="sxs-lookup"><span data-stu-id="3d0cb-129">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)