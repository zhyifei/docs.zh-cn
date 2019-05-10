---
title: 所有字段宽度（除了最后一个元素外）都必须大于零
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: c1537133300ac4de33d0d7ebc3ea0ad6768e8ec9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609151"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>所有字段宽度（除了最后一个元素外）都必须大于零
所有字段宽度（除了最后一个元素外）都必须大于零。 最后一个元素的字段宽度小于或等于零表示最后一个字段的长度是可变的。  
  
 操作已失败，因为最后一个元素以外的某个字段宽度被设置为等于或小于零。 可将小于或等于零的字段宽度用作最后一个元素以指示最后一个字段的长度可变，但不能将它用作任何其他元素。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 将字段宽度设置为正确的长度。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [如何：读取固定宽度的文本文件](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser 对象](../../visual-basic/language-reference/objects/textfieldparser-object.md)
