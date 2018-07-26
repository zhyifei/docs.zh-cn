---
title: 特性列表 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 23f2004a34f5d6dc27c8263f6e66642dd32c6a5f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936924"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="ecf91-102">特性列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecf91-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="ecf91-103">指定要应用于声明的编程元素的特性。</span><span class="sxs-lookup"><span data-stu-id="ecf91-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="ecf91-104">用逗号分隔多个属性。</span><span class="sxs-lookup"><span data-stu-id="ecf91-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="ecf91-105">下面是一个属性的语法。</span><span class="sxs-lookup"><span data-stu-id="ecf91-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf91-106">语法</span><span class="sxs-lookup"><span data-stu-id="ecf91-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ecf91-107">部件</span><span class="sxs-lookup"><span data-stu-id="ecf91-107">Parts</span></span>  
|||
|---|---|
|`attributemodifier`|<span data-ttu-id="ecf91-108">所需应用的源代码文件开头的属性。</span><span class="sxs-lookup"><span data-stu-id="ecf91-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="ecf91-109">可以是[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)或[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf91-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="ecf91-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="ecf91-110">Required.</span></span> <span data-ttu-id="ecf91-111">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ecf91-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="ecf91-112">可选。</span><span class="sxs-lookup"><span data-stu-id="ecf91-112">Optional.</span></span> <span data-ttu-id="ecf91-113">为此特性的位置自变量的列表。</span><span class="sxs-lookup"><span data-stu-id="ecf91-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="ecf91-114">由逗号分隔多个自变量。</span><span class="sxs-lookup"><span data-stu-id="ecf91-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="ecf91-115">可选。</span><span class="sxs-lookup"><span data-stu-id="ecf91-115">Optional.</span></span> <span data-ttu-id="ecf91-116">此属性的变量或属性初始值设定项的列表。</span><span class="sxs-lookup"><span data-stu-id="ecf91-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="ecf91-117">由逗号分隔多个初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="ecf91-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="ecf91-118">备注</span><span class="sxs-lookup"><span data-stu-id="ecf91-118">Remarks</span></span>  
 <span data-ttu-id="ecf91-119">可以将一个或多个特性应用于几乎任何编程元素 （类型、 过程、 属性等）。</span><span class="sxs-lookup"><span data-stu-id="ecf91-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="ecf91-120">属性出现在程序集的元数据，并且它们可以帮助您批注代码，或指定如何使用特定的编程元素。</span><span class="sxs-lookup"><span data-stu-id="ecf91-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="ecf91-121">您可以应用由 Visual Basic 和.NET Framework 中，定义的特性，可以定义自己的属性。</span><span class="sxs-lookup"><span data-stu-id="ecf91-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="ecf91-122">有关何时使用属性的详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf91-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="ecf91-123">属性名称的信息，请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf91-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ecf91-124">规则</span><span class="sxs-lookup"><span data-stu-id="ecf91-124">Rules</span></span>  
  
-   <span data-ttu-id="ecf91-125">**放置。**</span><span class="sxs-lookup"><span data-stu-id="ecf91-125">**Placement.**</span></span> <span data-ttu-id="ecf91-126">可以将特性应用于最声明的编程元素。</span><span class="sxs-lookup"><span data-stu-id="ecf91-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="ecf91-127">若要将应用一个或多个属性，将置于*特性块*元素声明的开头。</span><span class="sxs-lookup"><span data-stu-id="ecf91-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="ecf91-128">在属性列表中的每个条目指定你想要将应用，一个属性、 修饰符和自变量将用于此属性的调用。</span><span class="sxs-lookup"><span data-stu-id="ecf91-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="ecf91-129">**尖括号。**</span><span class="sxs-lookup"><span data-stu-id="ecf91-129">**Angle Brackets.**</span></span> <span data-ttu-id="ecf91-130">如果提供的属性列表，则必须将其括在尖括号中 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="ecf91-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="ecf91-131">**声明的一部分。**</span><span class="sxs-lookup"><span data-stu-id="ecf91-131">**Part of the Declaration.**</span></span> <span data-ttu-id="ecf91-132">该属性必须是元素声明，而不是单独语句的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecf91-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="ecf91-133">您可以使用行继续符序列 (" `_`") 来扩展到多个源代码行上的声明语句。</span><span class="sxs-lookup"><span data-stu-id="ecf91-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="ecf91-134">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="ecf91-134">**Modifiers.**</span></span> <span data-ttu-id="ecf91-135">特性修饰符 (`Assembly`或`Module`) 上应用到编程元素中的源文件开头的每个属性必需的。</span><span class="sxs-lookup"><span data-stu-id="ecf91-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="ecf91-136">应用于不在源文件开头的元素的特性不允许出现特性修饰符。</span><span class="sxs-lookup"><span data-stu-id="ecf91-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="ecf91-137">**自变量。**</span><span class="sxs-lookup"><span data-stu-id="ecf91-137">**Arguments.**</span></span> <span data-ttu-id="ecf91-138">属性的所有位置参数必须位于任何变量或属性初始值设定项之前。</span><span class="sxs-lookup"><span data-stu-id="ecf91-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecf91-139">示例</span><span class="sxs-lookup"><span data-stu-id="ecf91-139">Example</span></span>  
 <span data-ttu-id="ecf91-140">下面的示例应用<xref:System.Runtime.InteropServices.DllImportAttribute>属性的主干定义为`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="ecf91-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="ecf91-141"><xref:System.Runtime.InteropServices.DllImportAttribute> 指示特性化的过程表示非托管动态链接库 (DLL) 中的入口点。</span><span class="sxs-lookup"><span data-stu-id="ecf91-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="ecf91-142">该属性提供的 DLL 名称作为位置自变量和变量初始值设定项与其他信息。</span><span class="sxs-lookup"><span data-stu-id="ecf91-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf91-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf91-143">See Also</span></span>  
 [<span data-ttu-id="ecf91-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="ecf91-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="ecf91-145">Module \<关键字></span><span class="sxs-lookup"><span data-stu-id="ecf91-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="ecf91-146">属性概述</span><span class="sxs-lookup"><span data-stu-id="ecf91-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="ecf91-147">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="ecf91-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
