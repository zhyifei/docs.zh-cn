---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
标识为其类、 结构或接口的默认属性的属性。  
  
## <a name="remarks"></a>备注  
 类、 结构或接口可以指定最多为其属性之一*默认属性*，前提是属性采用至少一个参数。 如果代码使得对类或结构的引用，而不必指定的成员，Visual Basic 将解析的默认属性该引用。  
  
 默认属性可能会导致小减少源代码的字符，但它们会导致代码更难阅读。 如果在发出对类或结构名称的引用时，调用代码不熟悉类或结构，它无法确定该引用访问的类或结构本身或默认属性。 这可能导致编译器错误或细微的运行时逻辑错误。  
  
 你可以始终使用某种程度上减少默认属性的几率[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)设置编译器类型检查到`On`。  
  
 如果你计划可以使用预定义的类或结构中你的代码，必须确定它是否具有默认属性，以及如果是这样，其名称是什么。  
  
 由于这些缺点，应考虑未定义默认属性。 为了代码的可读性，你应还考虑始终显式引用所有属性，包括默认属性。  
  
 `Default`修饰符可用于在此上下文中：  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [如何： 声明和 Visual Basic 中调用默认属性](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
