---
title: '&#39;&lt;typename&gt; &#39;不能继承自&lt;类型&gt; &#39; &lt;b t y p&gt; &#39;扩展的基本访问权限，因此&lt;类型&gt;程序集外部的'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556478"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;typename&gt; &#39;不能继承自&lt;类型&gt; &#39; &lt;b t y p&gt; &#39;扩展的基本访问权限，因此&lt;类型&gt;程序集外部的
类或接口继承自的基类或接口但具有限制性较弱的访问级别。  
  
 例如，`Public`接口继承自`Friend`接口，或`Protected`类继承自`Private`类。 这会公开的基类或接口来访问超出了预期的级别。  
  
 **错误 ID:** BC30910  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   更改派生的类或接口的基类或接口至少限制的访问级别。  
  
     或  
  
-   如果需要限制较少的访问级别，请删除`Inherits`语句。 不能从更受限制的基类或接口继承。  
  
## <a name="see-also"></a>请参阅
- [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
