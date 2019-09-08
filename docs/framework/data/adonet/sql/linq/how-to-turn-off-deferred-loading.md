---
title: 如何：禁用推迟加载
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781652"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="c7a27-102">如何：禁用推迟加载</span><span class="sxs-lookup"><span data-stu-id="c7a27-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="c7a27-103">可以通过将 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 设置为 `false` 来关闭延迟加载。</span><span class="sxs-lookup"><span data-stu-id="c7a27-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="c7a27-104">有关详细信息，请参阅[延迟与立即加载](deferred-versus-immediate-loading.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a27-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7a27-105">关闭对象跟踪时，也隐式地关闭了延迟加载。</span><span class="sxs-lookup"><span data-stu-id="c7a27-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="c7a27-106">有关详细信息，请参阅[如何：将信息检索为只读](how-to-retrieve-information-as-read-only.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a27-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a27-107">示例</span><span class="sxs-lookup"><span data-stu-id="c7a27-107">Example</span></span>  
 <span data-ttu-id="c7a27-108">下面的示例演示如何通过将 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 设置为 `false` 来关闭延迟加载。</span><span class="sxs-lookup"><span data-stu-id="c7a27-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c7a27-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7a27-109">See also</span></span>

- [<span data-ttu-id="c7a27-110">查询概念</span><span class="sxs-lookup"><span data-stu-id="c7a27-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="c7a27-111">查询数据库</span><span class="sxs-lookup"><span data-stu-id="c7a27-111">Querying the Database</span></span>](querying-the-database.md)
