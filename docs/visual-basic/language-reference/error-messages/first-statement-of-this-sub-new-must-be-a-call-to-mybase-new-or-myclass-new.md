---
title: 该“Sub New”的第一个语句必须是对“MyBase.New”或“MyClass.New”的调用（没有不带参数的可访问构造函数）
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: debab4e495d05a05801dd11850d0665c8bd6b299
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801369"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="36be9-102">该“Sub New”的第一个语句必须是对“MyBase.New”或“MyClass.New”的调用（没有不带参数的可访问构造函数）</span><span class="sxs-lookup"><span data-stu-id="36be9-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="36be9-103">此 Sub New 的第一个语句必须是对 MyBase.New 或 MyClass.New 的调用，因为基类 '\<basename > 的\<derivedname > 不具有可访问 Sub New，可以调用不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="36be9-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="36be9-104">在派生类中，每个构造函数必须调用基类构造函数 (`MyBase.New`)。</span><span class="sxs-lookup"><span data-stu-id="36be9-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="36be9-105">如果基类具有不带任何参数是可用于派生类的构造函数`MyBase.New`可以自动调用。</span><span class="sxs-lookup"><span data-stu-id="36be9-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="36be9-106">如果没有，则必须使用参数，调用基类构造函数，这不能自动完成。</span><span class="sxs-lookup"><span data-stu-id="36be9-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="36be9-107">在这种情况下，每个派生的类构造函数的第一个语句必须在基础类上调用参数化构造函数或调用另一个构造函数可以调用基类构造函数在派生类中。</span><span class="sxs-lookup"><span data-stu-id="36be9-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="36be9-108">**错误 ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="36be9-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="36be9-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="36be9-109">To correct this error</span></span>  
  
- <span data-ttu-id="36be9-110">调用`MyBase.New`提供所需的参数，或调用此类调用对等构造函数。</span><span class="sxs-lookup"><span data-stu-id="36be9-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="36be9-111">例如，如果基本类具有声明为一个构造函数`Public Sub New(ByVal index as Integer)`中，第一个语句中的派生类构造函数可能是`MyBase.New(100)`。</span><span class="sxs-lookup"><span data-stu-id="36be9-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36be9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="36be9-112">See also</span></span>

- [<span data-ttu-id="36be9-113">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="36be9-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
