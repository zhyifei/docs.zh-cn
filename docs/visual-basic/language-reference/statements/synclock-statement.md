---
title: "SyncLock 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c826e1ba592dfc4f2899a26102466d2e7df54f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="synclock-statement"></a>SyncLock 语句
在执行块之前获取语句块的排他的锁。  
  
## <a name="syntax"></a>语法  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>部件  
 `lockobject`  
 必需。 计算结果为一个对象引用的表达式。  
  
 `block`  
 可选。 若要获取锁时执行的语句块。  
  
 `End SyncLock`  
 终止`SyncLock`块。  
  
## <a name="remarks"></a>备注  
 `SyncLock`语句可确保多个线程不会在同一时间中执行的语句块。 `SyncLock`防止每个线程正在进入块，直到没有其他线程正在执行它。  
  
 最常见的用途`SyncLock`是为了防止数据由多个线程同时更新。 如果操作数据的语句必须转到完成而不会中断，则将它们放`SyncLock`块。  
  
 有时称为受的排他锁的语句块*临界区*。  
  
## <a name="rules"></a>规则  
  
-   分支。 不能分支到`SyncLock`阻止其在块外部。  
  
-   锁定对象值。 值`lockobject`不能为`Nothing`。 你必须使用在之前创建的锁对象`SyncLock`语句。  
  
     无法更改值`lockobject`执行时`SyncLock`块。 机制都要求的锁对象保持不变。  
  
-   不能使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)中的运算符`SyncLock`块。  
  
## <a name="behavior"></a>行为  
  
-   机制。 在线程到达`SyncLock`语句，它的计算结果`lockobject`表达式将暂停执行，直到它将获取由表达式返回的对象的排他锁。 在另一个线程到达`SyncLock`语句，它不会获取锁直到第一个线程执行`End SyncLock`语句。  
  
-   受保护的数据。 如果`lockobject`是`Shared`变量，阻止类的任何实例中的线程执行的排他锁`SyncLock`阻止其他任何线程执行它时。 这可在所有实例间共享的数据。  
  
     如果`lockobject`是一个实例变量 (不`Shared`)，此锁将防止执行从当前实例中运行的线程`SyncLock`处的同一实例中的另一个线程在同一时间块。 这可维护的单个实例数据。  
  
-   获取和发布。 A`SyncLock`块的行为类似`Try...Finally`顺序构造`Try`块上获取排他锁`lockobject`和`Finally`块释放它。 因此，`SyncLock`块都可确保释放锁，不管您如何退出块。 这是 true 即使发生未经处理的异常。  
  
-   框架调用。 `SyncLock`块获取，并通过调用释放排他锁`Enter`和`Exit`方法`Monitor`类<xref:System.Threading>命名空间。  
  
## <a name="programming-practices"></a>编程做法  
 `lockobject`表达式应计算结果始终为仅属于你的类的对象。 应声明`Private`对象变量来保护数据属于当前实例，或`Private Shared`对象变量来保护数据普遍适用于所有实例。  
  
 不应使用`Me`关键字提供锁定的实例对象数据。 如果你的类的外部的代码可以对你的类的实例的引用，它可以使用该引用的锁对象作为`SyncLock`块完全不同于你的帐户，保护不同的数据。 这种方式，你的类和其他类将无法相互阻止执行其不相关`SyncLock`块。 因为使用相同的字符串的进程中的任何其他代码将共享同一个锁，则同样锁定对字符串可能会产生问题。  
  
 你也不应使用`Me.GetType`方法以提供的锁对象共享数据。 这是因为`GetType`始终返回相同`Type`给定的类名称的对象。 外部代码可以调用`GetType`类并获取正在使用相同的锁对象。 这将导致两个类相互阻止其`SyncLock`块。  
  
## <a name="examples"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例演示维护一个简单的消息列表的类。 它包含在一个数组中的消息，而且在变量中使用该数组的元素的最后一个。 `addAnotherMessage`过程递增的最后一个元素，并将存储新消息。 这两项操作受`SyncLock`和`End SyncLock`语句，因为后递增的最后一个元素，其他任何线程可以再次递增的最后一个元素之前，必须将存储新消息。  
  
 如果`simpleMessageList`类共享其所有实例，变量之间的消息的一个列表`messagesList`和`messagesLast`将声明为`Shared`。 在此情况下，该变量`messagesLock`还应`Shared`，以便将每个实例所使用的单个锁对象。  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a>描述  
 下面的示例使用线程和`SyncLock`。 只要`SyncLock`语句是存在，此语句块就是临界区和`balance`永远不会为负数。 你可以注释`SyncLock`和`End SyncLock`语句，以查看省去的效果`SyncLock`关键字。  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a>注释  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [线程同步](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)  
 [线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)
