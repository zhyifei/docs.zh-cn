---
title: 如何：将相关的常量值组合在一起
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354030"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>如何：将相关的常量值组合在一起 (Visual Basic)
An enumeration is the best way to group related constants together. You create an enumeration with the `Enum` statement in the declarations section of a class or a module. For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>To group related constant values  
  
1. Write a declaration that includes a code access level, the `Enum` keyword, and a valid name. This example creates the `Private` enumeration, `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Define the constants in the enumeration. This example creates the `Public` enumeration `temperatureValues` and assigns its values.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
