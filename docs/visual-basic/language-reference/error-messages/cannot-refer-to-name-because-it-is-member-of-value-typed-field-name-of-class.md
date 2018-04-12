---
title: 不能引用 &#39;&lt;名称&gt;&#39; 因为它是值类型字段 &#39; 的成员&lt;名称&gt;&#39; 的类 &#39;&lt;类名&gt;&#39; 它具有 &#39;System.MarshalByRefObject &#39;为基类
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>不能引用 &#39;&lt;名称&gt;&#39; 因为它是值类型字段 &#39; 的成员&lt;名称&gt;&#39; 的类 &#39;&lt;类名&gt;&#39; 它具有 &#39;System.MarshalByRefObject &#39;为基类
`System.MarshalByRefObject`类使应用程序支持跨应用程序域边界的远程访问的对象。 类型必须继承自`MarshalByRejectObject`类时跨应用程序域边界使用的类型。 因为对象的成员不在其中创建它们的应用程序域之外使用，必须不会复制对象的状态。  
  
 **错误 ID:** BC30310  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查以确保所引用的成员是有效的引用。  
  
2.  显式限定的成员`Me`关键字。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.MarshalByRefObject>  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
