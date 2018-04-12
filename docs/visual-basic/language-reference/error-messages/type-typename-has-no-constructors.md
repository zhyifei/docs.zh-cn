---
title: 类型 &#39;&lt;typename&gt;&#39; 没有构造函数
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2c1bfcc4af928fff6a10ca3d97957e75cbd7355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-has-no-constructors"></a><span data-ttu-id="b1e28-102">类型 &#39;&lt;typename&gt;&#39; 没有构造函数</span><span class="sxs-lookup"><span data-stu-id="b1e28-102">Type &#39;&lt;typename&gt;&#39; has no constructors</span></span>
<span data-ttu-id="b1e28-103">某个类型不支持对 `Sub New()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="b1e28-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="b1e28-104">一个可能的原因是编译器或二进制文件被损坏。</span><span class="sxs-lookup"><span data-stu-id="b1e28-104">One possible cause is a corrupted compiler or binary file.</span></span>  
  
 <span data-ttu-id="b1e28-105">**错误 ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="b1e28-105">**Error ID:** BC30251</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1e28-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b1e28-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b1e28-107">如果该类型位于其他项目或一个引用的文件中，则重新安装此项目或文件。</span><span class="sxs-lookup"><span data-stu-id="b1e28-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>  
  
2.  <span data-ttu-id="b1e28-108">如果该类型位于同一个项目中，则重新编译包含该类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="b1e28-108">If the type is in the same project, recompile the assembly containing the type.</span></span>  
  
3.  <span data-ttu-id="b1e28-109">如果错误重复出现，请重新安装 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器。</span><span class="sxs-lookup"><span data-stu-id="b1e28-109">If the error recurs, reinstall the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler.</span></span>  
  
4.  <span data-ttu-id="b1e28-110">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="b1e28-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e28-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1e28-111">See Also</span></span>  
 [<span data-ttu-id="b1e28-112">对象和类</span><span class="sxs-lookup"><span data-stu-id="b1e28-112">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="b1e28-113">与我们交流</span><span class="sxs-lookup"><span data-stu-id="b1e28-113">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
