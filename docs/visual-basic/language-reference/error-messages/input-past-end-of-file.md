---
title: 输入超出文件尾
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a>输入超出文件尾
任一`Input`语句正在读取或为空的文件中，一个在其中使用的所有数据时，或者你都使用`EOF`以二进制访问方式打开文件的函数。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用`EOF`函数前立即`Input`检测文件末尾的语句。  
  
2.  如果该文件打开进行二进制访问时，使用`Seek`和`Loc`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
