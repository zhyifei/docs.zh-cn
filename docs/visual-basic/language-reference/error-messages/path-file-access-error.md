---
title: 路径-文件访问错误
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 3c364296997f571956caad995581102ed990549d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842559"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="9f769-102">路径/文件访问错误</span><span class="sxs-lookup"><span data-stu-id="9f769-102">Path/File access error</span></span>
<span data-ttu-id="9f769-103">在文件访问权限或磁盘访问操作中，操作系统无法获得的路径和文件名称之间的连接。</span><span class="sxs-lookup"><span data-stu-id="9f769-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f769-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9f769-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="9f769-105">请确保文件规范的格式正确。</span><span class="sxs-lookup"><span data-stu-id="9f769-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="9f769-106">文件名称可以包含的完全限定 （绝对） 或相对路径。</span><span class="sxs-lookup"><span data-stu-id="9f769-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="9f769-107">完全限定的路径启动驱动器名称 （如果该路径是另一个驱动器上），并列出从根到该文件的显式路径。</span><span class="sxs-lookup"><span data-stu-id="9f769-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="9f769-108">任何不是完全限定的路径是相对于当前驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="9f769-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="9f769-109">请确保未尝试保存的文件，将替换现有只读文件。</span><span class="sxs-lookup"><span data-stu-id="9f769-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="9f769-110">如果这种情况，更改目标文件的只读属性，或使用其他文件名保存文件。</span><span class="sxs-lookup"><span data-stu-id="9f769-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="9f769-111">请确保未尝试打开只读文件中顺序`Output`或`Append`模式。</span><span class="sxs-lookup"><span data-stu-id="9f769-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="9f769-112">这种情况，如果打开的文件中`Input`模式或更改文件的只读属性。</span><span class="sxs-lookup"><span data-stu-id="9f769-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="9f769-113">请确保未尝试更改数据库或文档中的 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="9f769-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f769-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f769-114">See also</span></span>

- [<span data-ttu-id="9f769-115">错误类型</span><span class="sxs-lookup"><span data-stu-id="9f769-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
