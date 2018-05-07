---
title: '&#39;&lt;interfacename&gt;。&lt;membername&gt; &#39;已经实现的基类&#39; &lt;n a m e&gt;&#39;。 重新实现&lt;类型&gt;假定'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39;&lt;interfacename&gt;。&lt;membername&gt; &#39;已经实现的基类&#39; &lt;n a m e&gt;&#39;。 重新实现&lt;类型&gt;假定
属性、 过程或派生类中的事件使用`Implements`子句，用于指定已在基类中实现的接口成员。  
  
 派生类可以重新实现由其基类实现的接口成员。 这与重写基类实现不同。 有关详细信息，请参阅[实现](../../../visual-basic/language-reference/statements/implements-clause.md)。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42015  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果要重新实现接口成员，则无需执行任何操作。 在派生类中的代码可访问重新实现的成员，除非你使用`MyBase`关键字访问基类实现。  
  
-   如果不打算重新实现接口成员，请从属性、过程或事件声明中删除 `Implements` 子句。  
  
## <a name="see-also"></a>请参阅  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
