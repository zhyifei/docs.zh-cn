---
title: "权限被拒绝 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5d7965ebd42cb3e56d66966d035be9ba3d3957c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="5ffa5-102">权限被拒绝 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ffa5-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="5ffa5-103">试图写入写保护的磁盘或访问锁定的文件。</span><span class="sxs-lookup"><span data-stu-id="5ffa5-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5ffa5-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5ffa5-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="5ffa5-105">若要打开写保护的文件，请更改文件的写保护属性。</span><span class="sxs-lookup"><span data-stu-id="5ffa5-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="5ffa5-106">请确定另一个进程没有已锁定该文件，然后等待直到另一个进程释放它打开的文件。</span><span class="sxs-lookup"><span data-stu-id="5ffa5-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="5ffa5-107">若要访问注册表，请检查您的用户权限，包括此类型的注册表访问。</span><span class="sxs-lookup"><span data-stu-id="5ffa5-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ffa5-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ffa5-108">See Also</span></span>  
 [<span data-ttu-id="5ffa5-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="5ffa5-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
