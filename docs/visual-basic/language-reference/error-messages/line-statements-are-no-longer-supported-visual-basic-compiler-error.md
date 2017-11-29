---
title: "&#39;行 &#39;语句将不再支持 （Visual Basic 编译器错误）"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords: BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d2db5dc786749360dfcf6789f12b5659d5713fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;行 &#39;语句将不再支持 （Visual Basic 编译器错误）
不再支持行语句。 文件 I/O 功能是可用作`Microsoft.VisualBasic.FileSystem.LineInput`，图形功能可用作`System.Drawing.Graphics.DrawLine`。  
  
 **错误 ID:** BC30830  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  如果执行文件访问，请使用`Microsoft.VisualBasic.FileSystem.LineInput`。  
  
2.  如果执行图形，请使用`System.Drawing.Graphics.Drawline`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [使用 Visual Basic 访问文件](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
