---
title: 错误的文件模式
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a>错误的文件模式
在对文件内容进行操作中使用的语句必须是适合于该文件已打开的模式。 可能的原因包括：  
  
-   A`FilePutObject`或`FileGetObject`语句指定的顺序的文件。  
  
-   A`Print`语句指定的文件之外打开访问模式的`Output`或`Append`。  
  
-   `Input`语句指定以外打开访问模式的文件`Input`  
  
-   试图写入只读文件。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保`FilePutObject`和`FileGetObject`仅指文件供`Random`或`Binary`访问。  
  
-   请确保`Print`指定为打开的文件`Output`或`Append`访问模式。 如果不是，使用不同的语句将数据放在文件中，或重新打开了适当的模式中的文件。  
  
-   请确保`Input`指定为打开的文件`Input`。 如果不是，请使用不同的语句将数据放在文件或重新打开了适当的模式中的文件。  
  
-   如果你正在编写到只读文件，更改文件的读/写状态，或不要尝试对其进行写入。  
  
-   使用 `My.Computer.FileSystem` 对象中的可用功能。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [疑难解答：读取和写入文本文件](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
