---
title: 空间函数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: ad6b722e84aae40354e30434b107752d02352645
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559512"
---
# <a name="spatial-functions"></a><span data-ttu-id="9cf21-102">空间函数</span><span class="sxs-lookup"><span data-stu-id="9cf21-102">Spatial Functions</span></span>
<span data-ttu-id="9cf21-103">空间类型没有文本格式。</span><span class="sxs-lookup"><span data-stu-id="9cf21-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="9cf21-104">但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。</span><span class="sxs-lookup"><span data-stu-id="9cf21-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="9cf21-105">例如，以下函数调用会生成一个几何点：</span><span class="sxs-lookup"><span data-stu-id="9cf21-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="9cf21-106">[SpatialEdmFunctions 方法](https://msdn.microsoft.com/library/hh749531.aspx)页列出了所有空间规范实体框架方法。</span><span class="sxs-lookup"><span data-stu-id="9cf21-106">The [SpatialEdmFunctions Methods](https://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="9cf21-107">请单击相关方法以查看应向函数传递哪些参数。</span><span class="sxs-lookup"><span data-stu-id="9cf21-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
