---
title: 特性列表 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 35d031722a5eddd6adce5e32df62b86c500d305b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604064"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="bfc85-102">特性列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfc85-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="bfc85-103">指定要应用于声明的编程元素的属性。</span><span class="sxs-lookup"><span data-stu-id="bfc85-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="bfc85-104">用逗号分隔多个属性。</span><span class="sxs-lookup"><span data-stu-id="bfc85-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="bfc85-105">下面是一个属性的语法。</span><span class="sxs-lookup"><span data-stu-id="bfc85-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfc85-106">语法</span><span class="sxs-lookup"><span data-stu-id="bfc85-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bfc85-107">部件</span><span class="sxs-lookup"><span data-stu-id="bfc85-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="bfc85-108">所需的应用的源代码文件开头的属性。</span><span class="sxs-lookup"><span data-stu-id="bfc85-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="bfc85-109">可以是[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)或[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc85-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="bfc85-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="bfc85-110">Required.</span></span> <span data-ttu-id="bfc85-111">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="bfc85-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="bfc85-112">可选。</span><span class="sxs-lookup"><span data-stu-id="bfc85-112">Optional.</span></span> <span data-ttu-id="bfc85-113">此特性的位置自变量的列表。</span><span class="sxs-lookup"><span data-stu-id="bfc85-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="bfc85-114">用逗号分隔多个自变量。</span><span class="sxs-lookup"><span data-stu-id="bfc85-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="bfc85-115">可选。</span><span class="sxs-lookup"><span data-stu-id="bfc85-115">Optional.</span></span> <span data-ttu-id="bfc85-116">此属性的变量或属性初始值设定项的列表。</span><span class="sxs-lookup"><span data-stu-id="bfc85-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="bfc85-117">用逗号分隔多个初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="bfc85-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfc85-118">备注</span><span class="sxs-lookup"><span data-stu-id="bfc85-118">Remarks</span></span>  
 <span data-ttu-id="bfc85-119">你可以将一个或多个特性应用于几乎任何编程元素 （类型、 过程、 属性和等）。</span><span class="sxs-lookup"><span data-stu-id="bfc85-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="bfc85-120">特性显示在程序集的元数据，并且它们可以帮助您批注代码或指定如何使用特定的编程元素。</span><span class="sxs-lookup"><span data-stu-id="bfc85-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="bfc85-121">你可以应用 Visual Basic 和.NET Framework 中，通过定义属性，你可以定义你自己的特性。</span><span class="sxs-lookup"><span data-stu-id="bfc85-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="bfc85-122">有关何时使用属性的详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc85-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="bfc85-123">属性名称的信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc85-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bfc85-124">规则</span><span class="sxs-lookup"><span data-stu-id="bfc85-124">Rules</span></span>  
  
-   <span data-ttu-id="bfc85-125">**放置。**</span><span class="sxs-lookup"><span data-stu-id="bfc85-125">**Placement.**</span></span> <span data-ttu-id="bfc85-126">可以将特性应用于大多数已声明的编程元素。</span><span class="sxs-lookup"><span data-stu-id="bfc85-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="bfc85-127">若要应用一个或多个属性，你放置*特性块*元素声明的开头。</span><span class="sxs-lookup"><span data-stu-id="bfc85-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="bfc85-128">属性列表中的每个项指定你想要应用的属性、 修饰符和自变量将为此调用属性。</span><span class="sxs-lookup"><span data-stu-id="bfc85-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="bfc85-129">**命令的尖括号。**</span><span class="sxs-lookup"><span data-stu-id="bfc85-129">**Angle Brackets.**</span></span> <span data-ttu-id="bfc85-130">如果你提供的属性列表，你必须请将其括在尖括号中 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="bfc85-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="bfc85-131">**声明的一部分。**</span><span class="sxs-lookup"><span data-stu-id="bfc85-131">**Part of the Declaration.**</span></span> <span data-ttu-id="bfc85-132">该属性必须是元素声明，而不是单独的语句的一部分。</span><span class="sxs-lookup"><span data-stu-id="bfc85-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="bfc85-133">你可以使用行继续序列 (" `_`") 来扩展到多个源代码行上的声明语句。</span><span class="sxs-lookup"><span data-stu-id="bfc85-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="bfc85-134">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="bfc85-134">**Modifiers.**</span></span> <span data-ttu-id="bfc85-135">特性修饰符 (`Assembly`或`Module`) 上应用到编程元素中的源代码文件开头的每个属性必需的。</span><span class="sxs-lookup"><span data-stu-id="bfc85-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="bfc85-136">应用于未在源文件的开头的元素的特性不允许出现特性修饰符。</span><span class="sxs-lookup"><span data-stu-id="bfc85-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="bfc85-137">**自变量。**</span><span class="sxs-lookup"><span data-stu-id="bfc85-137">**Arguments.**</span></span> <span data-ttu-id="bfc85-138">属性的所有位置自变量必须位于任何变量或属性初始值设定项之前。</span><span class="sxs-lookup"><span data-stu-id="bfc85-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfc85-139">示例</span><span class="sxs-lookup"><span data-stu-id="bfc85-139">Example</span></span>  
 <span data-ttu-id="bfc85-140">下面的示例应用<xref:System.Runtime.InteropServices.DllImportAttribute>属性设为的主干定义`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="bfc85-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="bfc85-141"><xref:System.Runtime.InteropServices.DllImportAttribute> 指示特性化的过程表示非托管动态链接库 (DLL) 中的入口点。</span><span class="sxs-lookup"><span data-stu-id="bfc85-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="bfc85-142">该属性提供位置自变量作为 DLL 的名称和作为变量初始值设定项的其他信息。</span><span class="sxs-lookup"><span data-stu-id="bfc85-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc85-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfc85-143">See Also</span></span>  
 [<span data-ttu-id="bfc85-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="bfc85-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="bfc85-145">Module \<关键字></span><span class="sxs-lookup"><span data-stu-id="bfc85-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="bfc85-146">属性概述</span><span class="sxs-lookup"><span data-stu-id="bfc85-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="bfc85-147">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="bfc85-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
