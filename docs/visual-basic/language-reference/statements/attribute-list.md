---
title: "特性列表 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a>特性列表 (Visual Basic)
指定要应用于声明的编程元素的属性。 用逗号分隔多个属性。 下面是一个属性的语法。  
  
## <a name="syntax"></a>语法  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>部件  
 `attributemodifier`  
 所需的应用的源代码文件开头的属性。 可以是[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)或[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)。  
  
 `attributename`  
 必需。 属性的名称。  
  
 `attributearguments`  
 可选。 此特性的位置自变量的列表。 用逗号分隔多个自变量。  
  
 `attributeinitializer`  
 可选。 此属性的变量或属性初始值设定项的列表。 用逗号分隔多个初始值设定项。  
  
## <a name="remarks"></a>备注  
 你可以将一个或多个特性应用于几乎任何编程元素 （类型、 过程、 属性和等）。 特性显示在程序集的元数据，并且它们可以帮助您批注代码或指定如何使用特定的编程元素。 你可以应用 Visual Basic 和.NET Framework 中，通过定义属性，你可以定义你自己的特性。  

 有关何时使用属性的详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。 属性名称的信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
## <a name="rules"></a>规则  
  
-   **放置。** 可以将特性应用于大多数已声明的编程元素。 若要应用一个或多个属性，你放置*特性块*元素声明的开头。 属性列表中的每个项指定你想要应用的属性、 修饰符和自变量将为此调用属性。  
  
-   **命令的尖括号。** 如果你提供的属性列表，你必须请将其括在尖括号中 ("`<`"和"`>`")。  
  
-   **声明的一部分。** 该属性必须是元素声明，而不是单独的语句的一部分。 你可以使用行继续序列 (" `_`") 来扩展到多个源代码行上的声明语句。  
  
-   **修饰符。** 特性修饰符 (`Assembly`或`Module`) 上应用到编程元素中的源代码文件开头的每个属性必需的。 应用于未在源文件的开头的元素的特性不允许出现特性修饰符。  
  
-   **自变量。** 属性的所有位置自变量必须位于任何变量或属性初始值设定项之前。  
  
## <a name="example"></a>示例  
 下面的示例应用<xref:System.Runtime.InteropServices.DllImportAttribute>属性设为的主干定义`Function`过程。  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>指示特性化的过程表示非托管动态链接库 (DLL) 中的入口点。 该属性提供位置自变量作为 DLL 的名称和作为变量初始值设定项的其他信息。  
  
## <a name="see-also"></a>另请参阅  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Module \<关键字>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
