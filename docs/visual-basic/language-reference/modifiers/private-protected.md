---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351348"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="53bbd-102">私有受保护（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="53bbd-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="53bbd-103">`Private Protected` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="53bbd-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="53bbd-104">`Private Protected` 成员可以由其包含类中的所有成员访问，也可由派生自包含类的类型访问，但前提是在它的包含程序集内找到。</span><span class="sxs-lookup"><span data-stu-id="53bbd-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="53bbd-105">只能在类的成员上指定 `Private Protected`;无法将 `Private Protected` 应用到结构的成员，因为结构不能继承。</span><span class="sxs-lookup"><span data-stu-id="53bbd-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="53bbd-106">Visual Basic 15.5 及更高版本支持 `Private Protected` 访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="53bbd-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="53bbd-107">若要使用它，可以将以下元素添加到 Visual Basic 项目（\*.vbproj）文件。</span><span class="sxs-lookup"><span data-stu-id="53bbd-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="53bbd-108">只要您的系统上安装了 Visual Basic 15.5 或更高版本，就可以利用 Visual Basic 编译器最新版本支持的所有语言功能：</span><span class="sxs-lookup"><span data-stu-id="53bbd-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="53bbd-109">有关详细信息，请参阅[设置 Visual Basic 语言版本](../../language-reference/configure-language-version.md)。</span><span class="sxs-lookup"><span data-stu-id="53bbd-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53bbd-110">在 Visual Studio 中，选择 `private protected` 上的 F1 帮助为[私有](private.md)或[受保护](protected.md)的提供帮助。</span><span class="sxs-lookup"><span data-stu-id="53bbd-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="53bbd-111">IDE 将选取光标下的单个标记，而不是组合词。</span><span class="sxs-lookup"><span data-stu-id="53bbd-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="53bbd-112">规则</span><span class="sxs-lookup"><span data-stu-id="53bbd-112">Rules</span></span>

- <span data-ttu-id="53bbd-113">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="53bbd-113">**Declaration Context.**</span></span> <span data-ttu-id="53bbd-114">只能在类级别使用 `Private Protected`。</span><span class="sxs-lookup"><span data-stu-id="53bbd-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="53bbd-115">这意味着 `Protected` 元素的声明上下文必须是类，且不能是源文件、命名空间、接口、模块、结构或过程。</span><span class="sxs-lookup"><span data-stu-id="53bbd-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="53bbd-116">行为</span><span class="sxs-lookup"><span data-stu-id="53bbd-116">Behavior</span></span>

- <span data-ttu-id="53bbd-117">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="53bbd-117">**Access Level.**</span></span> <span data-ttu-id="53bbd-118">类中的所有代码都可以访问其元素。</span><span class="sxs-lookup"><span data-stu-id="53bbd-118">All code in a class can access its elements.</span></span> <span data-ttu-id="53bbd-119">派生自基类并包含在同一程序集中的任何类中的代码都可以访问该基类的所有 `Private Protected` 元素。</span><span class="sxs-lookup"><span data-stu-id="53bbd-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="53bbd-120">但是，任何派生自基类的类中的代码都包含在不同的程序集中，因此无法访问基类 `Private Protected` 元素。</span><span class="sxs-lookup"><span data-stu-id="53bbd-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="53bbd-121">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="53bbd-121">**Access Modifiers.**</span></span> <span data-ttu-id="53bbd-122">指定访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="53bbd-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="53bbd-123">有关访问修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="53bbd-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="53bbd-124">`Private Protected` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="53bbd-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="53bbd-125">嵌套类的[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)</span><span class="sxs-lookup"><span data-stu-id="53bbd-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="53bbd-126">Const 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="53bbd-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="53bbd-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="53bbd-128">嵌套在类中的委托的[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)</span><span class="sxs-lookup"><span data-stu-id="53bbd-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="53bbd-129">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="53bbd-130">嵌套在类中的枚举的[枚举语句](../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="53bbd-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="53bbd-131">Event 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="53bbd-132">Function 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="53bbd-133">嵌套在类中的接口的[接口语句](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="53bbd-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="53bbd-134">Property 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="53bbd-135">嵌套在类中的结构的[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)</span><span class="sxs-lookup"><span data-stu-id="53bbd-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="53bbd-136">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="53bbd-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="53bbd-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53bbd-137">See also</span></span>

- [<span data-ttu-id="53bbd-138">Public</span><span class="sxs-lookup"><span data-stu-id="53bbd-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="53bbd-139">Protected</span><span class="sxs-lookup"><span data-stu-id="53bbd-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="53bbd-140">Friend</span><span class="sxs-lookup"><span data-stu-id="53bbd-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="53bbd-141">Private</span><span class="sxs-lookup"><span data-stu-id="53bbd-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="53bbd-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="53bbd-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="53bbd-143">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="53bbd-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="53bbd-144">过程</span><span class="sxs-lookup"><span data-stu-id="53bbd-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="53bbd-145">结构</span><span class="sxs-lookup"><span data-stu-id="53bbd-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="53bbd-146">对象和类</span><span class="sxs-lookup"><span data-stu-id="53bbd-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
