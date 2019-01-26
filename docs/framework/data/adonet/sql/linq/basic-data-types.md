---
title: 基本数据类型
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: d9c79ae70d860c5e86d4338038b3158ebfba184f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704964"
---
# <a name="basic-data-types"></a>基本数据类型
因为 LINQ to SQL 查询转换为 Transact-SQL 后才在 Microsoft SQL Server 上执行。 LINQ to SQL 支持针对基本数据类型的许多和 SQL Server 一样的内置功能。  
  
## <a name="casting"></a>强制转换  
 支持从源 CLR 类型到目标 CLR 类型的隐式或显式强制转换，前提是在 SQL Server 中存在类似的有效转换。 有关 CLR 强制转换的详细信息，请参阅[CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic 中) 和[作为](~/docs/csharp/language-reference/keywords/as.md)。 转换后，强制转换会更改对 CLR 表达式执行的操作的行为，使之与自然映射到目标类型的其他 CLR 表达式的行为匹配。 强制转换还可以在继承映射的上下文中进行。 可以将对象强制转换成更具体的实体子类型，以便可以访问其特定于子类型的数据。  
  
## <a name="equality-operators"></a>相等运算符  
 LINQ to SQL 支持以下 LINQ to SQL 查询内部的基本数据类型上的相等运算符：  
  
-   相等和不相等运算符：支持对数值 <xref:System.Boolean>、<xref:System.DateTime> 和 <xref:System.TimeSpan> 类型的相等和不相等运算符。 有关 Visual Basic 运算符的详细`=`并`<>`，请参阅[比较运算符](~/docs/visual-basic/language-reference/operators/comparison-operators.md)。 有关详细信息C#比较运算符`==`并`!=`，请参阅[= = 运算符](~/docs/csharp/language-reference/operators/equality-comparison-operator.md)并[！ = 运算符](~/docs/csharp/language-reference/operators/not-equal-operator.md)分别  
  
-   Is 运算符：在使用继承映射时，`IS`运算符具有受支持的转换形式。 可以使用该运算符，而不用通过直接测试鉴别器列来确定对象是否属于特定实体类型，该运算符会转换为对鉴别器列的检查。 详细了解 Visual Basic 和C#Is 运算符，请参阅[Is 运算符](~/docs/visual-basic/language-reference/operators/is-operator.md)并[是](~/docs/csharp/language-reference/keywords/is.md)。  
  
## <a name="see-also"></a>请参阅
- [SQL-CLR 类型映射](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [数据类型和函数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
