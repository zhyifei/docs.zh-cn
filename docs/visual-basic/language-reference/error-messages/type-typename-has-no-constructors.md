---
title: 类型“<typename>”没有构造函数
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 6a12bc35aeaa6e9e21835ce0a091ee89ea4c326d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260360"
---
# <a name="type-typename-has-no-constructors"></a><span data-ttu-id="9b04e-102">类型\<类型名称 > 没有构造函数</span><span class="sxs-lookup"><span data-stu-id="9b04e-102">Type '\<typename>' has no constructors</span></span>
<span data-ttu-id="9b04e-103">某个类型不支持对 `Sub New()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="9b04e-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="9b04e-104">一个可能的原因是编译器或二进制文件被损坏。</span><span class="sxs-lookup"><span data-stu-id="9b04e-104">One possible cause is a corrupted compiler or binary file.</span></span>  
  
 <span data-ttu-id="9b04e-105">**错误 ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="9b04e-105">**Error ID:** BC30251</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b04e-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9b04e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="9b04e-107">如果该类型位于其他项目或一个引用的文件中，则重新安装此项目或文件。</span><span class="sxs-lookup"><span data-stu-id="9b04e-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>  
  
2.  <span data-ttu-id="9b04e-108">如果该类型位于同一个项目中，则重新编译包含该类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="9b04e-108">If the type is in the same project, recompile the assembly containing the type.</span></span>  
  
3.  <span data-ttu-id="9b04e-109">如果错误重复出现，请重新安装 Visual Basic 编译器。</span><span class="sxs-lookup"><span data-stu-id="9b04e-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>  
  
4.  <span data-ttu-id="9b04e-110">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="9b04e-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b04e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b04e-111">See also</span></span>
- [<span data-ttu-id="9b04e-112">对象和类</span><span class="sxs-lookup"><span data-stu-id="9b04e-112">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="9b04e-113">与我们交流</span><span class="sxs-lookup"><span data-stu-id="9b04e-113">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
