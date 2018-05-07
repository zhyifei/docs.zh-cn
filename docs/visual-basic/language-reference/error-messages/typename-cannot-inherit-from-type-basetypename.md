---
title: '&#39;&lt;typename&gt; &#39;不能继承自&lt;类型&gt; &#39;&lt;基类型名称&gt;&#39;扩展基访问权限，因此&lt;类型&gt;程序集外部'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: f747b2b24f5fecc22b9e1fbc6ba26b634e9ead2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;typename&gt; &#39;不能继承自&lt;类型&gt; &#39;&lt;基类型名称&gt;&#39;扩展基访问权限，因此&lt;类型&gt;程序集外部
类或接口继承自的基类或接口，但是具有限制性较弱的访问级别。  
  
 例如，`Public`接口继承自`Friend`接口，或`Protected`类继承自`Private`类。 这会公开基类或接口来访问不在预期级别。  
  
 **错误 ID:** BC30910  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   更改派生的类或接口让至少作为基类或接口的限制性最高的访问级别。  
  
     -或-  
  
-   如果你需要的限制性较弱的访问级别，删除`Inherits`语句。 不能从更受限制的基类或接口继承。  
  
## <a name="see-also"></a>请参阅  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
