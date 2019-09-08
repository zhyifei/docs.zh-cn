---
title: 如何：将信息作为只读信息检索
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 399bf44ef5536a9adebf1cad590439741df998f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793314"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="13303-102">如何：将信息作为只读信息检索</span><span class="sxs-lookup"><span data-stu-id="13303-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="13303-103">当您不打算更改数据时，您可以通过设法产生只读结果来提高查询性能。</span><span class="sxs-lookup"><span data-stu-id="13303-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="13303-104">通过将 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 可实现只读处理。</span><span class="sxs-lookup"><span data-stu-id="13303-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13303-105">当 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 时，<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 将隐式设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="13303-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13303-106">示例</span><span class="sxs-lookup"><span data-stu-id="13303-106">Example</span></span>  
 <span data-ttu-id="13303-107">下面的代码检索雇员雇佣日期的只读集合。</span><span class="sxs-lookup"><span data-stu-id="13303-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="13303-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="13303-108">See also</span></span>

- [<span data-ttu-id="13303-109">查询概念</span><span class="sxs-lookup"><span data-stu-id="13303-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="13303-110">查询数据库</span><span class="sxs-lookup"><span data-stu-id="13303-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="13303-111">推迟加载与即时加载</span><span class="sxs-lookup"><span data-stu-id="13303-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
