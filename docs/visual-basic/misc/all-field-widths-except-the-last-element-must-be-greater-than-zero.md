---
title: "所有字段宽度（除了最后一个元素外）都必须大于零"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b348494c0a3103641d29998218b546de0d432e2a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>所有字段宽度（除了最后一个元素外）都必须大于零
所有字段宽度（除了最后一个元素外）都必须大于零。 最后一个元素的字段宽度小于或等于零表示最后一个字段的长度是可变的。  
  
 操作已失败，因为最后一个元素以外的某个字段宽度被设置为等于或小于零。 可将小于或等于零的字段宽度用作最后一个元素以指示最后一个字段的长度可变，但不能将它用作任何其他元素。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将字段宽度设置为正确的长度。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>  
 [如何：读取固定宽度的文本文件](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)  
 [TextFieldParser 对象](../../visual-basic/language-reference/objects/textfieldparser-object.md)
