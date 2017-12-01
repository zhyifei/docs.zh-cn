---
title: "读取器/编写器锁"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a>读取器/编写器锁
<xref:System.Threading.ReaderWriterLockSlim>类使多个线程能够同时读取的资源，但需要一个线程等待的排他锁，若要写入的资源。  
  
 你可以使用<xref:System.Threading.ReaderWriterLockSlim>中你的应用程序，以提供访问共享的资源的线程间的协作同步。 锁占用<xref:System.Threading.ReaderWriterLockSlim>本身。  
  
 因为任何线程的同步机制，你必须确保没有线程绕过提供的锁定<xref:System.Threading.ReaderWriterLockSlim>。 确保这一点的一种方法是设计一个封装共享的资源的类。 此类将提供访问私有共享的资源和使用私有成员<xref:System.Threading.ReaderWriterLockSlim>同步。 有关示例，请参阅的代码示例<xref:System.Threading.ReaderWriterLockSlim>类。 <xref:System.Threading.ReaderWriterLockSlim>是高效到可用于同步单个对象。  
  
 构建你的应用程序，以最小化的持续时间的读取和写入操作。 长时间的写入操作直接影响吞吐量，因为写入锁是排他。 长时间的读取操作块等待编写器，并且，如果至少一个线程在等待以进行写访问，将以及阻止请求读取访问权限的线程。  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]具有两个读取器 / 编写器锁，<xref:System.Threading.ReaderWriterLockSlim>和<xref:System.Threading.ReaderWriterLock>。 <xref:System.Threading.ReaderWriterLockSlim>建议对于所有新的开发。 <xref:System.Threading.ReaderWriterLockSlim>类似于<xref:System.Threading.ReaderWriterLock>，但它已简化为递归以及升级或降级锁定状态的规则。 <xref:System.Threading.ReaderWriterLockSlim>可避免潜在的死锁的很多情况。 此外的性能<xref:System.Threading.ReaderWriterLockSlim>明显优于<xref:System.Threading.ReaderWriterLock>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
