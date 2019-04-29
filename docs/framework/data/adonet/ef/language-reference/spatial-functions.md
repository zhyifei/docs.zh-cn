---
title: 空间函数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797691"
---
# <a name="spatial-functions"></a>空间函数
空间类型没有文本格式。 但是，您可以使用规范实体实体框架函数，这些函数可使用已知文本格式的字符串来调用。 例如，以下函数调用会生成一个几何点：  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>方法具有所有空间规范实体框架方法。 请单击相关方法以查看应向函数传递哪些参数。
