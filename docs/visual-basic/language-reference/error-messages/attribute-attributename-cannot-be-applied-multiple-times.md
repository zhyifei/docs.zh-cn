---
title: 属性&#39; &lt;attributename&gt; &#39;不能应用多次
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: df97a4e391406661db98eb1c958c0e12e45b6c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>属性&#39; &lt;attributename&gt; &#39;不能应用多次
该属性只能应用一次。 `AttributeUsage`属性确定是否可以多次应用的特性。  
  
 **错误 ID:** BC30663  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保该属性只能应用一次。  
  
2.  如果你使用你开发的自定义特性，请考虑更改其`AttributeUsage`特性以允许多个特性用法，使用与下面的示例。  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.AttributeUsageAttribute>  
 [创建自定义特性](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
