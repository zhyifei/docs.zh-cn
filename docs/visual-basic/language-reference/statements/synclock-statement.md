---
title: SyncLock 语句（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: e981ee727b66ecda392014fd3ee8ca6f1526cd2e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72578903"
---
# <a name="synclock-statement"></a>SyncLock 语句
在执行块之前获取语句块的排他锁。  
  
## <a name="syntax"></a>语法  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>部件  
 `lockobject`  
 必须的。 计算结果为对象引用的表达式。  
  
 `block`  
 可选。 获取锁时要执行的语句块。  
  
 `End SyncLock`  
 终止 `SyncLock` 块。  
  
## <a name="remarks"></a>备注  
 @No__t_0 语句可确保多个线程不会同时执行语句块。 `SyncLock` 阻止每个线程进入块，直到没有其他线程执行它。  
  
 @No__t_0 的最常见用途是防止多个线程同时更新数据。 如果操作数据的语句必须在不中断的情况下完成，请将它们放在 `SyncLock` 块内。  
  
 受排他锁保护的语句块有时称为*临界区*。  
  
## <a name="rules"></a>规则  
  
- 产生. 不能从块外分支到 `SyncLock` 块。  
  
- 锁定对象值。 不能 `Nothing` `lockobject` 的值。 在 `SyncLock` 语句中使用该锁对象之前，必须先创建它。  
  
     执行 `SyncLock` 块时，不能更改 `lockobject` 的值。 机制要求锁定对象保持不变。  
  
- 不能在 `SyncLock` 块中使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)运算符。  
  
## <a name="behavior"></a>行为  
  
- 机制. 当线程到达 `SyncLock` 语句时，它将计算 `lockobject` 表达式并挂起执行，直到它获取表达式返回的对象上的排他锁。 当另一个线程到达 `SyncLock` 语句时，在第一个线程执行 `End SyncLock` 语句之前，不会获取锁。  
  
- 受保护的数据。 如果 `lockobject` 是 `Shared` 变量，则排他锁可防止类的任何实例中的线程执行 `SyncLock` 块，而任何其他线程正在执行该线程。 这会保护在所有实例之间共享的数据。  
  
     如果 `lockobject` 是实例变量（不 `Shared`），则锁定会阻止在当前实例中运行的线程与同一实例中的另一个线程同时执行 `SyncLock` 块。 这将保护由单个实例维护的数据。  
  
- 获取和发布。 @No__t_0 块的行为类似于 `Try...Finally` 构造，其中 `Try` 块在 `lockobject` 上获取排他锁，而 `Finally` 块释放它。 因此，无论退出块的方式如何，`SyncLock` 块均可保证锁的版本。 即使在发生未经处理的异常时也是如此。  
  
- 框架调用。 @No__t_0 块通过调用 <xref:System.Threading> 命名空间中的 `Monitor` 类的 `Enter` 和 `Exit` 方法获取并释放排他锁。  
  
## <a name="programming-practices"></a>编程做法  
 @No__t_0 表达式应始终计算为仅属于您的类的对象。 你应声明一个 `Private` 对象变量来保护属于当前实例的数据，或声明一个 `Private Shared` 对象变量来保护所有实例通用的数据。  
  
 不应使用 `Me` 关键字为实例数据提供锁定对象。 如果类的外部代码具有对类的实例的引用，则可以使用该引用作为 `SyncLock` 块完全不同的锁对象，从而保护不同的数据。 通过这种方式，类和其他类可以相互阻止执行其不相关的 `SyncLock` 块。 类似地锁定字符串可能会产生问题，因为使用相同字符串的进程中的任何其他代码都将共享同一个锁。  
  
 还应不要使用 `Me.GetType` 方法为共享数据提供锁定对象。 这是因为 `GetType` 始终针对给定类名称返回相同的 `Type` 对象。 外部代码可以对类调用 `GetType`，并获取正在使用的同一个锁对象。 这会导致两个类从其 `SyncLock` 块彼此阻止。  
  
## <a name="examples"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例演示维护简单消息列表的类。 它将消息保存在一个数组中，并将该数组的最后一个使用元素保存在一个变量中。 @No__t_0 过程将递增最后一个元素并存储新消息。 这两个操作受 `SyncLock` 和 `End SyncLock` 语句保护，因为当最后一个元素递增后，必须存储新消息，任何其他线程才能再次递增最后一个元素。  
  
 如果 `simpleMessageList` 类在其所有实例中共享一个消息列表，则 `messagesList` 和 `messagesLast` 的变量将被声明为 `Shared`。 在这种情况下，还应 `Shared` 变量 `messagesLock`，以便每个实例使用单个锁对象。  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>描述  
 下面的示例使用线程并 `SyncLock`。 只要存在 `SyncLock` 语句，语句块就会成为关键部分，并且 `balance` 绝不会成为负数。 您可以注释掉 `SyncLock` 和 `End SyncLock` 语句，以查看退出 `SyncLock` 关键字的效果。  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>注释  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [同步基元概述](../../../standard/threading/overview-of-synchronization-primitives.md)
