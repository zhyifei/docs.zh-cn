---
title: "路径文件访问错误"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a><span data-ttu-id="823a2-102">路径/文件访问错误</span><span class="sxs-lookup"><span data-stu-id="823a2-102">Path/File access error</span></span>
<span data-ttu-id="823a2-103">在文件访问或磁盘访问操作中，操作系统无法获得路径和文件名称之间的连接。</span><span class="sxs-lookup"><span data-stu-id="823a2-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="823a2-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="823a2-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="823a2-105">请确保文件规范的格式正确。</span><span class="sxs-lookup"><span data-stu-id="823a2-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="823a2-106">文件名称可以包含是完全限定 （绝对） 路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="823a2-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="823a2-107">完全限定的路径 （如果路径为另一个驱动器上） 开头的驱动器名称并列出文件的根的显式路径。</span><span class="sxs-lookup"><span data-stu-id="823a2-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="823a2-108">任何不是完全限定的路径是相对于当前的驱动器和目录。</span><span class="sxs-lookup"><span data-stu-id="823a2-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="823a2-109">请确保没有尝试保存将替换现有只读文件的文件。</span><span class="sxs-lookup"><span data-stu-id="823a2-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="823a2-110">如果出现这种情况，更改了目标文件的只读属性，或使用不同的文件名保存文件。</span><span class="sxs-lookup"><span data-stu-id="823a2-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="823a2-111">请确保你没有尝试打开只读文件中顺序`Output`或`Append`模式。</span><span class="sxs-lookup"><span data-stu-id="823a2-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="823a2-112">如果出现这种情况，打开中的文件`Input`模式或更改文件的只读属性。</span><span class="sxs-lookup"><span data-stu-id="823a2-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="823a2-113">请确保不尝试更改[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]数据库或文档中的项目。</span><span class="sxs-lookup"><span data-stu-id="823a2-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823a2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="823a2-114">See Also</span></span>  
 [<span data-ttu-id="823a2-115">错误类型</span><span class="sxs-lookup"><span data-stu-id="823a2-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
