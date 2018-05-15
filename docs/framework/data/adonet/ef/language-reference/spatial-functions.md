---
title: 空间函数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7b78cbf4dc53ba1bc4148fa0077615e43cc8f9f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="spatial-functions"></a><span data-ttu-id="fcc34-102">空间函数</span><span class="sxs-lookup"><span data-stu-id="fcc34-102">Spatial Functions</span></span>
<span data-ttu-id="fcc34-103">空间类型没有文本格式。</span><span class="sxs-lookup"><span data-stu-id="fcc34-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="fcc34-104">但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。</span><span class="sxs-lookup"><span data-stu-id="fcc34-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="fcc34-105">例如，以下函数调用会生成一个几何点：</span><span class="sxs-lookup"><span data-stu-id="fcc34-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="fcc34-106">[SpatialEdmFunctions 方法](http://msdn.microsoft.com/library/hh749531.aspx)页列出所有空间规范的实体框架方法。</span><span class="sxs-lookup"><span data-stu-id="fcc34-106">The [SpatialEdmFunctions Methods](http://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="fcc34-107">请单击相关方法以查看应向函数传递哪些参数。</span><span class="sxs-lookup"><span data-stu-id="fcc34-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
