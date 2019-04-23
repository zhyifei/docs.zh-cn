---
title: 错误的文件名或文件号
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322155"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="12931-102">错误的文件名或文件号</span><span class="sxs-lookup"><span data-stu-id="12931-102">Bad file name or number</span></span>
<span data-ttu-id="12931-103">尝试访问指定的文件时出错。</span><span class="sxs-lookup"><span data-stu-id="12931-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="12931-104">此错误的可能原因是：</span><span class="sxs-lookup"><span data-stu-id="12931-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="12931-105">语句引用中未指定文件的名称或数字开头的文件`FileOpen`中指定的语句或的`FileOpen`语句但随后被关闭。</span><span class="sxs-lookup"><span data-stu-id="12931-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="12931-106">语句引用的文件数量超出了文件编号的范围。</span><span class="sxs-lookup"><span data-stu-id="12931-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="12931-107">语句引用的文件名或不是有效的数字。</span><span class="sxs-lookup"><span data-stu-id="12931-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="12931-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="12931-108">To correct this error</span></span>  
  
1. <span data-ttu-id="12931-109">请确保文件名称中指定`FileOpen`语句。</span><span class="sxs-lookup"><span data-stu-id="12931-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="12931-110">请注意，如果您调用`FileClose`语句而不使用参数，您可能会无意中关闭所有打开的文件。</span><span class="sxs-lookup"><span data-stu-id="12931-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="12931-111">如果你的代码通过算法生成文件编号，请确保数字都有效。</span><span class="sxs-lookup"><span data-stu-id="12931-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="12931-112">检查以确保它们符合操作系统约定的文件名称。</span><span class="sxs-lookup"><span data-stu-id="12931-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12931-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="12931-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="12931-114">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="12931-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
