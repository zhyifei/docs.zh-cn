---
title: 在类构造函数中使用类的默认实例可能会导致无限递归调用
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: b4cae7802019cba569cf15517b1e948266a576f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631430"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="e90c9-102">在类构造函数中使用类的默认实例可能会导致无限递归调用</span><span class="sxs-lookup"><span data-stu-id="e90c9-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="e90c9-103">已在类的构造函数中使用类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="e90c9-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="e90c9-104">这可能会导致无限递归调用（也称为无限循环）。</span><span class="sxs-lookup"><span data-stu-id="e90c9-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e90c9-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e90c9-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e90c9-106">从类构造函数中删除默认实例。</span><span class="sxs-lookup"><span data-stu-id="e90c9-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90c9-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e90c9-107">See also</span></span>
- [<span data-ttu-id="e90c9-108">构造函数</span><span class="sxs-lookup"><span data-stu-id="e90c9-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
