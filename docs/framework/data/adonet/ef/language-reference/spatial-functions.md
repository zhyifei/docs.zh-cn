---
title: 空间函数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319302"
---
# <a name="spatial-functions"></a><span data-ttu-id="6c2e9-102">空间函数</span><span class="sxs-lookup"><span data-stu-id="6c2e9-102">Spatial Functions</span></span>
<span data-ttu-id="6c2e9-103">空间类型没有文本格式。</span><span class="sxs-lookup"><span data-stu-id="6c2e9-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="6c2e9-104">但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。</span><span class="sxs-lookup"><span data-stu-id="6c2e9-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="6c2e9-105">例如，以下函数调用会生成一个几何点：</span><span class="sxs-lookup"><span data-stu-id="6c2e9-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="6c2e9-106">@No__t_0 方法具有所有空间规范实体框架方法。</span><span class="sxs-lookup"><span data-stu-id="6c2e9-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="6c2e9-107">请单击相关方法以查看应向函数传递哪些参数。</span><span class="sxs-lookup"><span data-stu-id="6c2e9-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
