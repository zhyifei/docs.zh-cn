---
title: 私有受保护 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="6b01a-102">私有受保护 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b01a-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="6b01a-103">`Private Protected`关键字组合都是成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="6b01a-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="6b01a-104">A`Private Protected`成员是否可访问由其包含的类中的所有成员以及类型派生自包含的类，但仅当它们位于其包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="6b01a-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span> 

<span data-ttu-id="6b01a-105">你可以指定`Private Protected`仅能对成员的类; 不能应用`Private Protected`结构的成员由于结构不能被继承。</span><span class="sxs-lookup"><span data-stu-id="6b01a-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="6b01a-106">`Private Protected`由 Visual Basic 15.5 和更高版本提供支持访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="6b01a-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="6b01a-107">若要使用它，可以将下面的元素添加到 Visual Basic 项目 (\*.vbproj) 文件。</span><span class="sxs-lookup"><span data-stu-id="6b01a-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="6b01a-108">如你系统上安装了 Visual Basic 15.5 作为长或更高版本，它允许您充分利用最新版本的 Visual Basic 编译器支持的语言功能：</span><span class="sxs-lookup"><span data-stu-id="6b01a-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="6b01a-109">在 Visual Studio 中，选择 F1 帮助上`private protected`提供为帮助[私有](private.md)或[保护](protected.md)。</span><span class="sxs-lookup"><span data-stu-id="6b01a-109">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="6b01a-110">IDE 选取下光标，而不是复合 word 单个标记。</span><span class="sxs-lookup"><span data-stu-id="6b01a-110">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="6b01a-111">规则</span><span class="sxs-lookup"><span data-stu-id="6b01a-111">Rules</span></span>

- <span data-ttu-id="6b01a-112">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="6b01a-112">**Declaration Context.**</span></span> <span data-ttu-id="6b01a-113">你可以使用`Private Protected`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="6b01a-113">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="6b01a-114">这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="6b01a-114">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="6b01a-115">行为</span><span class="sxs-lookup"><span data-stu-id="6b01a-115">Behavior</span></span>

- <span data-ttu-id="6b01a-116">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="6b01a-116">**Access Level.**</span></span> <span data-ttu-id="6b01a-117">类中的所有代码可以都访问其元素。</span><span class="sxs-lookup"><span data-stu-id="6b01a-117">All code in a class can access its elements.</span></span> <span data-ttu-id="6b01a-118">中的任何类都派生自的基类，并且包含在同一程序集代码可以访问所有`Private Protected`元素的基类。</span><span class="sxs-lookup"><span data-stu-id="6b01a-118">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="6b01a-119">但是，在任何类中派生自的基类和其他程序集中包含的代码不能访问的基类`Private Protected`元素。</span><span class="sxs-lookup"><span data-stu-id="6b01a-119">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="6b01a-120">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="6b01a-120">**Access Modifiers.**</span></span> <span data-ttu-id="6b01a-121">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="6b01a-121">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="6b01a-122">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="6b01a-122">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>
  
 <span data-ttu-id="6b01a-123">`Private Protected` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="6b01a-123">The `Private Protected` modifier can be used in these contexts:</span></span>  
  
 <span data-ttu-id="6b01a-124">[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)的嵌套类</span><span class="sxs-lookup"><span data-stu-id="6b01a-124">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>  
  
 [<span data-ttu-id="6b01a-125">Const 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-125">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="6b01a-126">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-126">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="6b01a-127">[Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)委托的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="6b01a-127">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>  
  
 [<span data-ttu-id="6b01a-128">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 <span data-ttu-id="6b01a-129">[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)eumeration 的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="6b01a-129">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an eumeration nested in a class</span></span> 
  
 [<span data-ttu-id="6b01a-130">Event 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-130">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="6b01a-131">Function 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-131">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 <span data-ttu-id="6b01a-132">[Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)接口的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="6b01a-132">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span> 
  
 [<span data-ttu-id="6b01a-133">Property 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 <span data-ttu-id="6b01a-134">[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)结构的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="6b01a-134">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span> 
  
 [<span data-ttu-id="6b01a-135">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="6b01a-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b01a-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b01a-136">See Also</span></span>

[<span data-ttu-id="6b01a-137">Public</span><span class="sxs-lookup"><span data-stu-id="6b01a-137">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="6b01a-138">Protected</span><span class="sxs-lookup"><span data-stu-id="6b01a-138">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="6b01a-139">[友元](friend.md) </span><span class="sxs-lookup"><span data-stu-id="6b01a-139">[Friend](friend.md) </span></span>  
[<span data-ttu-id="6b01a-140">Private</span><span class="sxs-lookup"><span data-stu-id="6b01a-140">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="6b01a-141">[受保护的友元](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="6b01a-141">[Protected Friend](./protected-friend.md) </span></span>  
[<span data-ttu-id="6b01a-142">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="6b01a-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="6b01a-143">过程</span><span class="sxs-lookup"><span data-stu-id="6b01a-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="6b01a-144">结构</span><span class="sxs-lookup"><span data-stu-id="6b01a-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="6b01a-145">对象和类</span><span class="sxs-lookup"><span data-stu-id="6b01a-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
