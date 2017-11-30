---
title: "&#39;&lt;表达式&gt;&#39; 不能用作类型约束"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords: BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 054c05747491afb02601df00225a703560cbe91c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a>&#39;&lt;表达式&gt;&#39; 不能用作类型约束
约束列表包含的表达式不表示对类型形参的有效约束。  
  
 约束列表对传递给类型形参的类型实参有一定要求。 你可以采用任意组合指定以下要求：  
  
-   该类型实参必须实现一个或多个接口  
  
-   该类型实参最多从一个类继承  
  
-   类型实参必须公开一个创建代码可以访问的无形参构造函数（包括 `New` 约束）  
  
 如果不在约束列表中包括任何特定类或接口，则可以通过指定以下内容之一来施加更常规的要求：  
  
-   类型参数必须是值类型（包括 `Structure` 约束）  
  
-   类型参数必须是引用类型（包括 `Class` 约束）  
  
 不能为同一类型参数同时指定 `Structure` 和 `Class` ，并且它们两个都只能指定一次。  
  
 **错误 ID:** BC32061  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   验证表达式及其元素是否拼写正确。  
  
-   如果表达式不符合前面列出的要求，请从约束列表中将其删除。  
  
-   如果表达式引用接口或类，请验证编译器是否有权访问该接口或类。 可能需要限定其名称，并可能需要添加一个项目引用。 有关详细信息，请参阅"项目引用"[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [值类型和引用类型](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
