---
title: "比较语义 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1fd1c21fc4f156bfe7a5abf9f76bd341e2d0f10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="comparison-semantics-entity-sql"></a>比较语义 (Entity SQL)
执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：  
  
## <a name="explicit-comparison"></a>显式比较  
 相等运算：  
  
-   =  
  
-   !=  
  
 排序运算：  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 判断是否可为 Null 的运算：  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>显式区别  
 相等区别：  
  
-   DISTINCT  
  
-   GROUP BY  
  
 排序区别：  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>隐式区别  
 集运算和谓词（相等）：  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 项谓词（相等）：  
  
-   IN  
  
## <a name="supported-combinations"></a>支持的组合  
 下表说明了每种类型的比较运算符的所有受支持的组合：  
  
|**类型**|**=**<br /><br /> **!=**|**分组依据**<br /><br /> **非重复**|**UNION**<br /><br /> **相交**<br /><br /> **除非**<br /><br /> **设置**<br /><br /> **重叠**|**在**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**为 NULL**<br /><br /> **不为 NULL**|  
|-|-|-|-|-|-|-|-|  
|实体类型|Ref<sup>1</sup>|所有属性<sup>2</sup>|所有属性<sup>2</sup>|所有属性<sup>2</sup>|引发<sup>3</sup>|引发<sup>3</sup>|Ref<sup>1</sup>|  
|复杂类型|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|  
|行|所有属性<sup>4</sup>|所有属性<sup>4</sup>|所有属性<sup>4</sup>|引发<sup>3</sup>|引发<sup>3</sup>|所有属性<sup>4</sup>|引发<sup>3</sup>|  
|基元类型|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|  
|多集|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|  
|引用|是<sup>5</sup>|是<sup>5</sup>|是<sup>5</sup>|是<sup>5</sup>|引发|引发|是<sup>5</sup>|  
|关联<br /><br /> 类型|引发<sup>3</sup>|引发|引发|引发|引发<sup>3</sup>|引发<sup>3</sup>|引发<sup>3</sup>|  
  
 <sup>1</sup>隐式比较给定的实体类型实例的引用，如下面的示例中所示：  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 不能将实体实例与显式引用进行比较。 如果试图这么做，则会引发异常。 例如，以下查询将引发异常：  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>复杂类型的属性被转换为扁平发送到应用商店中，因此它们变得可比较 （只要其所有属性都是可比较的） 之前。 另请参阅<sup>4。</sup>  
  
 <sup>3</sup>实体框架运行时检测到不受支持的情况下，并在不牵扯提供程序/存储的情况下引发有意义的异常。  
  
 <sup>4</sup>尝试比较所有属性。 如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。  
  
 <sup>5</sup>所有单个元素的引用进行比较 （包括实体集名称和实体类型的所有键属性）。  
  
## <a name="see-also"></a>另请参阅  
 [Entity SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
