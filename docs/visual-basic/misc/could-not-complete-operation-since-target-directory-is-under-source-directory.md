---
title: 未能完成操作，因为目标目录位于源目录下
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: fca42f91f803a6b12535badcb25cc05cc3d23f6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598472"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="9bf90-102">未能完成操作，因为目标目录位于源目录下</span><span class="sxs-lookup"><span data-stu-id="9bf90-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="9bf90-103">循环操作已失败。</span><span class="sxs-lookup"><span data-stu-id="9bf90-103">A cyclic operation has failed.</span></span> <span data-ttu-id="9bf90-104">循环操作正在循环，因此无法完成。</span><span class="sxs-lookup"><span data-stu-id="9bf90-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="9bf90-105">例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。</span><span class="sxs-lookup"><span data-stu-id="9bf90-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9bf90-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9bf90-106">To correct this error</span></span>  
  
- <span data-ttu-id="9bf90-107">继承时，请确保没有任何循环引用。</span><span class="sxs-lookup"><span data-stu-id="9bf90-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf90-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf90-108">See also</span></span>

- [<span data-ttu-id="9bf90-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="9bf90-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="9bf90-110">在 Visual Studio 调试器中使用断点</span><span class="sxs-lookup"><span data-stu-id="9bf90-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
