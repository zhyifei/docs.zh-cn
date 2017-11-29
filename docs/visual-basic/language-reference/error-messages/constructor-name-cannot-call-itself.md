---
title: "构造函数 &#39;&lt;名称&gt;&#39; 不能调用其自身"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="5433b-102">构造函数 &#39;&lt;名称&gt;&#39; 不能调用其自身</span><span class="sxs-lookup"><span data-stu-id="5433b-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="5433b-103">A`Sub New`类或结构中的过程调用其自身。</span><span class="sxs-lookup"><span data-stu-id="5433b-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="5433b-104">构造函数的用途是初始化类的实例，或创建结构时第一个。</span><span class="sxs-lookup"><span data-stu-id="5433b-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="5433b-105">类或结构可以具有多个构造函数，前提是它们都具有不同参数列表。</span><span class="sxs-lookup"><span data-stu-id="5433b-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="5433b-106">允许一个构造函数调用另一个构造函数来执行其自身除了其功能。</span><span class="sxs-lookup"><span data-stu-id="5433b-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="5433b-107">但该无意义的构造函数调用自身，并且实际上会导致无限递归如果允许。</span><span class="sxs-lookup"><span data-stu-id="5433b-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="5433b-108">**错误 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="5433b-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5433b-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5433b-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="5433b-110">检查正在调用的构造函数的参数列表。</span><span class="sxs-lookup"><span data-stu-id="5433b-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="5433b-111">它应不同于该构造函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="5433b-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="5433b-112">如果你不想要调用的其他构造函数，则删除`Sub New`完全调用。</span><span class="sxs-lookup"><span data-stu-id="5433b-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5433b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5433b-113">See Also</span></span>  
 [<span data-ttu-id="5433b-114">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="5433b-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
