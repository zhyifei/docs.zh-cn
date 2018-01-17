---
title: "运算符优先级 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bc8ebd235016a22792d98e1a966e8c1217e2823e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="operator-precedence-entity-sql"></a>运算符优先级 (Entity SQL)
当[!INCLUDE[esql](../../../../../../includes/esql-md.md)]查询有多个运算符，运算符优先级确定执行的操作序列。 执行顺序可能对查询结果有明显的影响。  
  
 运算符的优先级别如下表中所示。 在较低级别的运算符之前先对较高级别的运算符进行求值。  
  
|级别|运算类型|运算符|  
|-----------|--------------------|--------------|  
|1|基本|`. , [] ()`|  
|2|一元|`! not`|  
|3|乘法|`* / %`|  
|4|加法|`+ -`|  
|5|订购|`< > <= >=`|  
|6|相等|`= != <>`|  
|7|条件“与”|`and &&`|  
|8|条件“或”|`or &#124;&#124;`|  
  
 当一个表达式中的两个运算符有相同的运算符优先级别时，将按照它们在查询中的位置对其从左到右进行求值。 例如，`x+y-z` 将计算为 `(x+y)-z`。  
  
 在查询中可以使用括号替代所定义的运算符的优先级。 首先对括号中的内容进行求值，从而产生一个结果，然后括号外的运算符才可以使用这个结果。 例如，`x+y*z`乘以`y`通过`z`，然后添加`x`，但`(x+y)*z`添加`x`到`y`然后相乘的结果和`z`。  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
