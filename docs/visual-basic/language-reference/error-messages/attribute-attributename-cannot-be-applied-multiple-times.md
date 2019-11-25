---
title: 特性“<attributename>”不能应用多次
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968228"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>特性 "\<attributename >" 不能应用多次

特性只能应用一次。 `AttributeUsage` 特性确定特性是否可以应用多次。  
  
 **错误 ID：** BC30663  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 请确保属性仅应用一次。  
  
2. 如果使用的是你开发的自定义特性，请考虑将其 `AttributeUsage` 特性更改为允许使用多种特性，如下面的示例所示。  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.AttributeUsageAttribute>
- [创建自定义特性](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
