---
title: Imports 语句-.NET 命名空间和类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912392"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="96d2c-102">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="96d2c-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="96d2c-103">允许引用类型名称, 而无需命名空间限定。</span><span class="sxs-lookup"><span data-stu-id="96d2c-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d2c-104">语法</span><span class="sxs-lookup"><span data-stu-id="96d2c-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="96d2c-105">部件</span><span class="sxs-lookup"><span data-stu-id="96d2c-105">Parts</span></span>  
  
|<span data-ttu-id="96d2c-106">术语</span><span class="sxs-lookup"><span data-stu-id="96d2c-106">Term</span></span>|<span data-ttu-id="96d2c-107">定义</span><span class="sxs-lookup"><span data-stu-id="96d2c-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="96d2c-108">可选。</span><span class="sxs-lookup"><span data-stu-id="96d2c-108">Optional.</span></span> <span data-ttu-id="96d2c-109">*导入别名*或代码可以引用`namespace`的名称, 而不是完全限定字符串。</span><span class="sxs-lookup"><span data-stu-id="96d2c-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="96d2c-110">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="96d2c-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="96d2c-111">必需。</span><span class="sxs-lookup"><span data-stu-id="96d2c-111">Required.</span></span> <span data-ttu-id="96d2c-112">要导入的命名空间的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="96d2c-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="96d2c-113">可以是嵌套到任何级别的命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="96d2c-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="96d2c-114">可选。</span><span class="sxs-lookup"><span data-stu-id="96d2c-114">Optional.</span></span> <span data-ttu-id="96d2c-115">命名空间中声明的编程元素的名称。</span><span class="sxs-lookup"><span data-stu-id="96d2c-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="96d2c-116">可以是任何容器元素。</span><span class="sxs-lookup"><span data-stu-id="96d2c-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96d2c-117">备注</span><span class="sxs-lookup"><span data-stu-id="96d2c-117">Remarks</span></span>  
 <span data-ttu-id="96d2c-118">`Imports`语句允许直接引用给定命名空间中包含的类型。</span><span class="sxs-lookup"><span data-stu-id="96d2c-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="96d2c-119">您可以提供单个命名空间名称或嵌套命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="96d2c-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="96d2c-120">每个嵌套命名空间都用句点 (`.`) 从下一个更高的级别命名空间中分离, 如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="96d2c-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="96d2c-121">每个源文件可以包含任意多`Imports`个语句。</span><span class="sxs-lookup"><span data-stu-id="96d2c-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="96d2c-122">它们必须遵循任何选项声明, 如`Option Strict`语句, 它们必须位于任何编程元素声明 ( `Module`如或`Class`语句) 之前。</span><span class="sxs-lookup"><span data-stu-id="96d2c-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="96d2c-123">只能在文件`Imports`级别使用。</span><span class="sxs-lookup"><span data-stu-id="96d2c-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="96d2c-124">这意味着, 用于导入的声明上下文必须是一个源文件, 而不能是命名空间、类、结构、模块、接口、过程或块。</span><span class="sxs-lookup"><span data-stu-id="96d2c-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="96d2c-125">请注意, `Imports`该语句不会使其他项目和程序集中的元素可用于您的项目。</span><span class="sxs-lookup"><span data-stu-id="96d2c-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="96d2c-126">导入不会替代设置引用。</span><span class="sxs-lookup"><span data-stu-id="96d2c-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="96d2c-127">它只是不再需要限定已可用于你的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="96d2c-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="96d2c-128">有关详细信息, 请参阅对已[声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)中的 "导入包含元素"。</span><span class="sxs-lookup"><span data-stu-id="96d2c-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96d2c-129">您可以使用 " `Imports` [引用" 页 ("项目设计器")](/visualstudio/ide/reference/references-page-project-designer-visual-basic)定义隐式语句 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="96d2c-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="96d2c-130">有关详细信息，请参阅[如何：添加或删除导入的命名空间](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)(Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="96d2c-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="96d2c-131">导入别名</span><span class="sxs-lookup"><span data-stu-id="96d2c-131">Import Aliases</span></span>  
 <span data-ttu-id="96d2c-132">*导入别名*定义命名空间或类型的别名。</span><span class="sxs-lookup"><span data-stu-id="96d2c-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="96d2c-133">如果需要使用一个或多个命名空间中声明的同名项, 则导入别名非常有用。</span><span class="sxs-lookup"><span data-stu-id="96d2c-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="96d2c-134">有关详细信息和示例, 请参阅对已[声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)中的 "限定元素名称"。</span><span class="sxs-lookup"><span data-stu-id="96d2c-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="96d2c-135">不应在模块级别使用与相同的名称`aliasname`声明成员。</span><span class="sxs-lookup"><span data-stu-id="96d2c-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="96d2c-136">如果这样做, 则 Visual Basic 编译器仅`aliasname`对已声明的成员使用, 而不再将其识别为导入别名。</span><span class="sxs-lookup"><span data-stu-id="96d2c-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="96d2c-137">尽管用于声明导入别名的语法与用于导入 XML 命名空间前缀的语法类似, 但结果不同。</span><span class="sxs-lookup"><span data-stu-id="96d2c-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="96d2c-138">导入别名可用作代码中的表达式, 而 XML 命名空间前缀只能在 XML 文本或 XML 轴属性中用作限定元素或属性名的前缀。</span><span class="sxs-lookup"><span data-stu-id="96d2c-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="96d2c-139">元素名称</span><span class="sxs-lookup"><span data-stu-id="96d2c-139">Element Names</span></span>  
 <span data-ttu-id="96d2c-140">如果提供`element`, 则它必须表示一个*容器元素*, 即一个可以包含其他元素的编程元素。</span><span class="sxs-lookup"><span data-stu-id="96d2c-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="96d2c-141">容器元素包括类、结构、模块、接口和枚举。</span><span class="sxs-lookup"><span data-stu-id="96d2c-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="96d2c-142">`Imports`语句提供的元素的作用域取决于您是否指定`element`了。</span><span class="sxs-lookup"><span data-stu-id="96d2c-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="96d2c-143">如果仅`namespace`指定, 则该命名空间的所有唯一命名的成员以及该命名空间内的容器元素的成员均可使用而无需进行限定。</span><span class="sxs-lookup"><span data-stu-id="96d2c-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="96d2c-144">如果同时`namespace`指定和`element`, 则仅可使用该元素的成员而无需进行限定。</span><span class="sxs-lookup"><span data-stu-id="96d2c-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96d2c-145">示例</span><span class="sxs-lookup"><span data-stu-id="96d2c-145">Example</span></span>  
 <span data-ttu-id="96d2c-146">下面的示例返回 C:\ 中的所有文件夹<xref:System.IO.DirectoryInfo>目录。</span><span class="sxs-lookup"><span data-stu-id="96d2c-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="96d2c-147">该代码的顶部`Imports`没有语句。</span><span class="sxs-lookup"><span data-stu-id="96d2c-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="96d2c-148">因此, `DirectoryInfo`、 <xref:System.Text.StringBuilder>和<xref:Microsoft.VisualBasic.ControlChars.CrLf>引用均由命名空间完全限定。</span><span class="sxs-lookup"><span data-stu-id="96d2c-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="96d2c-149">示例</span><span class="sxs-lookup"><span data-stu-id="96d2c-149">Example</span></span>  
 <span data-ttu-id="96d2c-150">下面的示例包含`Imports`引用的命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="96d2c-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="96d2c-151">因此, 无需使用命名空间完全限定类型。</span><span class="sxs-lookup"><span data-stu-id="96d2c-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="96d2c-152">示例</span><span class="sxs-lookup"><span data-stu-id="96d2c-152">Example</span></span>  
 <span data-ttu-id="96d2c-153">下面的示例包含`Imports`为被引用命名空间创建别名的语句。</span><span class="sxs-lookup"><span data-stu-id="96d2c-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="96d2c-154">类型是用别名限定的。</span><span class="sxs-lookup"><span data-stu-id="96d2c-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="96d2c-155">示例</span><span class="sxs-lookup"><span data-stu-id="96d2c-155">Example</span></span>  
 <span data-ttu-id="96d2c-156">下面的示例包含`Imports`为引用的类型创建别名的语句。</span><span class="sxs-lookup"><span data-stu-id="96d2c-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="96d2c-157">别名用于指定类型。</span><span class="sxs-lookup"><span data-stu-id="96d2c-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="96d2c-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="96d2c-158">See also</span></span>

- [<span data-ttu-id="96d2c-159">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="96d2c-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="96d2c-160">Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="96d2c-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="96d2c-161">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="96d2c-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="96d2c-162">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="96d2c-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="96d2c-163">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="96d2c-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
