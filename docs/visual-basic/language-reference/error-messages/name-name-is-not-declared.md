---
title: 名称“<name>”未声明
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260121"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="6b121-102">名称\<名称 > 未声明</span><span class="sxs-lookup"><span data-stu-id="6b121-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="6b121-103">语句引用的编程元素，但编译器找不到具有相同名称的元素。</span><span class="sxs-lookup"><span data-stu-id="6b121-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="6b121-104">**错误 ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="6b121-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b121-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6b121-105">To correct this error</span></span>  
  
1. <span data-ttu-id="6b121-106">检查引用语句中名称的拼写。</span><span class="sxs-lookup"><span data-stu-id="6b121-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="6b121-107">Visual Basic 是不区分大小写，但拼写中的任何其他变体都会被视为完全不同的名称。</span><span class="sxs-lookup"><span data-stu-id="6b121-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="6b121-108">请注意，下划线 (`_`) 是名称的一部分，因此也是拼写的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b121-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="6b121-109">检查你是否拥有成员访问运算符 (`.`) 对象及其成员之间。</span><span class="sxs-lookup"><span data-stu-id="6b121-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="6b121-110">例如，如果你拥有名为 <xref:System.Windows.Forms.TextBox> 的 `TextBox1`控件，则要键入 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 才可访问其 `TextBox1.Text`。</span><span class="sxs-lookup"><span data-stu-id="6b121-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="6b121-111">如果你转而键入 `TextBox1Text`，则会创建不同的名称。</span><span class="sxs-lookup"><span data-stu-id="6b121-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="6b121-112">如果任何对象成员访问语法正确的拼写正确，验证已声明元素。</span><span class="sxs-lookup"><span data-stu-id="6b121-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="6b121-113">有关详细信息，请参阅[Declared Elements](../../programming-guide/language-features/declared-elements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="6b121-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="6b121-114">如果已声明的编程元素，检查它是否在作用域中。</span><span class="sxs-lookup"><span data-stu-id="6b121-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="6b121-115">如果引用语句位于声明编程元素的区域外，您可能需要限定元素名称。</span><span class="sxs-lookup"><span data-stu-id="6b121-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="6b121-116">有关详细信息，请参阅 [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="6b121-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="6b121-117">如果不使用完全限定的类型和成员名称 (例如，你的代码是指属性作为`MethodInfo.Name`而不是`System.Reflection.MethodInfo.Name`)，添加[Imports 语句](../statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="6b121-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="6b121-118">如果您尝试编译 SDK 样式项目 (具有的项目\*.vbproj 文件以在行开头`<Project Sdk="Microsoft.NET.Sdk">`)，和错误消息引用的类型或成员中的 Microsoft.VisualBasic.dll 程序集，来配置应用程序使用 Visual Basic 运行库的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="6b121-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="6b121-119">默认情况下，库的一个子集嵌入在程序集 SDK 样式项目中。</span><span class="sxs-lookup"><span data-stu-id="6b121-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="6b121-120">例如，下面的示例无法进行编译，因为<xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName>找不到方法。</span><span class="sxs-lookup"><span data-stu-id="6b121-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="6b121-121">它不嵌入在你的应用程序中包含的 Visual Basic 运行时的子集。</span><span class="sxs-lookup"><span data-stu-id="6b121-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   <span data-ttu-id="6b121-122">若要解决此错误，将添加`<VBRuntime>Default</VBRuntime>`的项目元素`<PropertyGroup>`部分中，如下面的 Visual Basic 项目文件所示。</span><span class="sxs-lookup"><span data-stu-id="6b121-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="6b121-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b121-123">See also</span></span>

- [<span data-ttu-id="6b121-124">声明和常量摘要</span><span class="sxs-lookup"><span data-stu-id="6b121-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="6b121-125">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="6b121-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="6b121-126">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="6b121-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="6b121-127">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="6b121-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
