---
title: 不能引用&#39;&lt;名称&gt;&#39;是值类型字段的成员，因此&#39;&lt;名称&gt;&#39;类的&#39; &lt;classname&gt; &#39;具有&#39;System.MarshalByRefObject&#39;作为基类
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739292"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>不能引用&#39;&lt;名称&gt;&#39;是值类型字段的成员，因此&#39;&lt;名称&gt;&#39;类的&#39; &lt;classname&gt; &#39;具有&#39;System.MarshalByRefObject&#39;作为基类
`System.MarshalByRefObject`类可让应用程序支持跨应用程序域边界对对象的远程访问。 类型必须继承自`MarshalByRejectObject`类时跨应用程序域边界使用的类型。 不得复制对象的状态，因为对象的成员不是可在其中创建应用程序域之外使用。  
  
 **错误 ID:** BC30310  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查以确保所引用的成员的引用有效。  
  
2.  显式限定的成员`Me`关键字。  
  
## <a name="see-also"></a>请参阅
- <xref:System.MarshalByRefObject>
- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
