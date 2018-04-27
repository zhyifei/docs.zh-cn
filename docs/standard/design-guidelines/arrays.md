---
title: 数组
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54f5d68a343f473c67484e9e806551eb115bac36
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="arrays"></a>数组
**✓ 执行**喜欢使用通过公共 Api 中的数组的集合。 [集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供有关如何选择之间集合和数组的详细信息。  
  
 **X 不**使用只读数组字段。 字段自身是只读的和不能更改，但可以更改数组中的元素。  
  
 **请考虑 ✓**使用交错的数组而不多维数组。  
  
 交错的数组是包含也是数组的元素的数组。 构成元素的数组可以是不同的大小，以减少浪费空间某些集的数据 （例如，稀疏矩阵） 相比多维数组。 此外，CLR 优化对交错数组的索引操作，以便它们可能会在某些情况下更好的运行时性能表现出。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Array>  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
