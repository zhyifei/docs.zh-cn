---
title: "调度线程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a>调度线程
每个线程都有分配给它的线程优先级。 公共语言运行时内创建的线程最初分配的优先级**ThreadPriority.Normal**。 在运行时以外创建的线程会保留它们进入托管的环境之前所具有的优先级。 你可以获取或设置与任何线程的优先级**Thread.Priority**属性。  
  
 线程都计划进行执行基于它们的优先级别。 即使在运行时执行线程，所有线程都是由操作系统都分配处理器时间段。 用于确定线程的执行顺序的计划算法的详细信息因每个操作系统而异。 在某些操作系统下 （的这些可执行的线程） 的最高优先级的线程始终计划要首先运行。 如果具有相同优先级的多个线程都可用，通过以该优先级，提供在其执行中的固定的时间片的每个线程的线程的计划程序周期。 只要可用来运行具有较高优先级的线程，就不会较低优先级的线程执行。 当在给定的优先级存在没有其他可运行的线程时，计划程序将移动到下一步的较低优先级，并计划在执行该优先级的线程。 如果较高的优先级线程变得可运行的占用较低优先级的线程和更高优先级的线程可以再次执行。 除此之外，系统还可以调整线程优先级动态间前景色和背景移动应用程序的用户界面为。 其他操作系统可能选择使用不同的计划算法。  
  
## <a name="see-also"></a>另请参阅  
 [使用线程和线程处理](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Windows 中的托管和非托管线程](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
