---
title: 无法读取分隔字段，因为当 EscapeQuotes 设置为 True 时，双引号不是合法的分隔符
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: bc19fc7496b31eabca6dabedf212c89d6f5450d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61819270"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>无法读取分隔字段，因为当 EscapeQuotes 设置为 True 时，双引号不是合法的分隔符
`TextFieldParser` 无法从文件中读取，因为引号 (") 以分隔符形式提供，且 `EscapeQuotes` 设置为 `True`。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将 `EscapeQuotes` 设置为 `False`。  
  
## <a name="see-also"></a>请参阅

- [TextFieldParser.SetDelimiters 方法](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [TextFieldParser.Delimiters 属性](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [如何：读取逗号分隔的文本文件](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [TextFieldParser 对象](../../visual-basic/language-reference/objects/textfieldparser-object.md)
