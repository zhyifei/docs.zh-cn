---
title: Inherits Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae9ba54c3fd1ec3332c9f6260bc19a1293270ad8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inherits-statement"></a>Inherits Statement
使当前类或接口继承自另一个类或接口组的属性、 变量、 属性、 过程和事件。  
  
## <a name="syntax"></a>语法  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`basetypenames`|必需。 此类派生自的类名称。<br /><br /> - 或 -<br /><br /> 此接口派生的接口名称。 使用逗号分隔多个名称。|  
  
## <a name="remarks"></a>备注  
 如果使用，`Inherits`语句必须是类或接口定义中的第一个非空、 非注释行。 它应立即遵循`Class`或`Interface`语句。  
  
 你可以使用`Inherits`只能在类或接口中。 这意味着继承的声明上下文不能是源文件、 命名空间、 结构、 模块、 过程或块。  
  
## <a name="rules"></a>规则  
  
-   **类继承。** 如果一个类使用`Inherits`语句中，你可以指定只有一个基类。  
  
     类不能从嵌套在它里面的类继承。  
  
-   **接口继承。** 如果接口使用`Inherits`语句，则可以指定一个或多个基接口。 你可以即使它们各自定义具有相同名称的成员，从两个接口继承。 如果这样做，实现代码必须使用名称限定指定它正在实现的成员。  
  
     一个接口不能从具有限制性更强的访问级别的另一个接口继承。 例如，`Public`接口不能继承自`Friend`接口。  
  
     接口不能从嵌套在它里面的接口继承。  
  
 .NET Framework 中的类继承的一个示例是<xref:System.ArgumentException>类，该类继承自<xref:System.SystemException>类。 这提供对<xref:System.ArgumentException>所有预定义的属性和过程需要由系统异常，如<xref:System.Exception.Message%2A>属性和<xref:System.Exception.ToString%2A>方法。  
  
 .NET Framework 中的接口继承的一个示例是<xref:System.Collections.ICollection>接口，该类继承自<xref:System.Collections.IEnumerable>接口。 这将导致<xref:System.Collections.ICollection>继承需遍历集合的枚举数的定义。  
  
## <a name="example"></a>示例  
 下面的示例使用`Inherits`语句以显示类的名为`thisClass`可继承的名为的基类的所有成员`anotherClass`。  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示多个接口的继承。  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 名为的接口`thisInterface`现在包括中的所有定义<xref:System.IComparable>， <xref:System.IDisposable>，和<xref:System.IFormattable>接口继承的成员分别提供有关特定类型的比较两个对象，释放分配的资源表示作为对象的值和`String`。 一个类以实现`thisInterface`必须实现每个基接口的每个成员。  
  
## <a name="see-also"></a>另请参阅  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
