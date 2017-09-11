---
title: "在 Visual Basic 中的变量疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ccf7ee3b0205dcd85d82c06e1822c4d3f9296a1c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-variables-in-visual-basic"></a><span data-ttu-id="83969-102">变量疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83969-102">Troubleshooting Variables in Visual Basic</span></span>
<span data-ttu-id="83969-103">此页列出在中使用变量时可能会出现一些常见问题[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="83969-103">This page lists some common problems that can occur when working with variables in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="unable-to-access-members-of-an-object"></a><span data-ttu-id="83969-104">无法访问对象的成员</span><span class="sxs-lookup"><span data-stu-id="83969-104">Unable to Access Members of an Object</span></span>  
 <span data-ttu-id="83969-105">如果你的代码尝试访问对象上的属性或方法，可能会出现两种错误结果：</span><span class="sxs-lookup"><span data-stu-id="83969-105">If your code attempts to access a property or method on an object, there are two possible error outcomes:</span></span>  
  
-   <span data-ttu-id="83969-106">如果你声明对象变量为特定类型，然后引用不是由此类型定义的成员，则编译器可能生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="83969-106">The compiler can generate an error message if you declare the object variable to be of a specific type and then refer to a member not defined by that type.</span></span>  
  
-   <span data-ttu-id="83969-107">运行时<xref:System.MemberAccessException>分配给对象变量的对象不公开您的代码尝试访问的成员时发生。</xref:System.MemberAccessException></span><span class="sxs-lookup"><span data-stu-id="83969-107">A run-time <xref:System.MemberAccessException> occurs when the object assigned to an object variable does not expose the member your code is trying to access.</span></span> <span data-ttu-id="83969-108">在的变量的情况下[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)，您还可以获取此异常，如果该成员不是`Public`。</span><span class="sxs-lookup"><span data-stu-id="83969-108">In the case of a variable of [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md), you can also get this exception if the member is not `Public`.</span></span> <span data-ttu-id="83969-109">这是因为后期绑定只允许访问 `Public` 成员。</span><span class="sxs-lookup"><span data-stu-id="83969-109">This is because late binding allows access only to `Public` members.</span></span>  
  
 <span data-ttu-id="83969-110">当[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)集类型检查`On`，方法和类与其声明的属性，可以访问的对象变量。</span><span class="sxs-lookup"><span data-stu-id="83969-110">When the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets type checking `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="83969-111">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="83969-111">The following example illustrates this.</span></span>  

 <span data-ttu-id="83969-112">[!code-vb[VbVbalrVariables #&2;](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="83969-112">[!code-vb[VbVbalrVariables#2](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]</span></span>  
  
 <span data-ttu-id="83969-113">在此示例中，`p`可以使用的成员<xref:System.Object>类本身，其中不包括`Left`属性。</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="83969-113">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="83969-114">另一方面，`q`已声明的类型为<xref:System.Windows.Forms.Label>，因此它可以使用所有方法和属性<xref:System.Windows.Forms.Label>类<xref:System.Windows.Forms>命名空间。</xref:System.Windows.Forms> </xref:System.Windows.Forms.Label> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="83969-114">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="83969-115">正确方法</span><span class="sxs-lookup"><span data-stu-id="83969-115">Correct Approach</span></span>  
 <span data-ttu-id="83969-116">若要能够访问特定类的对象的所有成员，则尽可能将对象变量声明为该类的类型。</span><span class="sxs-lookup"><span data-stu-id="83969-116">To be able to access all the members of an object of a particular class, declare the object variable to be of the type of that class when possible.</span></span> <span data-ttu-id="83969-117">如果你不能这样做，例如，如果您不知道在编译时类型的对象，则必须设置`Option Strict`到`Off`并声明变量成为[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="83969-117">If you cannot do this, for example if you do not know the object type at compile time, you must set `Option Strict` to `Off` and declare the variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="83969-118">这将允许将任意类型的对象分配给该变量，你应该采取措施确保当前分配的对象是可接受的类型。</span><span class="sxs-lookup"><span data-stu-id="83969-118">This allows objects of any type to be assigned to the variable, and you should take steps to ensure that the currently assigned object is of an acceptable type.</span></span> <span data-ttu-id="83969-119">您可以使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)能够做出此判断。</span><span class="sxs-lookup"><span data-stu-id="83969-119">You can use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to make this determination.</span></span>  
  
## <a name="other-components-cannot-access-your-variable"></a><span data-ttu-id="83969-120">其他组件不能访问你的变量</span><span class="sxs-lookup"><span data-stu-id="83969-120">Other Components Cannot Access Your Variable</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="83969-121">名称是*不区分大小写*。</span><span class="sxs-lookup"><span data-stu-id="83969-121"> names are *case-insensitive*.</span></span> <span data-ttu-id="83969-122">如果这两个名称只是字母大小写不同，编译器会将其解析为相同的名称。</span><span class="sxs-lookup"><span data-stu-id="83969-122">If two names differ in alphabetic case only, the compiler interprets them as the same name.</span></span> <span data-ttu-id="83969-123">例如，它认为 `ABC` 和 `abc` 指的是同一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="83969-123">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="83969-124">但是，公共语言运行时 (CLR) 使用 *区分大小写* 绑定。</span><span class="sxs-lookup"><span data-stu-id="83969-124">However, the common language runtime (CLR) uses *case-sensitive* binding.</span></span> <span data-ttu-id="83969-125">因此，当你生成程序集或 DLL 并使其可供其他程序集使用时，则名称将不再不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="83969-125">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="83969-126">例如，如果你用名为 `ABC`的元素定义类，而其他程序集通过公共语言运行时使用你的类，则元素必须指的是 `ABC`。</span><span class="sxs-lookup"><span data-stu-id="83969-126">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="83969-127">如果你以后重新编译你的类并将元素名称更改为 `abc`，则使用你的类的其他程序集将不能再访问此元素。</span><span class="sxs-lookup"><span data-stu-id="83969-127">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class can no longer access that element.</span></span> <span data-ttu-id="83969-128">因此，发布程序集的更新版本时，不应该更改公共元素的字母大小写。</span><span class="sxs-lookup"><span data-stu-id="83969-128">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
 <span data-ttu-id="83969-129">有关详细信息，请参阅[公共语言运行库](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482)。</span><span class="sxs-lookup"><span data-stu-id="83969-129">For more information, see [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="83969-130">正确方法</span><span class="sxs-lookup"><span data-stu-id="83969-130">Correct Approach</span></span>  
 <span data-ttu-id="83969-131">若要允许其他组件访问你的变量，将其名称视为区分大小写。</span><span class="sxs-lookup"><span data-stu-id="83969-131">To allow other components to access your variables, treat their names as if they were case-sensitive.</span></span> <span data-ttu-id="83969-132">当测试类或模块时，确保其他程序集绑定到你所希望的变量。</span><span class="sxs-lookup"><span data-stu-id="83969-132">When you are testing your class or module, make sure other assemblies are binding to the variables you expect them to.</span></span> <span data-ttu-id="83969-133">发布组件后，请勿对现有变量名称进行修改，包括更改大小写。</span><span class="sxs-lookup"><span data-stu-id="83969-133">Once you have published a component, do not make any modifications to existing variable names, including changing their cases.</span></span>  
  
## <a name="wrong-variable-being-used"></a><span data-ttu-id="83969-134">正在使用的错误变量</span><span class="sxs-lookup"><span data-stu-id="83969-134">Wrong Variable Being Used</span></span>  
 <span data-ttu-id="83969-135">当您有一个同名的多个变量[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器尝试解析该名称对每个引用。</span><span class="sxs-lookup"><span data-stu-id="83969-135">When you have more than one variable with the same name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler attempts to resolve each reference to that name.</span></span> <span data-ttu-id="83969-136">如果变量具有不同的范围，编译器将解析对范围最小的声明的引用。</span><span class="sxs-lookup"><span data-stu-id="83969-136">If the variables have different scope, the compiler resolves a reference to the declaration with the narrowest scope.</span></span> <span data-ttu-id="83969-137">如果它们具有相同的范围，解析将失败，编译器将引发错误。</span><span class="sxs-lookup"><span data-stu-id="83969-137">If they have the same scope, the resolution fails and the compiler signals an error.</span></span> <span data-ttu-id="83969-138">有关详细信息，请参阅[对声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="83969-138">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="83969-139">正确方法</span><span class="sxs-lookup"><span data-stu-id="83969-139">Correct Approach</span></span>  
 <span data-ttu-id="83969-140">避免使用名称相同范围不同的变量。</span><span class="sxs-lookup"><span data-stu-id="83969-140">Avoid using variables with the same name but different scope.</span></span> <span data-ttu-id="83969-141">如果你正在使用其他程序集或项目，尽量避免使用在那些外部组件中定义的任何名称。</span><span class="sxs-lookup"><span data-stu-id="83969-141">If you are using other assemblies or projects, avoid using any names defined in those external components as much as possible.</span></span> <span data-ttu-id="83969-142">如果你有名称相同的多个变量，确保限定对它的每个引用。</span><span class="sxs-lookup"><span data-stu-id="83969-142">If you have more than one variable with the same name, be sure you qualify every reference to it.</span></span> <span data-ttu-id="83969-143">有关详细信息，请参阅[对声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="83969-143">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83969-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83969-144">See Also</span></span>  
 <span data-ttu-id="83969-145">[变量](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="83969-145">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="83969-146"> [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="83969-146"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="83969-147"> [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="83969-147"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="83969-148"> [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="83969-148"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="83969-149"> [如何︰ 访问对象的成员](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="83969-149"> [How to: Access Members of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span></span>  
<span data-ttu-id="83969-150"> [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="83969-150"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="83969-151"> [如何︰ 确定对象变量引用的类型](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="83969-151"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="83969-152"> [对已声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="83969-152"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="83969-153"> [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span><span class="sxs-lookup"><span data-stu-id="83969-153"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span></span>
