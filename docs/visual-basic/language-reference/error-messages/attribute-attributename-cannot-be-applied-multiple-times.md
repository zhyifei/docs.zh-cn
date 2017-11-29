---
title: "属性 &#39;&lt;attributename&gt;&#39; 不能应用多次"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords: BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 216cf54fd164ca95b6378517a679b5b54183559f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>属性 &#39;&lt;attributename&gt;&#39; 不能应用多次
该属性只能应用一次。 `AttributeUsage`属性确定是否可以多次应用的特性。  
  
 **错误 ID:** BC30663  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保该属性只能应用一次。  
  
2.  如果你使用你开发的自定义特性，请考虑更改其`AttributeUsage`特性以允许多个特性用法，使用与下面的示例。  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.AttributeUsageAttribute>  
 [创建自定义特性](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
