---
title: 读取器/编写器锁
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208174"
---
# <a name="reader-writer-locks"></a>读取器/编写器锁
借助 <xref:System.Threading.ReaderWriterLockSlim> 类，多个线程可以同时读取资源，但线程必须等待排他锁生成，才能对资源执行写入操作。  
  
 可以在应用中使用 <xref:System.Threading.ReaderWriterLockSlim>，以便在访问共享资源的线程之间进行协作同步。 锁应用于 <xref:System.Threading.ReaderWriterLockSlim> 本身。  
  
 与任何线程同步机制一样，必须确保没有线程规避 <xref:System.Threading.ReaderWriterLockSlim> 提供的锁定。 为了确保这一点，一种方法是设计一个类来封装共享资源。 此类的成员访问专用共享资源，并使用专用 <xref:System.Threading.ReaderWriterLockSlim> 执行同步。 有关示例，请参阅 <xref:System.Threading.ReaderWriterLockSlim> 类的代码示例。 <xref:System.Threading.ReaderWriterLockSlim> 非常高效，可用于同步各个对象。  
  
 请设计应用的结构，以最大限度地缩短读取和写入操作的持续时间。 长时间的写入操作会直接影响吞吐量，因为写锁是独占锁。 长时间的读取操作会阻止正在等待的编写器，并且如果至少有一个线程在等待写入访问，请求读取访问的线程也会受阻止。  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 有下面两个读取器-编写器锁：<xref:System.Threading.ReaderWriterLockSlim> 和 <xref:System.Threading.ReaderWriterLock>。 建议对所有新开发的项目使用 <xref:System.Threading.ReaderWriterLockSlim>。 虽然 <xref:System.Threading.ReaderWriterLockSlim> 类似于 <xref:System.Threading.ReaderWriterLock>，但不同之处在于，前者简化了递归规则以及锁状态的升级和降级规则。 <xref:System.Threading.ReaderWriterLockSlim> 避免了许多潜在的死锁情况。 另外，<xref:System.Threading.ReaderWriterLockSlim> 的性能显著优于 <xref:System.Threading.ReaderWriterLock>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [线程处理](../../../docs/standard/threading/index.md)  
- [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
