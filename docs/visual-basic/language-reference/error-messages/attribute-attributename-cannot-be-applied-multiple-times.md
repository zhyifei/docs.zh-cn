---
title: 属性&#39; &lt;attributename&gt; &#39;不能应用多次
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565158"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>属性&#39; &lt;attributename&gt; &#39;不能应用多次
该特性仅应用一次。 `AttributeUsage`属性确定是否可以多次应用属性。  
  
 **错误 ID:** BC30663  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保该属性只应用一次。  
  
2.  如果使用的您开发的自定义特性，请考虑更改其`AttributeUsage`属性以允许多个特性用法，与下面的示例一样。  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>请参阅
- <xref:System.AttributeUsageAttribute>
- [创建自定义特性](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
