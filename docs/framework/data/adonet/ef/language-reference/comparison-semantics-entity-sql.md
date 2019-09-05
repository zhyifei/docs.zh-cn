---
title: 比较语义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: da7b8f662d10376abd649e674701b43b7b740a6f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251183"
---
# <a name="comparison-semantics-entity-sql"></a>比较语义 (Entity SQL)
执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：  
  
## <a name="explicit-comparison"></a>显式比较  
 相等运算：  
  
- =  
  
- !=  
  
 排序运算：  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 判断是否可为 Null 的运算：  
  
- IS NULL  
  
- IS NOT NULL  
  
## <a name="explicit-distinction"></a>显式区别  
 相等区别：  
  
- DISTINCT  
  
- GROUP BY  
  
 排序区别：  
  
- ORDER BY  
  
## <a name="implicit-distinction"></a>隐式区别  
 集运算和谓词（相等）：  
  
- UNION  
  
- INTERSECT  
  
- EXCEPT  
  
- SET  
  
- OVERLAPS  
  
 项谓词（相等）：  
  
- IN  
  
## <a name="supported-combinations"></a>支持的组合  
 下表说明了每种类型的比较运算符的所有受支持的组合：  
  
|类型|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**为 NULL**<br /><br /> **不为 NULL**|  
|-|-|-|-|-|-|-|-|  
|实体类型|Ref<sup>1</sup>|所有属性<sup>2</sup>|所有属性<sup>2</sup>|所有属性<sup>2</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Ref<sup>1</sup>|  
|复杂类型|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|行|所有属性<sup>4</sup>|所有属性<sup>4</sup>|所有属性<sup>4</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|所有属性<sup>4</sup>|Throw<sup>3</sup>|  
|基元类型|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|特定于提供程序|  
|多集|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|引用|是<sup>5</sup>|是<sup>5</sup>|是<sup>5</sup>|是<sup>5</sup>|引发|引发|是<sup>5</sup>|  
|关联<br /><br /> type|Throw<sup>3</sup>|引发|引发|引发|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
  
 <sup>1</sup>给定实体类型实例的引用将被隐式比较，如下面的示例中所示：  
  
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
  
 <sup>2</sup>复杂类型的属性将在发送到存储区之前平展，因此它们可以比较（只要它们的所有属性都是可比较的）。 另请参阅<sup>4。</sup>  
  
 <sup>3</sup>实体框架运行时检测不受支持的情况，并引发有意义的异常，而不参与提供程序/存储。  
  
 <sup>4</sup>尝试比较所有属性。 如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。  
  
 <sup>5</sup>对引用的所有单个元素进行比较（这包括实体集名称和实体类型的所有键属性）。  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 概述](entity-sql-overview.md)
