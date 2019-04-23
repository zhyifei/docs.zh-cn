---
title: 权限被拒绝 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318821"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="70625-102">权限被拒绝 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70625-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="70625-103">尝试写入受写保护的磁盘或访问锁定的文件。</span><span class="sxs-lookup"><span data-stu-id="70625-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70625-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="70625-104">To correct this error</span></span>  
  
1. <span data-ttu-id="70625-105">若要打开受写保护的文件，请更改文件的写保护属性。</span><span class="sxs-lookup"><span data-stu-id="70625-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="70625-106">请确保另一个进程已不锁定该文件，并等待，直到另一个进程释放它打开该文件。</span><span class="sxs-lookup"><span data-stu-id="70625-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="70625-107">若要访问注册表，请检查您的用户权限，包括此类型的注册表访问。</span><span class="sxs-lookup"><span data-stu-id="70625-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70625-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="70625-108">See also</span></span>

- [<span data-ttu-id="70625-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="70625-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
