---
title: "类型&lt;typename&gt;不符合 CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords: BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d45da3b061dff0f82c1155daf5724033261bbdaa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a>类型&lt;typename&gt;不符合 CLS
变量、 属性或函数返回声明具有不符合 CLS 的数据类型。  
  
 应用程序，以符合[语言独立性和独立于语言的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，它必须只使用符合 cls 的类型。  
  
 以下 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 数据类型不符合 CLS：  
  
-   [SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **错误 ID:** BC40041  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果你的应用程序需要符合 cls 的将此元素的数据类型更改为最接近的符合 cls 的类型。 例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。 如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。  
  
-   如果你的应用程序并不需要符合 cls 的你不需要更改任何内容。 你应注意它是不符合，但是。  
  
## <a name="see-also"></a>另请参阅  
 [\<PAVE 通过 > 编写符合 Cls 的代码](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
