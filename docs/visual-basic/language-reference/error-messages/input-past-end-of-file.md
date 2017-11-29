---
title: "输入超出文件尾"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="cb788-102">输入超出文件尾</span><span class="sxs-lookup"><span data-stu-id="cb788-102">Input past end of file</span></span>
<span data-ttu-id="cb788-103">任一`Input`语句正在读取或为空的文件中，一个在其中使用的所有数据时，或者你都使用`EOF`以二进制访问方式打开文件的函数。</span><span class="sxs-lookup"><span data-stu-id="cb788-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb788-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cb788-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="cb788-105">使用`EOF`函数前立即`Input`检测文件末尾的语句。</span><span class="sxs-lookup"><span data-stu-id="cb788-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="cb788-106">如果该文件打开进行二进制访问时，使用`Seek`和`Loc`。</span><span class="sxs-lookup"><span data-stu-id="cb788-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb788-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb788-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
