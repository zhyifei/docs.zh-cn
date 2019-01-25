---
title: 构造函数&#39;&lt;名称&gt;&#39;不能调用自身
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 4a02277893147716098a3dcc327e221e0775d476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662720"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="d6b6e-102">构造函数&#39;&lt;名称&gt;&#39;不能调用自身</span><span class="sxs-lookup"><span data-stu-id="d6b6e-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="d6b6e-103">一个`Sub New`类或结构中的过程调用其自身。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="d6b6e-104">结构首次创建或构造函数的用途是初始化类的实例。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="d6b6e-105">类或结构可以具有多个构造函数，前提是它们都具有不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="d6b6e-106">构造函数可以调用另一个构造函数来执行其功能，此外还是其自身。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="d6b6e-107">它是构造函数来调用本身，这对于没有意义，但实际上这会导致无限递归如果允许。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="d6b6e-108">**错误 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="d6b6e-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6b6e-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d6b6e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="d6b6e-110">检查正在调用的构造函数的参数列表。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="d6b6e-111">它应为不同的构造函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="d6b6e-112">如果您不想要调用的其他构造函数，删除`Sub New`完全调用。</span><span class="sxs-lookup"><span data-stu-id="d6b6e-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b6e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6b6e-113">See also</span></span>
- [<span data-ttu-id="d6b6e-114">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="d6b6e-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
