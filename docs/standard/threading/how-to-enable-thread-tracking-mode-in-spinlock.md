---
title: "如何：在 SpinLock 中启用线程跟踪模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>如何：在 SpinLock 中启用线程跟踪模式
<xref:System.Threading.SpinLock?displayProperty=nameWithType>是一个可用于具有等待时间非常短的方案的低级别的相互排斥锁。 <xref:System.Threading.SpinLock>不是可重入的。 线程进入锁定后，它必须之前可以重新输入正确退出锁。 通常情况下，重新进入锁定状态的任何尝试都会导致死锁，并且死锁可以很难进行调试。 作为辅助手段开发，<xref:System.Threading.SpinLock?displayProperty=nameWithType>支持一个线程尝试重新输入已持有的锁时引发异常的线程跟踪模式。 这样可以更易于定位的锁未正确退出点。 你可以通过启用线程跟踪模式<xref:System.Threading.SpinLock>构造函数采用一个布尔值输入参数，并传入的自变量`true`。 开发和测试阶段完成后，关闭线程跟踪模式以更好的性能。  
  
## <a name="example"></a>示例  
 下面的示例演示线程跟踪模式。 正确退出锁的行注释掉，以模拟导致以下结果之一的编码错误：  
  
-   如果引发异常<xref:System.Threading.SpinLock>通过使用的自变量创建`true`(`True`在 Visual Basic 中)。  
  
-   如果发生死锁<xref:System.Threading.SpinLock>通过使用的自变量创建`false`(`False`在 Visual Basic 中)。  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>另请参阅  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
