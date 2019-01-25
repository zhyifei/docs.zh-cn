---
title: 类型的值&#39;type1&#39;不能转换为&#39;y p e 2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 657e0feb675e15b9ece00d40c3d1ebe932a29099
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568279"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>类型的值&#39;type1&#39;不能转换为&#39;y p e 2&#39;
类型 type1 的值无法转换为 type2。 可以使用 Value 属性来获取第一个元素的字符串值\<parentElement >。  
  
 已尝试将 XML 文本隐式强制转换为特定类型。 XML 文本不能隐式强制转换为指定类型。  
  
 **错误 ID:** BC31194  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。 使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Convert>
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
