---
title: "声明的元素名称 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 899bcb2ecc8f5c07fdf4592e15827ff67f55c136
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="efe91-102">已声明的元素名称 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efe91-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="efe91-103">每个已声明的元素有一个名称，也称为*标识符*，这是该代码使用来引用它。</span><span class="sxs-lookup"><span data-stu-id="efe91-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="efe91-104">规则</span><span class="sxs-lookup"><span data-stu-id="efe91-104">Rules</span></span>  
 <span data-ttu-id="efe91-105">中的元素名称[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]必须遵守以下规则︰</span><span class="sxs-lookup"><span data-stu-id="efe91-105">An element name in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="efe91-106">它必须以字母字符或下划线开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="efe91-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="efe91-107">它必须仅包含字母字符、 十进制数字和下划线。</span><span class="sxs-lookup"><span data-stu-id="efe91-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="efe91-108">如果以下划线开头，它必须包含至少一个字母字符或十进制数字类别。</span><span class="sxs-lookup"><span data-stu-id="efe91-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="efe91-109">它不得超过 1023年个字符长。</span><span class="sxs-lookup"><span data-stu-id="efe91-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="efe91-110">1023 个字符的长度限制也适用于整个字符串的完全限定的名称，如`outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`。</span><span class="sxs-lookup"><span data-stu-id="efe91-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="efe91-111">下面的示例演示一些有效的元素名称。</span><span class="sxs-lookup"><span data-stu-id="efe91-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="efe91-112">下面的示例演示一些无效的元素名称。</span><span class="sxs-lookup"><span data-stu-id="efe91-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="efe91-113">第一个仅包含一个下划线、 十进制数字，以开始第二个和第三个包含无效字符 （$）。</span><span class="sxs-lookup"><span data-stu-id="efe91-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="efe91-114">元素名称以下划线开头 (`_`) 不属于[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，因此符合 cls 的代码不能使用一个组件，它定义了此类名称。</span><span class="sxs-lookup"><span data-stu-id="efe91-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="efe91-115">但是，元素名称中的任何其他位置的下划线是符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="efe91-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="efe91-116">名称长度原则</span><span class="sxs-lookup"><span data-stu-id="efe91-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="efe91-117">在实践中，您的名称应尽可能短时仍然能够清楚地标识该元素的特性。</span><span class="sxs-lookup"><span data-stu-id="efe91-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="efe91-118">这可以提高您的代码的可读性并降低行长度和源文件大小。</span><span class="sxs-lookup"><span data-stu-id="efe91-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="efe91-119">另一方面，您的名称不应为太短，它不会不充分描述的元素表示以及您的代码如何使用它。</span><span class="sxs-lookup"><span data-stu-id="efe91-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="efe91-120">这是代码的重要的可读性。</span><span class="sxs-lookup"><span data-stu-id="efe91-120">This is important for the readability of your code.</span></span> <span data-ttu-id="efe91-121">如果其他人正试图了解它，或者如果您自己正在寻求通过它您撰写后很长时间，适当元素名称可以节省相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="efe91-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="efe91-122">转义的名称</span><span class="sxs-lookup"><span data-stu-id="efe91-122">Escaped Names</span></span>  
 <span data-ttu-id="efe91-123">通常情况下，元素名称必须与任何不匹配的保留的关键字[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，如`Case`或`Friend`。</span><span class="sxs-lookup"><span data-stu-id="efe91-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="efe91-124">但是，可以定义*转义名称*，这由方括号括起来 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="efe91-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="efe91-125">转义的名称可以匹配任何[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]关键字，因为括号消除了不明确性。</span><span class="sxs-lookup"><span data-stu-id="efe91-125">An escaped name can match any [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="efe91-126">在更高版本在代码中引用的名称时，还可以使用方括号。</span><span class="sxs-lookup"><span data-stu-id="efe91-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="efe91-127">通常情况下，应使用转义的名称时，才︰</span><span class="sxs-lookup"><span data-stu-id="efe91-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="efe91-128">您的代码已从早期版本迁移[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，没有保留关键字用作名称; 或</span><span class="sxs-lookup"><span data-stu-id="efe91-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="efe91-129">您正在使用中的给定的关键字不保留的另一种语言编写的代码。</span><span class="sxs-lookup"><span data-stu-id="efe91-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="efe91-130">否则，应考虑重命名该元素，如果其名称与关键字冲突。</span><span class="sxs-lookup"><span data-stu-id="efe91-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="efe91-131">集成的开发环境 (IDE) 提供了轻松执行此操作。</span><span class="sxs-lookup"><span data-stu-id="efe91-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="efe91-132">有关详细信息，请参阅[重构](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb)。</span><span class="sxs-lookup"><span data-stu-id="efe91-132">For more information, see [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="efe91-133">在名称中的区分大小写</span><span class="sxs-lookup"><span data-stu-id="efe91-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="efe91-134">中的元素名称[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="efe91-134">Element names in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] are case-insensitive.</span></span> <span data-ttu-id="efe91-135">这意味着当编译器在比较两个不同的字母大小写的名称，将其解释为相同的名称。</span><span class="sxs-lookup"><span data-stu-id="efe91-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="efe91-136">例如，它认为 `ABC` 和 `abc` 指的是同一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="efe91-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="efe91-137">但是，公共语言运行时 (CLR) 使用区分大小写的绑定。</span><span class="sxs-lookup"><span data-stu-id="efe91-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="efe91-138">因此，当你生成程序集或 DLL 并使其可供其他程序集使用时，则名称将不再不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="efe91-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="efe91-139">例如，如果你用名为 `ABC`的元素定义类，而其他程序集通过公共语言运行时使用你的类，则元素必须指的是 `ABC`。</span><span class="sxs-lookup"><span data-stu-id="efe91-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="efe91-140">如果以后要重新编译该类并将更改元素的名称传递给`abc`，则使用您的类的其他程序集将无法再访问该元素。</span><span class="sxs-lookup"><span data-stu-id="efe91-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="efe91-141">因此，发布程序集的更新版本时，不应该更改公共元素的字母大小写。</span><span class="sxs-lookup"><span data-stu-id="efe91-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="efe91-142">名称和区域设置</span><span class="sxs-lookup"><span data-stu-id="efe91-142">Names and Locales</span></span>  
 <span data-ttu-id="efe91-143">名称的比较是独立于区域设置。</span><span class="sxs-lookup"><span data-stu-id="efe91-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="efe91-144">如果在一个区域设置中匹配两个名称，可确保在所有区域设置匹配。</span><span class="sxs-lookup"><span data-stu-id="efe91-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe91-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efe91-145">See Also</span></span>  
 <span data-ttu-id="efe91-146">[已声明的元素](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span><span class="sxs-lookup"><span data-stu-id="efe91-146">[Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span></span>  
<span data-ttu-id="efe91-147"> [已声明的元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="efe91-147"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="efe91-148"> [对已声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="efe91-148"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="efe91-149"> [语句](../../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="efe91-149"> [Statements](../../../../visual-basic/language-reference/statements/index.md)</span></span>
