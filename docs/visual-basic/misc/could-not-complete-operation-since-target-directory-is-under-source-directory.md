---
title: 未能完成操作，因为目标目录位于源目录下
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 68217023a980891200c18b5536ef902574d36257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638507"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="7fb58-102">未能完成操作，因为目标目录位于源目录下</span><span class="sxs-lookup"><span data-stu-id="7fb58-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="7fb58-103">循环操作已失败。</span><span class="sxs-lookup"><span data-stu-id="7fb58-103">A cyclic operation has failed.</span></span> <span data-ttu-id="7fb58-104">循环操作正在循环，因此无法完成。</span><span class="sxs-lookup"><span data-stu-id="7fb58-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="7fb58-105">例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。</span><span class="sxs-lookup"><span data-stu-id="7fb58-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7fb58-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7fb58-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7fb58-107">继承时，请确保没有任何循环引用。</span><span class="sxs-lookup"><span data-stu-id="7fb58-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb58-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fb58-108">See Also</span></span>  
 [<span data-ttu-id="7fb58-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="7fb58-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="7fb58-110">调试基础知识： 断点</span><span class="sxs-lookup"><span data-stu-id="7fb58-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
