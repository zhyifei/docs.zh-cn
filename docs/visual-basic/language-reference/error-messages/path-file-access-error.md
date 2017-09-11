---
title: "路径文件访问错误 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6307c0d0115e3791d5ad6bf4243057e6ed90d9cd
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="pathfile-access-error"></a><span data-ttu-id="1db3a-102">路径/文件访问错误</span><span class="sxs-lookup"><span data-stu-id="1db3a-102">Path/File access error</span></span>
<span data-ttu-id="1db3a-103">文件访问权限或磁盘访问操作期间，操作系统无法获得的路径和文件名之间的连接。</span><span class="sxs-lookup"><span data-stu-id="1db3a-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1db3a-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1db3a-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="1db3a-105">请确保已正确地格式化文件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1db3a-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="1db3a-106">文件名可以包含是完全限定的 （绝对） 路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="1db3a-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="1db3a-107">完全限定的路径开头的驱动器名称 （如果此路径为另一个驱动器上），并列出从根到该文件的显式路径。</span><span class="sxs-lookup"><span data-stu-id="1db3a-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="1db3a-108">任何不是完全限定的路径是相对于当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="1db3a-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="1db3a-109">请确保未尝试保存文件将替换现有只读文件。</span><span class="sxs-lookup"><span data-stu-id="1db3a-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="1db3a-110">如果出现这种情况，更改了目标文件的只读属性，或用其他文件名保存文件。</span><span class="sxs-lookup"><span data-stu-id="1db3a-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="1db3a-111">请确保您未尝试打开只读文件中顺序`Output`或`Append`模式。</span><span class="sxs-lookup"><span data-stu-id="1db3a-111">Make sure you did not attempt to open a read-only file in sequential`Output`or `Append` mode.</span></span> <span data-ttu-id="1db3a-112">如果出现这种情况，打开的文件中`Input`模式或更改文件的只读属性。</span><span class="sxs-lookup"><span data-stu-id="1db3a-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="1db3a-113">请确保不尝试更改[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据库或文档中的项目。</span><span class="sxs-lookup"><span data-stu-id="1db3a-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db3a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1db3a-114">See Also</span></span>  
 [<span data-ttu-id="1db3a-115">错误类型</span><span class="sxs-lookup"><span data-stu-id="1db3a-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
