---
title: 已声明的元素名称 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 2f48f885b66f99ecc8c6c7e13fea7e75f0e3d24a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651474"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="deedd-102">已声明的元素名称 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="deedd-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="deedd-103">每个声明的元素有一个名称，也称为*标识符*，即来引用它的代码使用。</span><span class="sxs-lookup"><span data-stu-id="deedd-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="deedd-104">规则</span><span class="sxs-lookup"><span data-stu-id="deedd-104">Rules</span></span>  
 <span data-ttu-id="deedd-105">在 Visual Basic 中的元素名称必须遵守以下规则：</span><span class="sxs-lookup"><span data-stu-id="deedd-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
-   <span data-ttu-id="deedd-106">它必须以字母字符或下划线开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="deedd-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="deedd-107">它必须仅包含字母字符、 十进制数字和下划线。</span><span class="sxs-lookup"><span data-stu-id="deedd-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="deedd-108">如果以下划线开头，它必须包含至少一个字母字符或十进制数。</span><span class="sxs-lookup"><span data-stu-id="deedd-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="deedd-109">它不得超过 1023年个字符长。</span><span class="sxs-lookup"><span data-stu-id="deedd-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="deedd-110">1023 个字符的长度限制也适用于整个字符串的完全限定名称，如`outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`。</span><span class="sxs-lookup"><span data-stu-id="deedd-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="deedd-111">下面的示例演示了一些有效的元素名称。</span><span class="sxs-lookup"><span data-stu-id="deedd-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="deedd-112">下面的示例演示一些无效的元素名称。</span><span class="sxs-lookup"><span data-stu-id="deedd-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="deedd-113">第一个仅包含一个下划线、 十进制数字，开头开始第二个和第三个包含无效字符 （$）。</span><span class="sxs-lookup"><span data-stu-id="deedd-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="deedd-114">元素名称以下划线开头 (`_`) 不属于[语言独立性和独立于语言的组件](../../../../standard/language-independence-and-language-independent-components.md)(CLS)，因此符合 cls 的代码不能使用定义此类名称的组件。</span><span class="sxs-lookup"><span data-stu-id="deedd-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="deedd-115">但是，在元素名中的任何其他位置中以下划线是符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="deedd-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="deedd-116">名称长度准则</span><span class="sxs-lookup"><span data-stu-id="deedd-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="deedd-117">在实践中，你的名称应尽可能短同时在仍然能够清楚地标识的元素的性质。</span><span class="sxs-lookup"><span data-stu-id="deedd-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="deedd-118">这可以提高代码的可读性，并减少行长度和源文件大小。</span><span class="sxs-lookup"><span data-stu-id="deedd-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="deedd-119">另一方面，你的名称不应为太短，它不会不充分描述该元素表示和你的代码如何使用它。</span><span class="sxs-lookup"><span data-stu-id="deedd-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="deedd-120">这是你代码的可读性很重要。</span><span class="sxs-lookup"><span data-stu-id="deedd-120">This is important for the readability of your code.</span></span> <span data-ttu-id="deedd-121">如果其他人尝试理解它，或你自己正在寻求通过它您在编写后很长时间，适合元素名称可以节省相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="deedd-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="deedd-122">转义的名称</span><span class="sxs-lookup"><span data-stu-id="deedd-122">Escaped Names</span></span>  
 <span data-ttu-id="deedd-123">通常，元素名称必须不匹配的任何关键字由 Visual Basic 中，如保留`Case`或`Friend`。</span><span class="sxs-lookup"><span data-stu-id="deedd-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="deedd-124">但是，你可以定义*转义名称*，这由括号括起来 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="deedd-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="deedd-125">转义的名称可以匹配任何 Visual Basic 关键字，因为括号消除了不明确性。</span><span class="sxs-lookup"><span data-stu-id="deedd-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="deedd-126">在更高版本在你的代码中引用名时，还可以使用括号。</span><span class="sxs-lookup"><span data-stu-id="deedd-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="deedd-127">一般情况下，应使用转义的名称时，才：</span><span class="sxs-lookup"><span data-stu-id="deedd-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="deedd-128">你的代码已从没有保留关键字作为名称; 正在使用的 Visual Basic 的早期版本迁移或</span><span class="sxs-lookup"><span data-stu-id="deedd-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="deedd-129">你正在使用在其中给定的关键字不保留的另一种语言编写的代码。</span><span class="sxs-lookup"><span data-stu-id="deedd-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="deedd-130">否则，应考虑重命名元素，如果其名称与关键字冲突。</span><span class="sxs-lookup"><span data-stu-id="deedd-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="deedd-131">集成的开发环境 (IDE) 提供了执行此操作的简单办法。</span><span class="sxs-lookup"><span data-stu-id="deedd-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="deedd-132">有关详细信息，请参阅[重构](/visualstudio/vb-ide/refactoring-vb)。</span><span class="sxs-lookup"><span data-stu-id="deedd-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="deedd-133">在名称中的区分大小写</span><span class="sxs-lookup"><span data-stu-id="deedd-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="deedd-134">在 Visual Basic 中的元素名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="deedd-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="deedd-135">这意味着当编译器在比较两个字母大小写不同的名称，将其解释为相同的名称。</span><span class="sxs-lookup"><span data-stu-id="deedd-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="deedd-136">例如，它认为 `ABC` 和 `abc` 指的是同一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="deedd-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="deedd-137">但是，公共语言运行时 (CLR) 使用区分大小写的绑定。</span><span class="sxs-lookup"><span data-stu-id="deedd-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="deedd-138">因此，当你生成程序集或 DLL 并使其可供其他程序集使用时，则名称将不再不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="deedd-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="deedd-139">例如，如果你用名为 `ABC`的元素定义类，而其他程序集通过公共语言运行时使用你的类，则元素必须指的是 `ABC`。</span><span class="sxs-lookup"><span data-stu-id="deedd-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="deedd-140">如果你以后重新编译你的类并将更改元素的名称与`abc`，则使用你的类的其他程序集将无法再访问该元素。</span><span class="sxs-lookup"><span data-stu-id="deedd-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="deedd-141">因此，发布程序集的更新版本时，不应该更改公共元素的字母大小写。</span><span class="sxs-lookup"><span data-stu-id="deedd-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="deedd-142">名称和区域设置</span><span class="sxs-lookup"><span data-stu-id="deedd-142">Names and Locales</span></span>  
 <span data-ttu-id="deedd-143">名称比较是独立于区域设置。</span><span class="sxs-lookup"><span data-stu-id="deedd-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="deedd-144">如果在一个区域设置中匹配两个名称，可确保在所有区域设置匹配。</span><span class="sxs-lookup"><span data-stu-id="deedd-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deedd-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="deedd-145">See Also</span></span>  
 [<span data-ttu-id="deedd-146">已声明的元素</span><span class="sxs-lookup"><span data-stu-id="deedd-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [<span data-ttu-id="deedd-147">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="deedd-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="deedd-148">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="deedd-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="deedd-149">语句</span><span class="sxs-lookup"><span data-stu-id="deedd-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
