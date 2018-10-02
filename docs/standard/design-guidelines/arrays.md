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
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399676"
---
# <a name="arrays"></a>数组
**✓ DO** 喜欢使用通过公共 Api 中的数组的集合。 [集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供有关如何集合和数组之间进行选择的详细信息。  
  
 **X DO NOT** 使用只读数组字段。 该字段本身是只读的无法更改，但可以更改数组中的元素。  
  
 **✓ CONSIDER** 使用交错的数组而不多维数组。  
  
 交错的数组是具有也存在数组的元素的数组。 构成元素的数组可以是不同的大小，以与多维数组相比某些集的数据 （例如，稀疏矩阵） 的不太浪费空间。 此外，CLR 优化交错数组的索引操作，因此它们可能会表现出更好的运行时性能在某些情况下。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- <xref:System.Array>  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
