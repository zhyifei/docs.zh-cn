---
title: 类型的值&#39;type1&#39;不能转换为&#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>类型的值&#39;type1&#39;不能转换为&#39;type2&#39;
类型 type1 的值无法转换到 type2。 你可以使用 Value 属性来获取的第一个元素的字符串值\<parentElement >。  
  
 已尝试将 XML 文本隐式强制转换为特定类型。 XML 文本不能隐式强制转换为指定类型。  
  
 **错误 ID:** BC31194  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。 使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Convert>  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
