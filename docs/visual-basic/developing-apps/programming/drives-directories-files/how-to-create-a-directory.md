---
title: "如何：在 Visual Basic 中创建目录 | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 81afe64204fda468f452f86171b15080f9c3d948
ms.contentlocale: zh-cn
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a>如何：在 Visual Basic 中创建目录
使用 `My.Computer.FileSystem` 对象的 `CreateDirectory` 方法来创建目录。  
  
 如果该目录已存在，则不引发任何异常。  
  
### <a name="to-create-a-directory"></a>创建目录  
  
-   使用 `CreateDirectory` 方法，指定将在其中创建目录的位置的完整路径。 此示例在 `NewDirectory` 中创建目录 `C:\Documents and Settings\All Users\Documents`。  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
-   目录名称格式不正确。 例如，它包含非法字符或仅为空白 (<xref:System.ArgumentException>)。  
  
-   要创建的目录的父目录是只读的 (<xref:System.IO.IOException>)。  
  
-   目录名称为 `Nothing` (<xref:System.ArgumentNullException>)。  
  
-   目录名称太长 (<xref:System.IO.PathTooLongException>)。  
  
-   目录是一个冒号“:”(<xref:System.NotSupportedException>)。  
  
-   用户无权创建目录 (<xref:System.UnauthorizedAccessException>)。  
  
-   用户处于部分信任的情况，权限不足 (<xref:System.Security.SecurityException>)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [创建、删除和移动文件和目录](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
