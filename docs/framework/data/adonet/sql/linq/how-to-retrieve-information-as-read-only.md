---
title: 如何：将信息作为只读信息检索
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 131562e9ee0fbfde8c94f580bcb6d452918f42ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148975"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="689dc-102">如何：将信息作为只读信息检索</span><span class="sxs-lookup"><span data-stu-id="689dc-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="689dc-103">当您不打算更改数据时，您可以通过设法产生只读结果来提高查询性能。</span><span class="sxs-lookup"><span data-stu-id="689dc-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="689dc-104">通过将 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 可实现只读处理。</span><span class="sxs-lookup"><span data-stu-id="689dc-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="689dc-105">当 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 时，<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 将隐式设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="689dc-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="689dc-106">示例</span><span class="sxs-lookup"><span data-stu-id="689dc-106">Example</span></span>  
 <span data-ttu-id="689dc-107">下面的代码检索雇员雇佣日期的只读集合。</span><span class="sxs-lookup"><span data-stu-id="689dc-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="689dc-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="689dc-108">See also</span></span>

- [<span data-ttu-id="689dc-109">查询概念</span><span class="sxs-lookup"><span data-stu-id="689dc-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="689dc-110">查询数据库</span><span class="sxs-lookup"><span data-stu-id="689dc-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="689dc-111">推迟加载与即时加载</span><span class="sxs-lookup"><span data-stu-id="689dc-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
