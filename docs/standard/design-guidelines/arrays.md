---
title: 数组
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: d0332591be7659aafb5b3169f92c81d47d519dc2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127558"
---
# <a name="arrays"></a>数组
**✓ 务必**在公共 API 中首选使用集合而不是数组。 [集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供了有关如何在集合和数组之间进行选择的详细信息。  
  
 **X 切忌**使用只读数组字段。 该字段本身是只读的且无法更改，但可以更改数组中的元素。  
  
 **✓ 考虑**使用交错数组而不是多维数组。  
  
 交错数组是其元素也是数组的一种数组。 构成元素的数组可以具有不同的大小，与多维数组相比，可减少一些数据集（例如，稀疏矩阵）的浪费空间。 此外，CLR 优化了交错数组的索引操作，因此在某些情况下它们可能表现出更好的运行时性能。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- <xref:System.Array>  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
