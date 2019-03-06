---
title: 专用受保护 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376385"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="78645-102">专用受保护 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78645-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="78645-103">`Private Protected` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="78645-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="78645-104">一个`Private Protected`成员是由其包含的类中的所有成员以及派生自包含类的类型可访问，但仅当它们位于其包含程序集。</span><span class="sxs-lookup"><span data-stu-id="78645-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="78645-105">您可以指定`Private Protected`只能在类; 的成员上不能应用`Private Protected`为结构成员的因为结构不能被继承。</span><span class="sxs-lookup"><span data-stu-id="78645-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="78645-106">`Private Protected`由 Visual Basic 15.5 和更高版本提供支持访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="78645-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="78645-107">若要使用它，您可以将以下元素添加到 Visual Basic 项目 (\*.vbproj) 文件。</span><span class="sxs-lookup"><span data-stu-id="78645-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="78645-108">只要 Visual Basic 15.5 或更高版本在系统上安装的因为它允许您充分利用所有最新版本的 Visual Basic 编译器支持的语言功能：</span><span class="sxs-lookup"><span data-stu-id="78645-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="78645-109">有关详细信息请参阅[设置的 Visual Basic 语言版本](../../language-reference/configure-language-version.md)。</span><span class="sxs-lookup"><span data-stu-id="78645-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78645-110">在 Visual Studio 中，选择上的 F1 帮助`private protected`提供有关可以帮助[专用](private.md)或[保护](protected.md)。</span><span class="sxs-lookup"><span data-stu-id="78645-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="78645-111">IDE 选取单个令牌在光标，而不是组合词。</span><span class="sxs-lookup"><span data-stu-id="78645-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="78645-112">规则</span><span class="sxs-lookup"><span data-stu-id="78645-112">Rules</span></span>

- <span data-ttu-id="78645-113">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="78645-113">**Declaration Context.**</span></span> <span data-ttu-id="78645-114">可以使用`Private Protected`仅在类级别。</span><span class="sxs-lookup"><span data-stu-id="78645-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="78645-115">这意味着声明上下文`Protected`元素必须是类，且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="78645-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="78645-116">行为</span><span class="sxs-lookup"><span data-stu-id="78645-116">Behavior</span></span>

- <span data-ttu-id="78645-117">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="78645-117">**Access Level.**</span></span> <span data-ttu-id="78645-118">在类中的所有代码可以都访问它的元素。</span><span class="sxs-lookup"><span data-stu-id="78645-118">All code in a class can access its elements.</span></span> <span data-ttu-id="78645-119">中的任何类都派生自的基类并且包含在同一程序集代码可以访问所有`Private Protected`元素的基类。</span><span class="sxs-lookup"><span data-stu-id="78645-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="78645-120">但是中的任何类都派生自的基类和其他程序集中包含的代码无法访问的基类`Private Protected`元素。</span><span class="sxs-lookup"><span data-stu-id="78645-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="78645-121">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="78645-121">**Access Modifiers.**</span></span> <span data-ttu-id="78645-122">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="78645-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="78645-123">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="78645-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="78645-124">
  `Private Protected\` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="78645-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="78645-125">[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)的嵌套类</span><span class="sxs-lookup"><span data-stu-id="78645-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="78645-126">Const 语句</span><span class="sxs-lookup"><span data-stu-id="78645-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="78645-127">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="78645-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="78645-128">[Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)委托的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="78645-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="78645-129">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="78645-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="78645-130">[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)枚举的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="78645-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="78645-131">Event 语句</span><span class="sxs-lookup"><span data-stu-id="78645-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="78645-132">Function 语句</span><span class="sxs-lookup"><span data-stu-id="78645-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="78645-133">[Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)接口的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="78645-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="78645-134">Property 语句</span><span class="sxs-lookup"><span data-stu-id="78645-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="78645-135">[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)结构的嵌套类中</span><span class="sxs-lookup"><span data-stu-id="78645-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="78645-136">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="78645-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="78645-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="78645-137">See also</span></span>

- [<span data-ttu-id="78645-138">Public</span><span class="sxs-lookup"><span data-stu-id="78645-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="78645-139">Protected</span><span class="sxs-lookup"><span data-stu-id="78645-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="78645-140">Friend</span><span class="sxs-lookup"><span data-stu-id="78645-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="78645-141">Private</span><span class="sxs-lookup"><span data-stu-id="78645-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="78645-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="78645-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="78645-143">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="78645-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="78645-144">过程</span><span class="sxs-lookup"><span data-stu-id="78645-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="78645-145">结构</span><span class="sxs-lookup"><span data-stu-id="78645-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="78645-146">对象和类</span><span class="sxs-lookup"><span data-stu-id="78645-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
