---
title: SyncLock 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 6f5a89ebe359ca2fdae1d5545192dc2dcecca6a2
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244152"
---
# <a name="synclock-statement"></a><span data-ttu-id="a1f40-102">SyncLock 语句</span><span class="sxs-lookup"><span data-stu-id="a1f40-102">SyncLock Statement</span></span>
<span data-ttu-id="a1f40-103">执行块之前获取语句块的排他的锁。</span><span class="sxs-lookup"><span data-stu-id="a1f40-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f40-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1f40-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="a1f40-105">部件</span><span class="sxs-lookup"><span data-stu-id="a1f40-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="a1f40-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="a1f40-106">Required.</span></span> <span data-ttu-id="a1f40-107">计算结果为一个对象引用的表达式。</span><span class="sxs-lookup"><span data-stu-id="a1f40-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="a1f40-108">可选。</span><span class="sxs-lookup"><span data-stu-id="a1f40-108">Optional.</span></span> <span data-ttu-id="a1f40-109">要获取的锁时执行的语句块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="a1f40-110">终止`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1f40-111">备注</span><span class="sxs-lookup"><span data-stu-id="a1f40-111">Remarks</span></span>  
 <span data-ttu-id="a1f40-112">`SyncLock`语句可确保多个线程不会在同一时间中执行的语句块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="a1f40-113">`SyncLock` 阻止每个线程进入块，直到没有其他线程正在执行它。</span><span class="sxs-lookup"><span data-stu-id="a1f40-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="a1f40-114">最常用的`SyncLock`是由多个线程同时更新保护数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="a1f40-115">如果操作的数据的语句必须转到完成而不发生中断，则将它们放`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="a1f40-116">受保护的排他锁的语句块有时称为*临界区*。</span><span class="sxs-lookup"><span data-stu-id="a1f40-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a1f40-117">规则</span><span class="sxs-lookup"><span data-stu-id="a1f40-117">Rules</span></span>  
  
