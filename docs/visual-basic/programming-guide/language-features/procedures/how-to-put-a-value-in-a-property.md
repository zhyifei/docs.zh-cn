---
title: "如何：在属性中放置值 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44e7c4a92ea3d087c12e74aa2ede33a52c8730cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>如何：在属性中放置值 (Visual Basic)
通过将属性名称放在赋值语句的左侧，可以在属性中存储值。  
  
 该属性的`Set`过程存储一个值，但并不按名称显式调用它。 就像你将使用变量，你可以使用该属性。 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]调用属性的过程。  
  
### <a name="to-store-a-value-in-a-property"></a>若要将值存储在属性  
  
1.  在赋值语句的左侧使用的属性名称。  
  
     下面的示例设置的值[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]`TimeOfDay`属性为中午，隐式调用其`Set`过程。  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  如果该属性接受参数，请按照用括号将自变量列表括起来的属性名称。 如果不有任何自变量，你可以选择省略括号。  
  
3.  将自变量放在括号里，用逗号分隔参数列表中。 请确保你提供属性定义的相应参数的相同顺序的自变量。  
  
4.  赋值语句右侧生成的值存储在属性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [属性过程](./property-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md)  
 [如何：创建属性](./how-to-create-a-property.md)  
 [如何：声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)  
 [如何： 声明和 Visual Basic 中调用默认属性](./how-to-declare-and-call-a-default-property.md)  
 [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
