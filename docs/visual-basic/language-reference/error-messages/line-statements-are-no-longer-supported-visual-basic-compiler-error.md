---
title: '&#39;行&#39;语句将不再支持 （Visual Basic 编译器错误）'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 36226cc371ffb8a51cb8d0f918952f1c717aea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702962"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;行&#39;语句将不再支持 （Visual Basic 编译器错误）
不再支持行语句。 文件 I/O 功能是可用作`Microsoft.VisualBasic.FileSystem.LineInput`图形功能，可作为`System.Drawing.Graphics.DrawLine`。  
  
 **错误 ID:** BC30830  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  如果执行文件访问，请使用`Microsoft.VisualBasic.FileSystem.LineInput`。  
  
2.  如果执行图形，则请使用 `System.Drawing.Graphics.Drawline`。  
  
## <a name="see-also"></a>请参阅
- <xref:System.IO>
- <xref:System.Drawing>
- [使用 Visual Basic 访问文件](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
