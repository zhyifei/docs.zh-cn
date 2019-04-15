---
title: 不再支持“Line”语句（Visual Basic 编译器错误）
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: c7a3e6bcd0db268a0e0acfc74c570e26f89cff6a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339068"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>不再支持“Line”语句（Visual Basic 编译器错误）
不再支持行语句。 文件 I/O 功能是可用作`Microsoft.VisualBasic.FileSystem.LineInput`图形功能，可作为`System.Drawing.Graphics.DrawLine`。  
  
 **错误 ID:** BC30830  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 如果执行文件访问，请使用`Microsoft.VisualBasic.FileSystem.LineInput`。  
  
2. 如果执行图形，则请使用 `System.Drawing.Graphics.Drawline`。  
  
## <a name="see-also"></a>请参阅

- <xref:System.IO>
- <xref:System.Drawing>
- [使用 Visual Basic 访问文件](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
