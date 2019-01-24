---
title: 权限被拒绝 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: 43ec20382a2043868fb54e2f472cb316ebfbd623
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717826"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="afb17-102">权限被拒绝 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afb17-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="afb17-103">尝试写入受写保护的磁盘或访问锁定的文件。</span><span class="sxs-lookup"><span data-stu-id="afb17-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="afb17-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="afb17-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="afb17-105">若要打开受写保护的文件，请更改文件的写保护属性。</span><span class="sxs-lookup"><span data-stu-id="afb17-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="afb17-106">请确保另一个进程已不锁定该文件，并等待，直到另一个进程释放它打开该文件。</span><span class="sxs-lookup"><span data-stu-id="afb17-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="afb17-107">若要访问注册表，请检查您的用户权限，包括此类型的注册表访问。</span><span class="sxs-lookup"><span data-stu-id="afb17-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb17-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="afb17-108">See also</span></span>
- [<span data-ttu-id="afb17-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="afb17-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
