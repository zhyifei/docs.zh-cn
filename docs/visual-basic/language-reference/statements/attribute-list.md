---
title: "属性列表 (Visual Basic 中) |Microsoft 文档"
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
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 6aea239e2e0d8a266b8eb6ba2876fb109e077c46
ms.contentlocale: zh-cn
ms.lasthandoff: 05/15/2017

---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="eb6af-102">特性列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb6af-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="eb6af-103">指定要应用于声明的编程元素的属性。</span><span class="sxs-lookup"><span data-stu-id="eb6af-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="eb6af-104">用逗号分隔多个属性。</span><span class="sxs-lookup"><span data-stu-id="eb6af-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="eb6af-105">下面是一个属性的语法。</span><span class="sxs-lookup"><span data-stu-id="eb6af-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb6af-106">语法</span><span class="sxs-lookup"><span data-stu-id="eb6af-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="eb6af-107">部件</span><span class="sxs-lookup"><span data-stu-id="eb6af-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="eb6af-108">所需的应用的源代码文件开头的属性。</span><span class="sxs-lookup"><span data-stu-id="eb6af-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="eb6af-109">可以是[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)或[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6af-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="eb6af-110">必需。</span><span class="sxs-lookup"><span data-stu-id="eb6af-110">Required.</span></span> <span data-ttu-id="eb6af-111">属性名称。</span><span class="sxs-lookup"><span data-stu-id="eb6af-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="eb6af-112">可选。</span><span class="sxs-lookup"><span data-stu-id="eb6af-112">Optional.</span></span> <span data-ttu-id="eb6af-113">此属性的位置参数的列表。</span><span class="sxs-lookup"><span data-stu-id="eb6af-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="eb6af-114">用逗号分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="eb6af-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="eb6af-115">可选。</span><span class="sxs-lookup"><span data-stu-id="eb6af-115">Optional.</span></span> <span data-ttu-id="eb6af-116">此属性的变量或属性初始值设定项的列表。</span><span class="sxs-lookup"><span data-stu-id="eb6af-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="eb6af-117">用逗号分隔多个初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="eb6af-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb6af-118">备注</span><span class="sxs-lookup"><span data-stu-id="eb6af-118">Remarks</span></span>  
 <span data-ttu-id="eb6af-119">可以将一个或多个特性应用于几乎所有编程元素 （类型、 过程、 属性和等）。</span><span class="sxs-lookup"><span data-stu-id="eb6af-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="eb6af-120">属性出现在程序集的元数据，并且它们可以帮助您为您的代码添加批注或指定如何使用特定的编程元素。</span><span class="sxs-lookup"><span data-stu-id="eb6af-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="eb6af-121">您可以应用属性定义的 Visual Basic 和.NET Framework 中，并且可以定义您自己的属性。</span><span class="sxs-lookup"><span data-stu-id="eb6af-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="eb6af-122">有关何时使用属性的详细信息，请参阅[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6af-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="eb6af-123">属性名称的信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6af-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="eb6af-124">规则</span><span class="sxs-lookup"><span data-stu-id="eb6af-124">Rules</span></span>  
  
-   <span data-ttu-id="eb6af-125">**处的位置。**</span><span class="sxs-lookup"><span data-stu-id="eb6af-125">**Placement.**</span></span> <span data-ttu-id="eb6af-126">可以将特性应用于大多数已声明的编程元素。</span><span class="sxs-lookup"><span data-stu-id="eb6af-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="eb6af-127">若要将应用一个或多个属性，将放*特性块*元素声明的开头。</span><span class="sxs-lookup"><span data-stu-id="eb6af-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="eb6af-128">每个条目的属性列表中指定您要将应用的属性、 修饰符和参数将用于调用该属性。</span><span class="sxs-lookup"><span data-stu-id="eb6af-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="eb6af-129">**尖括号。**</span><span class="sxs-lookup"><span data-stu-id="eb6af-129">**Angle Brackets.**</span></span> <span data-ttu-id="eb6af-130">如果您提供的属性列表，则必须将其括在尖括号中 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="eb6af-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="eb6af-131">**声明的一部分。**</span><span class="sxs-lookup"><span data-stu-id="eb6af-131">**Part of the Declaration.**</span></span> <span data-ttu-id="eb6af-132">该属性必须是元素声明，而不是单独语句的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb6af-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="eb6af-133">您可以使用行继续符序列 (" `_`") 来扩展到多个源代码行上的声明语句。</span><span class="sxs-lookup"><span data-stu-id="eb6af-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="eb6af-134">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="eb6af-134">**Modifiers.**</span></span> <span data-ttu-id="eb6af-135">属性修饰符 (`Assembly`或`Module`) 需要在每个特性应用于源代码文件开头的编程元素上。</span><span class="sxs-lookup"><span data-stu-id="eb6af-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="eb6af-136">应用于不源文件中的开始处的元素特性不允许使用属性修饰符。</span><span class="sxs-lookup"><span data-stu-id="eb6af-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="eb6af-137">**参数。**</span><span class="sxs-lookup"><span data-stu-id="eb6af-137">**Arguments.**</span></span> <span data-ttu-id="eb6af-138">属性的所有位置参数必须优先任何变量或属性初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="eb6af-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb6af-139">示例</span><span class="sxs-lookup"><span data-stu-id="eb6af-139">Example</span></span>  
 <span data-ttu-id="eb6af-140">下面的示例应用<xref:System.Runtime.InteropServices.DllImportAttribute>属性的主干定义为`Function`过程。</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="eb6af-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 <span data-ttu-id="eb6af-141">[!code-vb[VbVbalrStatements #&1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb6af-141">[!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span></span>  
  
 <span data-ttu-id="eb6af-142"><xref:System.Runtime.InteropServices.DllImportAttribute>指示特性化的过程表示非托管动态链接库 (DLL) 中的入口点。</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="eb6af-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="eb6af-143">该属性提供了位置参数作为 DLL 的名称和作为变量的初始值设定项的其他信息。</span><span class="sxs-lookup"><span data-stu-id="eb6af-143">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6af-144">请参见</span><span class="sxs-lookup"><span data-stu-id="eb6af-144">See Also</span></span>  
 <span data-ttu-id="eb6af-145">[程序集](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="eb6af-145">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="eb6af-146"> [模块\<关键字&1;>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="eb6af-146"> [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="eb6af-147"> [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb6af-147"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="eb6af-148"> [如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="eb6af-148"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>

