---
title: 此第一个语句&#39;Sub New&#39;必须是对调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39; （不带参数没有可访问构造函数）
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589455"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="f66c6-102">此第一个语句&#39;Sub New&#39;必须是对调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39; （不带参数没有可访问构造函数）</span><span class="sxs-lookup"><span data-stu-id="f66c6-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="f66c6-103">此 Sub New 的第一个语句必须是对 MyBase.New 或 MyClass.New 的调用，因为基类的\<基名称 > 的\<derivedname > 没有可访问 Sub New 可调用不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="f66c6-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="f66c6-104">在派生类中，每个构造函数必须调用基类构造函数 (`MyBase.New`)。</span><span class="sxs-lookup"><span data-stu-id="f66c6-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="f66c6-105">如果基类中存在的构造函数不带任何参数派生的类，可以访问的`MyBase.New`可以自动调用。</span><span class="sxs-lookup"><span data-stu-id="f66c6-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="f66c6-106">如果没有，则必须使用参数，调用基类构造函数，这不能自动完成。</span><span class="sxs-lookup"><span data-stu-id="f66c6-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="f66c6-107">在这种情况下，每个派生的类构造函数的第一个语句必须调用基类，参数化构造函数，或使基类构造函数调用派生类中调用另一个构造函数。</span><span class="sxs-lookup"><span data-stu-id="f66c6-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="f66c6-108">**错误 ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="f66c6-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f66c6-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f66c6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f66c6-110">调用`MyBase.New`提供所需的参数，或调用此类调用的对等构造函数。</span><span class="sxs-lookup"><span data-stu-id="f66c6-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="f66c6-111">例如，如果基类具有构造函数声明为`Public Sub New(ByVal index as Integer)`，第一个语句中派生类构造函数可能`MyBase.New(100)`。</span><span class="sxs-lookup"><span data-stu-id="f66c6-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66c6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f66c6-112">See Also</span></span>  
 [<span data-ttu-id="f66c6-113">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="f66c6-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
