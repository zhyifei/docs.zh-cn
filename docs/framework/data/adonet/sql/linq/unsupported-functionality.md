---
title: 不支持的功能
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: c4ed52a43fe9cf04c8015aad9247e9f2eb2481e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364485"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="9cbb9-102">不支持的功能</span><span class="sxs-lookup"><span data-stu-id="9cbb9-102">Unsupported Functionality</span></span>
<span data-ttu-id="9cbb9-103">在 LINQ to SQL 中，无法通过转换现有的公共语言运行库 (CLR) 和 .NET Framework 构造公开以下 SQL 功能：</span><span class="sxs-lookup"><span data-stu-id="9cbb9-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="9cbb9-104">尽管通过直接转换，不支持 `LIKE`，但是 <xref:System.Data.Linq.SqlClient.SqlMethods> 类中仍存在相似的功能。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="9cbb9-105">有关详细信息，请参阅<xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="9cbb9-106">LINQ to SQL 具有对 `DATEDIFF` 的有限支持。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="9cbb9-107"><xref:System.Data.Linq.SqlClient.SqlMethods> 类中存在相似的功能。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="9cbb9-108">LINQ to SQL 具有对 `ROUND` 的有限支持。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="9cbb9-109">有关详细信息，请参阅[System.Math 方法](system-math-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbb9-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbb9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cbb9-110">See Also</span></span>  
 [<span data-ttu-id="9cbb9-111">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="9cbb9-111">Data Types and Functions</span></span>](data-types-and-functions.md)