-   <span data-ttu-id="a1f40-118">分支。</span><span class="sxs-lookup"><span data-stu-id="a1f40-118">Branching.</span></span> <span data-ttu-id="a1f40-119">不能分支到`SyncLock`阻止其块外部。</span><span class="sxs-lookup"><span data-stu-id="a1f40-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="a1f40-120">锁定对象值。</span><span class="sxs-lookup"><span data-stu-id="a1f40-120">Lock Object Value.</span></span> <span data-ttu-id="a1f40-121">值`lockobject`不能为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="a1f40-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="a1f40-122">必须先将其用于创建的锁对象`SyncLock`语句。</span><span class="sxs-lookup"><span data-stu-id="a1f40-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="a1f40-123">无法更改的值`lockobject`执行时`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="a1f40-124">该机制要求的锁对象保持不变。</span><span class="sxs-lookup"><span data-stu-id="a1f40-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="a1f40-125">不能使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)中的运算符`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a1f40-126">行为</span><span class="sxs-lookup"><span data-stu-id="a1f40-126">Behavior</span></span>  
  
-   <span data-ttu-id="a1f40-127">机制。</span><span class="sxs-lookup"><span data-stu-id="a1f40-127">Mechanism.</span></span> <span data-ttu-id="a1f40-128">当一个线程到达`SyncLock`语句，它的计算结果`lockobject`表达式和挂起执行，直到它将获取由表达式返回的对象上的排他锁。</span><span class="sxs-lookup"><span data-stu-id="a1f40-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="a1f40-129">在另一个线程到达`SyncLock`语句，它并不获取锁直到第一个线程执行`End SyncLock`语句。</span><span class="sxs-lookup"><span data-stu-id="a1f40-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="a1f40-130">受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-130">Protected Data.</span></span> <span data-ttu-id="a1f40-131">如果`lockobject`是`Shared`变量，防止类的任何实例中的线程执行的排他锁`SyncLock`阻止其他线程执行时。</span><span class="sxs-lookup"><span data-stu-id="a1f40-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="a1f40-132">这将保护在所有实例间共享的数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="a1f40-133">如果`lockobject`是一个实例变量 (不`Shared`)，锁将阻止执行从当前实例中运行的线程`SyncLock`处的同一实例中的另一个线程在同一时间块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="a1f40-134">这样可以保护单个实例保留的数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="a1f40-135">获取和释放。</span><span class="sxs-lookup"><span data-stu-id="a1f40-135">Acquisition and Release.</span></span> <span data-ttu-id="a1f40-136">一个`SyncLock`块的行为类似于`Try...Finally`在其中构造`Try`块上获取排他锁`lockobject`和`Finally`块释放它。</span><span class="sxs-lookup"><span data-stu-id="a1f40-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="a1f40-137">正因为如此，`SyncLock`块都可确保释放锁，不管您如何退出块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="a1f40-138">这是甚至在未处理的异常的情况下，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="a1f40-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="a1f40-139">框架将调用。</span><span class="sxs-lookup"><span data-stu-id="a1f40-139">Framework Calls.</span></span> <span data-ttu-id="a1f40-140">`SyncLock`块将获取并释放通过调用的排他锁`Enter`并`Exit`的方法`Monitor`类<xref:System.Threading>命名空间。</span><span class="sxs-lookup"><span data-stu-id="a1f40-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="a1f40-141">编程做法</span><span class="sxs-lookup"><span data-stu-id="a1f40-141">Programming Practices</span></span>  
 <span data-ttu-id="a1f40-142">`lockobject`表达式应计算结果始终为以独占方式属于您的类的对象。</span><span class="sxs-lookup"><span data-stu-id="a1f40-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="a1f40-143">应声明`Private`对象变量来保护属于当前实例的数据或`Private Shared`对象变量来保护数据普遍适用于所有实例。</span><span class="sxs-lookup"><span data-stu-id="a1f40-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="a1f40-144">不应使用`Me`关键字提供锁定对象实例数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="a1f40-145">如果您的类的外部代码可以对您的类的实例的引用，它可以使用该引用的锁定对象作为`SyncLock`块完全不同，如果您保护不同的数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="a1f40-146">这样一来，您的类和其他类可能会互相阻塞执行其不相关`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="a1f40-147">因为使用相同的字符串的过程中的任何其他代码将共享同一个锁，同样锁定一个字符串，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="a1f40-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="a1f40-148">您也不应使用`Me.GetType`方法以提供锁定对象的共享数据。</span><span class="sxs-lookup"><span data-stu-id="a1f40-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="a1f40-149">这是因为`GetType`始终返回同一个`Type`给定的类名称的对象。</span><span class="sxs-lookup"><span data-stu-id="a1f40-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="a1f40-150">外部代码可以调用`GetType`在类上，并获取正在使用的同一个锁对象。</span><span class="sxs-lookup"><span data-stu-id="a1f40-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="a1f40-151">这将导致两个类相互阻止其`SyncLock`块。</span><span class="sxs-lookup"><span data-stu-id="a1f40-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a1f40-152">示例</span><span class="sxs-lookup"><span data-stu-id="a1f40-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="a1f40-153">描述</span><span class="sxs-lookup"><span data-stu-id="a1f40-153">Description</span></span>  
 <span data-ttu-id="a1f40-154">下面的示例显示了维护一个简单的消息列表的类。</span><span class="sxs-lookup"><span data-stu-id="a1f40-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="a1f40-155">它包含消息数组中而且上次使用的变量中的该数组的元素。</span><span class="sxs-lookup"><span data-stu-id="a1f40-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="a1f40-156">`addAnotherMessage`过程递增的最后一个元素，并将存储新消息。</span><span class="sxs-lookup"><span data-stu-id="a1f40-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="a1f40-157">这两项操作受`SyncLock`和`End SyncLock`语句，因为后递增的最后一个元素，任何其他线程可以再次增加的最后一个元素之前，必须将存储新消息。</span><span class="sxs-lookup"><span data-stu-id="a1f40-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="a1f40-158">如果`simpleMessageList`类共享其所有实例，这些变量之间的消息的一个列表`messagesList`并`messagesLast`将被声明为`Shared`。</span><span class="sxs-lookup"><span data-stu-id="a1f40-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="a1f40-159">在此情况下，变量`messagesLock`也应是`Shared`，以便将每个实例使用的单个锁对象。</span><span class="sxs-lookup"><span data-stu-id="a1f40-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a1f40-160">代码</span><span class="sxs-lookup"><span data-stu-id="a1f40-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="a1f40-161">描述</span><span class="sxs-lookup"><span data-stu-id="a1f40-161">Description</span></span>  
 <span data-ttu-id="a1f40-162">下面的示例使用线程和`SyncLock`。</span><span class="sxs-lookup"><span data-stu-id="a1f40-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="a1f40-163">只要`SyncLock`语句，语句块就是关键部分和`balance`永远不会是负数。</span><span class="sxs-lookup"><span data-stu-id="a1f40-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="a1f40-164">您可以注释掉`SyncLock`并`End SyncLock`语句，以查看影响省去`SyncLock`关键字。</span><span class="sxs-lookup"><span data-stu-id="a1f40-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a1f40-165">代码</span><span class="sxs-lookup"><span data-stu-id="a1f40-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="a1f40-166">注释</span><span class="sxs-lookup"><span data-stu-id="a1f40-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f40-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1f40-167">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="a1f40-168">线程同步</span><span class="sxs-lookup"><span data-stu-id="a1f40-168">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="a1f40-169">线程处理</span><span class="sxs-lookup"><span data-stu-id="a1f40-169">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
