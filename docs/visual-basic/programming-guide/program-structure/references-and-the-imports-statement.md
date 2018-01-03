---
title: "引用和 Imports 语句 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60c62eae57ae127fcbb860fe72853604802cccd9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="references-and-the-imports-statement-visual-basic"></a>引用和 Imports 语句 (Visual Basic)
你可以向外部对象提供你的项目通过选择**添加引用**命令**项目**菜单。 在引用[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]可以指向程序集，它们是与类似类型库但包含的详细信息。  
  
## <a name="the-imports-statement"></a>Imports 语句  
 程序集包含一个或多个命名空间。 当你将添加对程序集的引用时，你还可以添加`Imports`控制该程序集的模块中的命名空间的可见性的模块的语句。 `Imports`语句提供了的作用域的上下文中，你可以使用仅提供唯一的引用所需的命名空间的一部分。  
  
 `Imports`语句具有以下语法：  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`引用为短名称，你可以使用代码中引用的导入的命名空间。 `Namespace`是通过在项目中，定义或通过以前的项目引用的命名空间通过可用`Imports`语句。  
  
 模块可能包含任意数量的`Imports`语句。 它们必须出现在任何之后`Option`语句，如果存在，但在任何其他代码之前。  
  
> [!NOTE]
>  不要混淆项目引用与`Imports`语句或`Declare`语句。 项目引用使得外部对象，例如在程序集中中的对象可用于[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]项目。 `Imports`语句用于简化对项目引用的访问，但不提供对这些对象的访问。 `Declare`语句用于声明对外部过程中动态链接库 (DLL) 的引用。  
  
## <a name="using-aliases-with-the-imports-statement"></a>使用导入语句中使用别名  
 `Imports`语句，从而更便于访问的类的方法，无需显式类型引用的完全限定的名称。 别名，可以将更友好的名称分配给一个属于命名空间。 例如，回车符/换行符导致一段单独的文本显示在多个行上的序列是的一部分<xref:Microsoft.VisualBasic.ControlChars>中的模块<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。 若要在不带别名程序中使用此常量，你需要键入以下代码：  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`语句必须始终为紧接着的第一个行`Option`模块中的语句。 下面的代码段演示如何导入和分配的别名<xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>模块：  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 将来对此命名空间的引用可以是简短得多：  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 如果`Imports`语句不包括别名名称，而无需限定的模块可用于在导入的命名空间中定义的元素。 如果指定的别名名称，则它必须用作限定符包含在该命名空间的名称。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [如何：使用命令行创建和使用程序集](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
