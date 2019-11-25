---
title: Declared Element Names
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
ms.openlocfilehash: e8620517b934a5f1a97ea25c5a94c8b932bb47b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345430"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="b88ba-102">已声明的元素名称 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b88ba-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="b88ba-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span><span class="sxs-lookup"><span data-stu-id="b88ba-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b88ba-104">规则</span><span class="sxs-lookup"><span data-stu-id="b88ba-104">Rules</span></span>  
 <span data-ttu-id="b88ba-105">An element name in Visual Basic must observe the following rules:</span><span class="sxs-lookup"><span data-stu-id="b88ba-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="b88ba-106">It must begin with an alphabetic character or an underscore (`_`).</span><span class="sxs-lookup"><span data-stu-id="b88ba-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="b88ba-107">It must only contain alphabetic characters, decimal digits, and underscores.</span><span class="sxs-lookup"><span data-stu-id="b88ba-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="b88ba-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span><span class="sxs-lookup"><span data-stu-id="b88ba-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="b88ba-109">It must not be more than 1023 characters long.</span><span class="sxs-lookup"><span data-stu-id="b88ba-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="b88ba-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="b88ba-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="b88ba-111">The following example shows some valid element names.</span><span class="sxs-lookup"><span data-stu-id="b88ba-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="b88ba-112">The following example shows some invalid element names.</span><span class="sxs-lookup"><span data-stu-id="b88ba-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="b88ba-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span><span class="sxs-lookup"><span data-stu-id="b88ba-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="b88ba-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span><span class="sxs-lookup"><span data-stu-id="b88ba-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="b88ba-115">However, an underscore in any other position in an element name is CLS-compliant.</span><span class="sxs-lookup"><span data-stu-id="b88ba-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="b88ba-116">Name Length Guidelines</span><span class="sxs-lookup"><span data-stu-id="b88ba-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="b88ba-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span><span class="sxs-lookup"><span data-stu-id="b88ba-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="b88ba-118">This improves the readability of your code and reduces line length and source-file size.</span><span class="sxs-lookup"><span data-stu-id="b88ba-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="b88ba-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span><span class="sxs-lookup"><span data-stu-id="b88ba-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="b88ba-120">This is important for the readability of your code.</span><span class="sxs-lookup"><span data-stu-id="b88ba-120">This is important for the readability of your code.</span></span> <span data-ttu-id="b88ba-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span><span class="sxs-lookup"><span data-stu-id="b88ba-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="b88ba-122">Escaped Names</span><span class="sxs-lookup"><span data-stu-id="b88ba-122">Escaped Names</span></span>  
 <span data-ttu-id="b88ba-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span><span class="sxs-lookup"><span data-stu-id="b88ba-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="b88ba-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="b88ba-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="b88ba-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span><span class="sxs-lookup"><span data-stu-id="b88ba-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="b88ba-126">You also use the brackets when you refer to the name later in your code.</span><span class="sxs-lookup"><span data-stu-id="b88ba-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="b88ba-127">In general, you should use escaped names only when:</span><span class="sxs-lookup"><span data-stu-id="b88ba-127">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="b88ba-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span><span class="sxs-lookup"><span data-stu-id="b88ba-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="b88ba-129">You are working with code written in another language in which the given keyword is not reserved.</span><span class="sxs-lookup"><span data-stu-id="b88ba-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="b88ba-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span><span class="sxs-lookup"><span data-stu-id="b88ba-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="b88ba-131">The integrated development environment (IDE) provides an easy way to do this.</span><span class="sxs-lookup"><span data-stu-id="b88ba-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="b88ba-132">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b88ba-132">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="b88ba-133">Case Sensitivity in Names</span><span class="sxs-lookup"><span data-stu-id="b88ba-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="b88ba-134">Element names in Visual Basic are case-insensitive.</span><span class="sxs-lookup"><span data-stu-id="b88ba-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="b88ba-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span><span class="sxs-lookup"><span data-stu-id="b88ba-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="b88ba-136">例如，它认为 `ABC` 和 `abc` 指的是同一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="b88ba-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="b88ba-137">However, the common language runtime (CLR) uses case-sensitive binding.</span><span class="sxs-lookup"><span data-stu-id="b88ba-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="b88ba-138">因此，当你生成程序集或 DLL 并使其可供其他程序集使用时，则名称将不再不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b88ba-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="b88ba-139">例如，如果你用名为 `ABC`的元素定义类，而其他程序集通过公共语言运行时使用你的类，则元素必须指的是 `ABC`。</span><span class="sxs-lookup"><span data-stu-id="b88ba-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="b88ba-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span><span class="sxs-lookup"><span data-stu-id="b88ba-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="b88ba-141">因此，发布程序集的更新版本时，不应该更改公共元素的字母大小写。</span><span class="sxs-lookup"><span data-stu-id="b88ba-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="b88ba-142">Names and Locales</span><span class="sxs-lookup"><span data-stu-id="b88ba-142">Names and Locales</span></span>  
 <span data-ttu-id="b88ba-143">Comparison of names is independent of locale.</span><span class="sxs-lookup"><span data-stu-id="b88ba-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="b88ba-144">If two names match in one locale, they are guaranteed to match in all locales.</span><span class="sxs-lookup"><span data-stu-id="b88ba-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88ba-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="b88ba-145">See also</span></span>

- [<span data-ttu-id="b88ba-146">已声明的元素</span><span class="sxs-lookup"><span data-stu-id="b88ba-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="b88ba-147">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="b88ba-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="b88ba-148">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="b88ba-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b88ba-149">语句</span><span class="sxs-lookup"><span data-stu-id="b88ba-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
