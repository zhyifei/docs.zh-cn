---
title: 按位规范函数
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 3c1f32acc7a035658198b807646c1ceb95dfed0b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251301"
---
# <a name="bitwise-canonical-functions"></a>按位规范函数
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 包含按位规范函数。  
  
## <a name="remarks"></a>备注  
 下表列出了 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 按位规范函数。 如果提供 `Null` 输入，则这些函数返回 `Null`。 这些函数的返回类型与参数类型相同。 如果函数采用多个自变量，则这些自变量必须具有相同的类型。 若要跨不同类型执行按位运算，需要显式强制转换为同一类型。  
  
|函数|描述|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位与结果。<br /><br /> **参数**<br /><br /> `Byte` 、`Int16`、和。`Int64` `Int32`<br /><br /> **示例**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|返回 `value` 的位求反结果。<br /><br /> **参数**<br /><br /> `Byte` 、`Int16`、和。`Int64` `Int32`<br /><br /> **示例**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位或结果。<br /><br /> **参数**<br /><br /> `Byte` 、`Int16`和。`Int64` `Int32`<br /><br /> **示例**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 位异或结果。<br /><br /> **参数**<br /><br /> `Byte` 、`Int16`和。`Int64` `Int32`<br /><br /> **示例**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>请参阅

- [规范函数](canonical-functions.md)
