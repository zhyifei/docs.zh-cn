---
title: Imports“<qualifiedelementname>”中指定的命名空间或类型不包含任何公共成员，或者找不到该命名空间或类型
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 1873c0af7a251afd7754557f5dcb6aed13eb9f11
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357880"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="0f9d9-102">中的导入指定的 Namespace 或类型\<qualifiedelementname > 不包含任何公共成员，或者找不到</span><span class="sxs-lookup"><span data-stu-id="0f9d9-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="0f9d9-103">中的导入指定的 Namespace 或类型\<qualifiedelementname > 不包含任何公共成员，或者找不到。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="0f9d9-104">请确保该命名空间或类型定义，其中包含至少一个公共成员。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="0f9d9-105">请确保别名名称中不包含其他别名。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="0f9d9-106">`Imports`语句指定的包含元素不能为找到或未定义任何`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="0f9d9-107">一个*包含元素*可以是命名空间、 类、 结构、 模块、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="0f9d9-108">包含元素包含成员，例如变量、 过程或其他包含的元素。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="0f9d9-109">导入的目的是允许你访问命名空间或类型成员的代码而无需限定它们。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="0f9d9-110">你的项目可能还需要添加对命名空间或类型的引用。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="0f9d9-111">详细信息，请参阅"导入包含元素"中[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="0f9d9-112">如果编译器找不到指定的包含元素，它无法解析使用它的引用。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="0f9d9-113">如果它找到的元素，但该元素不会公开任何`Public`成员，则任何引用都不会成功。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="0f9d9-114">在任一情况下是没有意义的 import 元素。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="0f9d9-115">请记住，如果您导入包含元素，并为其分配的导入别名，然后您不能使用该导入别名来导入另一个元素。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="0f9d9-116">下面的代码生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="0f9d9-117">**错误 ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="0f9d9-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0f9d9-118">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0f9d9-118">To correct this error</span></span>

1. <span data-ttu-id="0f9d9-119">验证包含的元素可从你的项目进行访问。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="0f9d9-120">验证包含的元素的规范不包括从另一个导入任何导入别名。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="0f9d9-121">验证包含的元素公开至少一个`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="0f9d9-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f9d9-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f9d9-122">See also</span></span>

- [<span data-ttu-id="0f9d9-123">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="0f9d9-123">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="0f9d9-124">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="0f9d9-124">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="0f9d9-125">Public</span><span class="sxs-lookup"><span data-stu-id="0f9d9-125">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="0f9d9-126">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="0f9d9-126">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="0f9d9-127">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="0f9d9-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
