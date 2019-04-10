---
title: 如何：筛选相关数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218220"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="f9b73-102">如何：筛选相关数据</span><span class="sxs-lookup"><span data-stu-id="f9b73-102">How to: Filter Related Data</span></span>
<span data-ttu-id="f9b73-103">使用 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 方法可指定用来限制检索到的数据量的子查询。</span><span class="sxs-lookup"><span data-stu-id="f9b73-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9b73-104">示例</span><span class="sxs-lookup"><span data-stu-id="f9b73-104">Example</span></span>  
 <span data-ttu-id="f9b73-105">在下面的示例中，<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 方法将检索到的 `Orders` 限制为今天尚未发货的那些订单。</span><span class="sxs-lookup"><span data-stu-id="f9b73-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="f9b73-106">如果不使用这种方式，则即使只需要一部分订单，也会检索到所有 `Orders`。</span><span class="sxs-lookup"><span data-stu-id="f9b73-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f9b73-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9b73-107">See also</span></span>

- [<span data-ttu-id="f9b73-108">查询数据库</span><span class="sxs-lookup"><span data-stu-id="f9b73-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
