---
title: Namespace 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 7f6b976af7933b3895f6992488d2d1532a8fc2f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784132"
---
# <a name="namespace-statement"></a><span data-ttu-id="79ead-102">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="79ead-102">Namespace Statement</span></span>
<span data-ttu-id="79ead-103">声明命名空间的名称，并使遵循声明在该命名空间中进行编译的源代码。</span><span class="sxs-lookup"><span data-stu-id="79ead-103">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ead-104">语法</span><span class="sxs-lookup"><span data-stu-id="79ead-104">Syntax</span></span>  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="79ead-105">部件</span><span class="sxs-lookup"><span data-stu-id="79ead-105">Parts</span></span>  
 <span data-ttu-id="79ead-106">Global</span><span class="sxs-lookup"><span data-stu-id="79ead-106">Global</span></span>  
 <span data-ttu-id="79ead-107">可选。</span><span class="sxs-lookup"><span data-stu-id="79ead-107">Optional.</span></span> <span data-ttu-id="79ead-108">允许你定义你的项目根命名空间之外。</span><span class="sxs-lookup"><span data-stu-id="79ead-108">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="79ead-109">请参阅[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-109">See [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="79ead-110">必需。</span><span class="sxs-lookup"><span data-stu-id="79ead-110">Required.</span></span> <span data-ttu-id="79ead-111">用于标识命名空间的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="79ead-111">A unique name that identifies the namespace.</span></span> <span data-ttu-id="79ead-112">必须是有效的 Visual Basic 标识符。</span><span class="sxs-lookup"><span data-stu-id="79ead-112">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="79ead-113">有关详细信息，请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-113">For more information, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="79ead-114">可选。</span><span class="sxs-lookup"><span data-stu-id="79ead-114">Optional.</span></span> <span data-ttu-id="79ead-115">构成该命名空间的元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-115">Elements that make up the namespace.</span></span> <span data-ttu-id="79ead-116">这些包括但不限于枚举、 结构、 接口、 类、 模块、 委托和其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-116">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="79ead-117">终止`Namespace`块。</span><span class="sxs-lookup"><span data-stu-id="79ead-117">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ead-118">备注</span><span class="sxs-lookup"><span data-stu-id="79ead-118">Remarks</span></span>  
 <span data-ttu-id="79ead-119">命名空间用作组织的系统。</span><span class="sxs-lookup"><span data-stu-id="79ead-119">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="79ead-120">它们提供一种方法来进行分类并提供向其他程序和应用程序公开的编程元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-120">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="79ead-121">请注意，命名空间不是*类型*类或结构是在意义上，不能声明为具有一个命名空间的数据类型的编程元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-121">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="79ead-122">所有编程元素声明后`Namespace`语句属于该命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-122">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="79ead-123">Visual Basic 会继续将编译到最后一个声明的命名空间的元素，直到它遇到上述任何`End Namespace`语句或另一个`Namespace`语句。</span><span class="sxs-lookup"><span data-stu-id="79ead-123">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="79ead-124">如果已定义一个命名空间，甚至在项目之外，您可以向其添加编程元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-124">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="79ead-125">若要执行此操作，应使用`Namespace`语句，以指示 Visual Basic 将编译到该命名空间的元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-125">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="79ead-126">可以使用`Namespace`仅在文件或命名空间级别语句。</span><span class="sxs-lookup"><span data-stu-id="79ead-126">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="79ead-127">这意味着*声明上下文*的命名空间必须是源文件或另一个命名空间，且不能为类、 结构、 模块、 接口或过程。</span><span class="sxs-lookup"><span data-stu-id="79ead-127">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="79ead-128">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="79ead-129">您可以声明一个命名空间包含在另一个。</span><span class="sxs-lookup"><span data-stu-id="79ead-129">You can declare one namespace within another.</span></span> <span data-ttu-id="79ead-130">可以声明，但请记住，当其他代码访问最内部的命名空间中声明的元素，它必须使用包含嵌套层次结构中的所有命名空间名称的限定字符串的嵌套级别没有严格限制。</span><span class="sxs-lookup"><span data-stu-id="79ead-130">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="79ead-131">访问级别</span><span class="sxs-lookup"><span data-stu-id="79ead-131">Access Level</span></span>  
 <span data-ttu-id="79ead-132">命名空间均被视为如同它们具有`Public`访问级别。</span><span class="sxs-lookup"><span data-stu-id="79ead-132">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="79ead-133">从任意位置在同一项目中的代码、 其他引用该项目的项目和项目生成任何程序集，可以访问命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-133">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="79ead-134">在命名空间级别，这意味着命名空间中、 但在任何其他元素声明的编程元素可以具有`Public`或`Friend`访问。</span><span class="sxs-lookup"><span data-stu-id="79ead-134">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="79ead-135">如果未指定，使用此类的访问级别元素`Friend`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="79ead-135">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="79ead-136">可以在命名空间级别声明的元素包括类、 结构、 模块、 接口、 枚举和委托。</span><span class="sxs-lookup"><span data-stu-id="79ead-136">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="79ead-137">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-137">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="79ead-138">根 Namespace</span><span class="sxs-lookup"><span data-stu-id="79ead-138">Root Namespace</span></span>  
 <span data-ttu-id="79ead-139">在项目中的所有命名空间名称基于*根命名空间*。</span><span class="sxs-lookup"><span data-stu-id="79ead-139">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="79ead-140">Visual Studio 针对项目中的所有代码，将项目名称指定为默认根命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-140">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="79ead-141">例如，如果项目命名为 `Payroll`，则其编程元素属于命名空间 `Payroll`。</span><span class="sxs-lookup"><span data-stu-id="79ead-141">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="79ead-142">如果声明`Namespace funding`，该命名空间的完整名称是`Payroll.funding`。</span><span class="sxs-lookup"><span data-stu-id="79ead-142">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="79ead-143">如果你想要指定现有的命名空间中`Namespace`语句，如在泛型列表类示例中，可以将根命名空间设置为 null 值。</span><span class="sxs-lookup"><span data-stu-id="79ead-143">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="79ead-144">若要执行此操作，请单击**项目属性**从**项目**菜单，然后清除**根命名空间**条目，以便此框为空。</span><span class="sxs-lookup"><span data-stu-id="79ead-144">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="79ead-145">如果您没有不这样做在泛型列表类的示例中，将需要 Visual Basic 编译器`System.Collections.Generic`作为新项目中的命名空间`Payroll`，使用的完整名称`Payroll.System.Collections.Generic`。</span><span class="sxs-lookup"><span data-stu-id="79ead-145">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="79ead-146">或者，可以使用`Global`关键字来引用在项目外部定义的命名空间的元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-146">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="79ead-147">这样就可以保留你的项目名称作为根命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-147">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="79ead-148">这将减少无意中将编程元素以及现有命名空间的可能性。</span><span class="sxs-lookup"><span data-stu-id="79ead-148">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="79ead-149">有关详细信息，请参阅中的"全局关键字中完全限定名称"部分[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-149">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="79ead-150">`Global`还 Namespace 语句中使用关键字。</span><span class="sxs-lookup"><span data-stu-id="79ead-150">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="79ead-151">这将允许你定义项目根命名空间之外的命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-151">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="79ead-152">有关详细信息，请参阅中的"全局关键字在 Namespace 语句"一节[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="79ead-152">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="79ead-153">**故障排除。**</span><span class="sxs-lookup"><span data-stu-id="79ead-153">**Troubleshooting.**</span></span> <span data-ttu-id="79ead-154">根命名空间可能会导致意外的命名空间名称的串联。</span><span class="sxs-lookup"><span data-stu-id="79ead-154">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="79ead-155">如果在项目外部定义的命名空间的引用，Visual Basic 编译器可以 construe 它们作为根命名空间中的嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-155">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="79ead-156">在这种情况下，编译器无法识别已在外部命名空间中定义的任何类型。</span><span class="sxs-lookup"><span data-stu-id="79ead-156">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="79ead-157">若要避免此问题，请设置根命名空间为"根 Namespace，"中所述的 null 值，或使用`Global`关键字来访问外部命名空间的元素。</span><span class="sxs-lookup"><span data-stu-id="79ead-157">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="79ead-158">特性和修饰符</span><span class="sxs-lookup"><span data-stu-id="79ead-158">Attributes and Modifiers</span></span>  
 <span data-ttu-id="79ead-159">不能将特性应用到的命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-159">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="79ead-160">特性提供信息对程序集的元数据，这并无意义的源分类器，例如命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-160">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="79ead-161">不能应用到命名空间的任何访问或过程修饰符或任何其他修饰符。</span><span class="sxs-lookup"><span data-stu-id="79ead-161">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="79ead-162">由于它不是类型，这些修饰符不是有意义的。</span><span class="sxs-lookup"><span data-stu-id="79ead-162">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ead-163">示例</span><span class="sxs-lookup"><span data-stu-id="79ead-163">Example</span></span>  
 <span data-ttu-id="79ead-164">下面的示例声明两个命名空间，嵌套在另一个。</span><span class="sxs-lookup"><span data-stu-id="79ead-164">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a><span data-ttu-id="79ead-165">示例</span><span class="sxs-lookup"><span data-stu-id="79ead-165">Example</span></span>  
 <span data-ttu-id="79ead-166">下面的示例在单个行上声明多个嵌套的命名空间，它等效于前面的示例。</span><span class="sxs-lookup"><span data-stu-id="79ead-166">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="79ead-167">示例</span><span class="sxs-lookup"><span data-stu-id="79ead-167">Example</span></span>  
 <span data-ttu-id="79ead-168">以下示例将访问的上一示例中定义的类。</span><span class="sxs-lookup"><span data-stu-id="79ead-168">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="79ead-169">示例</span><span class="sxs-lookup"><span data-stu-id="79ead-169">Example</span></span>  
 <span data-ttu-id="79ead-170">下面的示例定义一个新的泛型列表类的框架，并将其添加到<xref:System.Collections.Generic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="79ead-170">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="79ead-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="79ead-171">See also</span></span>

- [<span data-ttu-id="79ead-172">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="79ead-172">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="79ead-173">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="79ead-173">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="79ead-174">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="79ead-174">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
