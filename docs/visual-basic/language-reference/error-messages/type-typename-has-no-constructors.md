---
title: 类型“<typename>”没有构造函数
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: b06c1d930a3551e9bc175c814a6297894799237d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837971"
---
# <a name="type-typename-has-no-constructors"></a><span data-ttu-id="8b8a3-102">类型\<类型名称 > 没有构造函数</span><span class="sxs-lookup"><span data-stu-id="8b8a3-102">Type '\<typename>' has no constructors</span></span>
<span data-ttu-id="8b8a3-103">某个类型不支持对 `Sub New()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="8b8a3-104">一个可能的原因是编译器或二进制文件被损坏。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-104">One possible cause is a corrupted compiler or binary file.</span></span>  
  
 <span data-ttu-id="8b8a3-105">**错误 ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="8b8a3-105">**Error ID:** BC30251</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b8a3-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8b8a3-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="8b8a3-107">如果该类型位于其他项目或一个引用的文件中，则重新安装此项目或文件。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>  
  
2.  <span data-ttu-id="8b8a3-108">如果该类型位于同一个项目中，则重新编译包含该类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-108">If the type is in the same project, recompile the assembly containing the type.</span></span>  
  
3.  <span data-ttu-id="8b8a3-109">如果错误重复出现，请重新安装 Visual Basic 编译器。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>  
  
4.  <span data-ttu-id="8b8a3-110">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="8b8a3-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8a3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b8a3-111">See also</span></span>

- [<span data-ttu-id="8b8a3-112">对象和类</span><span class="sxs-lookup"><span data-stu-id="8b8a3-112">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="8b8a3-113">与我们交流</span><span class="sxs-lookup"><span data-stu-id="8b8a3-113">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
