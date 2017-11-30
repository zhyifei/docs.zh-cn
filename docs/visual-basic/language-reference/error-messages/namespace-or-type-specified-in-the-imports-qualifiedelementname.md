---
title: "Namespace 或导入 &#39; 中指定的类型&lt;qualifiedelementname&gt;&#39; 没有 &#39; 不包含任何公共成员，或无法找到"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords: BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace 或导入 &#39; 中指定的类型&lt;qualifiedelementname&gt;&#39; 没有 &#39; 不包含任何公共成员，或无法找到
Namespace 或类型中的导入的指定\<qualifiedelementname > 不包含任何公共成员，或无法找到。 请确保命名空间或类型定义，并且包含至少一个公共成员。 请确保该别名名称不包含其他别名。  
  
 `Imports`语句指定的包含的元素不能找到或未定义任何`Public`成员。  
  
 A*包含元素*可以是命名空间、 类、 结构、 模块、 接口或枚举。 包含的元素包含成员，例如变量、 过程或其他包含的元素。  
  
 导入的目的是允许你访问命名空间或类型成员的代码，而无需限定它们。 你的项目可能还需要添加对命名空间或类型的引用。 详细信息，请参阅"导入包含元素"中[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
 如果编译器找不到指定的包含元素，它无法解析使用它的引用。 如果它找到的元素，但该元素不公开任何`Public`成员，则任何引用都不会成功。 在任一情况下是没有意义，来导入元素。  
  
 请记住，如果你导入包含元素，并为其分配导入别名，则无法使用该导入别名来导入另一个元素。 下面的代码生成编译器错误。  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **错误 ID:** BC40056  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  验证包含的元素可从你的项目中访问。  
  
2.  验证包含的元素的规范不包括从另一个导入任何导入别名。  
  
3.  验证包含元素公开至少一个`Public`成员。  
  
## <a name="see-also"></a>另请参阅  
 [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
