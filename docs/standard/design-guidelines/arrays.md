---
title: 数组
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48024527"
---
# <a name="arrays"></a>数组
**✓ 务必** 在公共 API 中使用集合而不是数组。[集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供了有关如何在集合和数组之间进行选择的详细信息。
  
**X 切忌** 使用只读数组字段。该字段本身是只读的，无法更改，但可以更改数组中的元素。

**✓ 考虑** 使用交错数组而不是多维数组。

交错数组是一个数组，其元素也是数组。构成元素的数组可以具有不同的大小，与多维数组相比，导致一些数据集（例如，稀疏矩阵）的浪费空间更少。此外，CLR 优化了交错数组的索引操作，因此在某些情况下它们可能表现出更好的运行时性能。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- <xref:System.Array>  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
