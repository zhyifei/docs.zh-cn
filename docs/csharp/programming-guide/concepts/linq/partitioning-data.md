---
title: "数据分区 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32b95887e05767513dd818743dd1726149503b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-c"></a>数据分区 (C#)
LINQ 中的分区是指将输入序列划分为两个部分的操作，无需重新排列元素，然后返回其中一个部分。  
  
 下图显示对字符序列进行三种不同的分区操作的结果。 第一个操作返回序列中的前三个元素。 第二个操作跳过前三个元素，返回剩余元素。 第三个操作跳过序列中的前两个元素，返回接下来的三个元素。  
  
 ![LINQ 分区操作](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 下面一节列出了对序列进行分区的标准查询运算符方法。  
  
## <a name="operators"></a>运算符  
  
|运算符名称|描述|C# 查询表达式语法|详细信息|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|跳过序列中指定位置之前的元素。|不适用。|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|基于谓词函数跳过元素，直到元素不符合条件。|不适用。|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|获取序列中指定位置之前的元素。|不适用。|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|基于谓词函数获取元素，直到元素不符合条件。|不适用。|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq>  
 [标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
