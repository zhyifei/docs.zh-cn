---
title: "不支持的功能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b54bac0c9ce0b473ef8d86b039ef638b79af784f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-functionality"></a>不支持的功能
在 LINQ to SQL 中，无法通过转换现有的公共语言运行库 (CLR) 和 .NET Framework 构造公开以下 SQL 功能：  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     尽管通过直接转换，不支持 `LIKE`，但是 <xref:System.Data.Linq.SqlClient.SqlMethods> 类中仍存在相似的功能。 有关详细信息，请参阅<xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>。  
  
-   `DATEDIFF`  
  
     LINQ to SQL 具有对 `DATEDIFF` 的有限支持。 <xref:System.Data.Linq.SqlClient.SqlMethods> 类中存在相似的功能。  
  
-   `ROUND`  
  
     LINQ to SQL 具有对 `ROUND` 的有限支持。 有关详细信息，请参阅[System.Math 方法](system-math-methods.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据类型和函数](data-types-and-functions.md)
