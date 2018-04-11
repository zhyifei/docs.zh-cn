---
title: 错误的文件名或文件号
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="91f82-102">错误的文件名或文件号</span><span class="sxs-lookup"><span data-stu-id="91f82-102">Bad file name or number</span></span>
<span data-ttu-id="91f82-103">尝试访问指定的文件时出错。</span><span class="sxs-lookup"><span data-stu-id="91f82-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="91f82-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="91f82-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="91f82-105">语句引用中未指定文件名称或数字的文件`FileOpen`中指定的语句或，`FileOpen`语句但随后被关闭。</span><span class="sxs-lookup"><span data-stu-id="91f82-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="91f82-106">语句引用的文件与大量超出文件数字的范围。</span><span class="sxs-lookup"><span data-stu-id="91f82-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="91f82-107">语句引用的文件名称或不是有效的数字。</span><span class="sxs-lookup"><span data-stu-id="91f82-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91f82-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="91f82-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="91f82-109">请确保文件名称中指定`FileOpen`语句。</span><span class="sxs-lookup"><span data-stu-id="91f82-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="91f82-110">请注意，如果你在调用`FileClose`语句无需自变量，你可能会意外地关闭所有打开的文件。</span><span class="sxs-lookup"><span data-stu-id="91f82-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="91f82-111">如果你的代码生成的文件数字算法，请确保两个数字是有效。</span><span class="sxs-lookup"><span data-stu-id="91f82-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="91f82-112">请检查以确保它们符合操作系统约定的文件名称。</span><span class="sxs-lookup"><span data-stu-id="91f82-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f82-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91f82-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="91f82-114">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="91f82-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
