---
title: "值的类型 &#39; type1 &#39;不能转换为 &#39; type2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>值的类型 &#39; type1 &#39;不能转换为 &#39; type2 &#39;
类型 type1 的值无法转换到 type2。 你可以使用 Value 属性来获取的第一个元素的字符串值\<parentElement >。  
  
 已尝试将 XML 文本隐式强制转换为特定类型。 XML 文本不能隐式强制转换为指定类型。  
  
 **错误 ID:** BC31194  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。 使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Convert>  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
