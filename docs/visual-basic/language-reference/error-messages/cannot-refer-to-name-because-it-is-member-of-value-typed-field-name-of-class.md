---
title: 不能引用&#39;&lt;名称&gt;&#39;因为它是值类型字段成员的&#39;&lt;名称&gt;&#39;类的&#39; &lt;classname&gt; &#39;具有&#39;System.MarshalByRefObject&#39;用作基类
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: f44d33c9d51148e6bbcfbf5db4dbc115101df1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586342"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>不能引用&#39;&lt;名称&gt;&#39;因为它是值类型字段成员的&#39;&lt;名称&gt;&#39;类的&#39; &lt;classname&gt; &#39;具有&#39;System.MarshalByRefObject&#39;用作基类
`System.MarshalByRefObject`类使应用程序支持跨应用程序域边界的远程访问的对象。 类型必须继承自`MarshalByRejectObject`类时跨应用程序域边界使用的类型。 因为对象的成员不在其中创建它们的应用程序域之外使用，必须不会复制对象的状态。  
  
 **错误 ID:** BC30310  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查以确保所引用的成员是有效的引用。  
  
2.  显式限定的成员`Me`关键字。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.MarshalByRefObject>  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
