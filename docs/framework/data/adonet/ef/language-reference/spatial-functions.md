---
title: "空间函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c482c2f79c6416a4e748599c896280b426d31ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="spatial-functions"></a><span data-ttu-id="13561-102">空间函数</span><span class="sxs-lookup"><span data-stu-id="13561-102">Spatial Functions</span></span>
<span data-ttu-id="13561-103">空间类型没有文本格式。</span><span class="sxs-lookup"><span data-stu-id="13561-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="13561-104">但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。</span><span class="sxs-lookup"><span data-stu-id="13561-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="13561-105">例如，以下函数调用会生成一个几何点：</span><span class="sxs-lookup"><span data-stu-id="13561-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="13561-106">[SpatialEdmFunctions 方法](http://msdn.microsoft.com/library/hh749531.aspx)页列出所有空间规范的实体框架方法。</span><span class="sxs-lookup"><span data-stu-id="13561-106">The [SpatialEdmFunctions Methods](http://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="13561-107">请单击相关方法以查看应向函数传递哪些参数。</span><span class="sxs-lookup"><span data-stu-id="13561-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
