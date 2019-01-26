---
title: '&lt;type1&gt;&#39;&lt;typename&gt; &#39;必须实现&#39; &lt;methodname&gt; &#39;接口&#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642434"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39;必须实现&#39; &lt;methodname&gt; &#39;接口&#39; &lt;interfacename&gt;&#39;
类或结构声明实现一个接口，但不实现的接口定义的过程。 必须实现该接口的每个成员。  
  
 **错误 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明具有相同名称和签名，因为在接口中定义的过程。 请务必包括至少`End Function`或`End Sub`语句。  
  
2.  添加`Implements`子句的末尾`Function`或`Sub`语句。 例如：  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>请参阅
- [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)
- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
