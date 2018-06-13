---
title: 如何：使用 ConcurrentBag 创建目标池
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9239a38d1970a052567f111b57be2b6596f1e5f1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32768302"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="ef2a8-102">如何：使用 ConcurrentBag 创建目标池</span><span class="sxs-lookup"><span data-stu-id="ef2a8-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="ef2a8-103">本示例演示如何使用并发包来实现对象池。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="ef2a8-104">在需要某个类的多个实例并且创建或销毁该类的成本很高的情况下，对象池可以改进应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="ef2a8-105">客户端程序请求新对象时，对象池先尝试提供一个已创建并返回到该池的对象。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="ef2a8-106">仅在没有可用对象时，才会创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="ef2a8-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> 用于存储对象，因为它支持快速插入和删除，特别是在同一线程既添加又删除项时。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="ef2a8-108">本示例可进一步扩充为以包数据结构实现的 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 为依据生成，就像 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601> 一样。</span><span class="sxs-lookup"><span data-stu-id="ef2a8-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef2a8-109">示例</span><span class="sxs-lookup"><span data-stu-id="ef2a8-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="ef2a8-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef2a8-110">See Also</span></span>  
 [<span data-ttu-id="ef2a8-111">线程安全集合</span><span class="sxs-lookup"><span data-stu-id="ef2a8-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
