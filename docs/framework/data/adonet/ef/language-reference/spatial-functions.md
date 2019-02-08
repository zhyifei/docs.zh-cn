---
title: 空间函数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904476"
---
# <a name="spatial-functions"></a><span data-ttu-id="ee921-102">空间函数</span><span class="sxs-lookup"><span data-stu-id="ee921-102">Spatial Functions</span></span>
<span data-ttu-id="ee921-103">空间类型没有文本格式。</span><span class="sxs-lookup"><span data-stu-id="ee921-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="ee921-104">但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。</span><span class="sxs-lookup"><span data-stu-id="ee921-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="ee921-105">例如，以下函数调用会生成一个几何点：</span><span class="sxs-lookup"><span data-stu-id="ee921-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="ee921-106"><xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>方法具有所有空间规范实体框架方法。</span><span class="sxs-lookup"><span data-stu-id="ee921-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="ee921-107">请单击相关方法以查看应向函数传递哪些参数。</span><span class="sxs-lookup"><span data-stu-id="ee921-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
