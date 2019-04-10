---
title: 文件太多
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 1d7fc769a0a2d0f8474c0a72a5600b84c8396201
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310052"
---
# <a name="too-many-files"></a><span data-ttu-id="c130a-102">文件太多</span><span class="sxs-lookup"><span data-stu-id="c130a-102">Too many files</span></span>
<span data-ttu-id="c130a-103">更多的文件已创建的根目录中超出操作系统允许的值，或打开多个文件中指定的数字超出**文件 =** config。SYS 文件。</span><span class="sxs-lookup"><span data-stu-id="c130a-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c130a-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c130a-104">To correct this error</span></span>  
  
1. <span data-ttu-id="c130a-105">如果您的程序是打开、 关闭或保存文件的根目录中，更改您的程序，以便它使用一个子目录。</span><span class="sxs-lookup"><span data-stu-id="c130a-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="c130a-106">增加中指定的文件数你**文件 =** config。SYS 文件，并重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="c130a-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c130a-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="c130a-107">See also</span></span>

- [<span data-ttu-id="c130a-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="c130a-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
