---
title: Imports 语句-.NET Namespace 和类型 (Visual Basic)
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
ms.openlocfilehash: 4574bab62ca6d095ab66c17bf186da5f3d79bfb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826517"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="40643-102">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="40643-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="40643-103">使类型名称而无需命名空间限定引用。</span><span class="sxs-lookup"><span data-stu-id="40643-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40643-104">语法</span><span class="sxs-lookup"><span data-stu-id="40643-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="40643-105">部件</span><span class="sxs-lookup"><span data-stu-id="40643-105">Parts</span></span>  
  
|<span data-ttu-id="40643-106">术语</span><span class="sxs-lookup"><span data-stu-id="40643-106">Term</span></span>|<span data-ttu-id="40643-107">定义</span><span class="sxs-lookup"><span data-stu-id="40643-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="40643-108">可选。</span><span class="sxs-lookup"><span data-stu-id="40643-108">Optional.</span></span> <span data-ttu-id="40643-109">*导入别名*或名称的代码可以指`namespace`而不是完全限定字符串。</span><span class="sxs-lookup"><span data-stu-id="40643-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="40643-110">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="40643-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="40643-111">必需。</span><span class="sxs-lookup"><span data-stu-id="40643-111">Required.</span></span> <span data-ttu-id="40643-112">正在导入的命名空间完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="40643-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="40643-113">可以命名空间的字符串嵌套到任意级别。</span><span class="sxs-lookup"><span data-stu-id="40643-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="40643-114">可选。</span><span class="sxs-lookup"><span data-stu-id="40643-114">Optional.</span></span> <span data-ttu-id="40643-115">命名空间中声明的编程元素的名称。</span><span class="sxs-lookup"><span data-stu-id="40643-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="40643-116">可以是任何容器元素。</span><span class="sxs-lookup"><span data-stu-id="40643-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40643-117">备注</span><span class="sxs-lookup"><span data-stu-id="40643-117">Remarks</span></span>  
 <span data-ttu-id="40643-118">`Imports`语句启用直接引用给定命名空间中包含的类型。</span><span class="sxs-lookup"><span data-stu-id="40643-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="40643-119">你可以提供单个命名空间名称或嵌套的命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="40643-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="40643-120">每个嵌套的命名空间从下一步的更高级别命名空间用句点隔开 (`.`)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="40643-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="40643-121">每个源文件可以包含任意数量的`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="40643-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="40643-122">这些必须遵循的任何选项声明，如`Option Strict`语句，并且它们必须编程元素位于任何声明之前，如`Module`或`Class`语句。</span><span class="sxs-lookup"><span data-stu-id="40643-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="40643-123">可以使用`Imports`仅在文件级别。</span><span class="sxs-lookup"><span data-stu-id="40643-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="40643-124">这意味着导入声明上下文必须是源文件，且不能为命名空间、 类、 结构、 模块、 接口、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="40643-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="40643-125">请注意，`Imports`语句不会将元素从其他项目和程序集提供给你的项目。</span><span class="sxs-lookup"><span data-stu-id="40643-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="40643-126">导入不会替代设置的引用。</span><span class="sxs-lookup"><span data-stu-id="40643-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="40643-127">而只会删除需要限定已可供你的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="40643-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="40643-128">详细信息，请参阅"导入包含元素"中[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="40643-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40643-129">您可以定义隐式`Imports`通过使用语句[引用页上，项目设计器 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="40643-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="40643-130">有关详细信息，请参阅[如何：添加或删除导入命名空间 (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="40643-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="40643-131">导入别名</span><span class="sxs-lookup"><span data-stu-id="40643-131">Import Aliases</span></span>  
 <span data-ttu-id="40643-132">*导入别名*定义命名空间或类型的别名。</span><span class="sxs-lookup"><span data-stu-id="40643-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="40643-133">需要使用一个或多个命名空间中声明了一个同名的项时，导入别名是非常有用。</span><span class="sxs-lookup"><span data-stu-id="40643-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="40643-134">详细信息和示例，请参阅"符合条件的元素名称"中[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="40643-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="40643-135">不应声明在模块级别具有相同的名称成员`aliasname`。</span><span class="sxs-lookup"><span data-stu-id="40643-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="40643-136">如果这样做，Visual Basic 编译器将使用`aliasname`仅对声明的成员且不能将其识别为某个导入别名。</span><span class="sxs-lookup"><span data-stu-id="40643-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="40643-137">尽管用于声明以导入别名的语法类似的用于导入 XML 命名空间前缀，则结果将不同。</span><span class="sxs-lookup"><span data-stu-id="40643-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="40643-138">导入别名可以用作在代码中，表达式，而 XML 命名空间前缀可以用于只能在 XML 文本或 XML 轴属性中作为前缀限定的元素或属性名称。</span><span class="sxs-lookup"><span data-stu-id="40643-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="40643-139">元素名称</span><span class="sxs-lookup"><span data-stu-id="40643-139">Element Names</span></span>  
 <span data-ttu-id="40643-140">如果提供`element`，则它必须表示*容器元素*，也就是说，可以包含其他元素的编程元素。</span><span class="sxs-lookup"><span data-stu-id="40643-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="40643-141">容器元素包括类、 结构、 模块、 接口和枚举。</span><span class="sxs-lookup"><span data-stu-id="40643-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="40643-142">提供的元素的作用域`Imports`语句取决于是否指定`element`。</span><span class="sxs-lookup"><span data-stu-id="40643-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="40643-143">如果仅指定`namespace`，所有具有唯一名为该命名空间的成员和该命名空间中的容器元素的成员，是无需限定即可。</span><span class="sxs-lookup"><span data-stu-id="40643-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="40643-144">如果同时指定`namespace`和`element`，只有该元素的成员是无需限定即可。</span><span class="sxs-lookup"><span data-stu-id="40643-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40643-145">示例</span><span class="sxs-lookup"><span data-stu-id="40643-145">Example</span></span>  
 <span data-ttu-id="40643-146">下面的示例通过使用在 C:\ 目录中返回的所有文件夹<xref:System.IO.DirectoryInfo>类。</span><span class="sxs-lookup"><span data-stu-id="40643-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="40643-147">没有代码`Imports`语句的文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="40643-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="40643-148">因此， `DirectoryInfo`， <xref:System.Text.StringBuilder>，和<xref:Microsoft.VisualBasic.ControlChars.CrLf>所有完全限定的命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="40643-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="40643-149">示例</span><span class="sxs-lookup"><span data-stu-id="40643-149">Example</span></span>  
 <span data-ttu-id="40643-150">下面的示例包括`Imports`引用的命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="40643-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="40643-151">因此，类型不需要用命名空间加以完全限定。</span><span class="sxs-lookup"><span data-stu-id="40643-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="40643-152">示例</span><span class="sxs-lookup"><span data-stu-id="40643-152">Example</span></span>  
 <span data-ttu-id="40643-153">下面的示例包括`Imports`为被引用的命名空间创建别名的语句。</span><span class="sxs-lookup"><span data-stu-id="40643-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="40643-154">类型别名进行限定。</span><span class="sxs-lookup"><span data-stu-id="40643-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="40643-155">示例</span><span class="sxs-lookup"><span data-stu-id="40643-155">Example</span></span>  
 <span data-ttu-id="40643-156">下面的示例包括`Imports`语句创建引用类型的别名。</span><span class="sxs-lookup"><span data-stu-id="40643-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="40643-157">使用别名来指定的类型。</span><span class="sxs-lookup"><span data-stu-id="40643-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="40643-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="40643-158">See also</span></span>

- [<span data-ttu-id="40643-159">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="40643-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="40643-160">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="40643-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="40643-161">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="40643-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="40643-162">Imports 语句（XML 命名空间）</span><span class="sxs-lookup"><span data-stu-id="40643-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="40643-163">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="40643-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
