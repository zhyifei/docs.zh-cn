---
title: 构造函数“<name>”不能调用自身
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324378"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="c79e2-102">构造函数\<名称 > 不能调用自身</span><span class="sxs-lookup"><span data-stu-id="c79e2-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="c79e2-103">一个`Sub New`类或结构中的过程调用其自身。</span><span class="sxs-lookup"><span data-stu-id="c79e2-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="c79e2-104">结构首次创建或构造函数的用途是初始化类的实例。</span><span class="sxs-lookup"><span data-stu-id="c79e2-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="c79e2-105">类或结构可以具有多个构造函数，前提是它们都具有不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="c79e2-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="c79e2-106">构造函数可以调用另一个构造函数来执行其功能，此外还是其自身。</span><span class="sxs-lookup"><span data-stu-id="c79e2-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="c79e2-107">它是构造函数来调用本身，这对于没有意义，但实际上这会导致无限递归如果允许。</span><span class="sxs-lookup"><span data-stu-id="c79e2-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="c79e2-108">**错误 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="c79e2-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c79e2-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c79e2-109">To correct this error</span></span>  
  
1. <span data-ttu-id="c79e2-110">检查正在调用的构造函数的参数列表。</span><span class="sxs-lookup"><span data-stu-id="c79e2-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="c79e2-111">它应为不同的构造函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="c79e2-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="c79e2-112">如果您不想要调用的其他构造函数，删除`Sub New`完全调用。</span><span class="sxs-lookup"><span data-stu-id="c79e2-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79e2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c79e2-113">See also</span></span>

- [<span data-ttu-id="c79e2-114">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="c79e2-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
