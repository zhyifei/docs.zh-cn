---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="c4d1a-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="c4d1a-102">Object Data Type</span></span>
<span data-ttu-id="c4d1a-103">包含引用的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="c4d1a-104">你可以将任何引用类型 （字符串、 数组、 类或接口） 分配给`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="c4d1a-105">`Object`变量也可以指任何值类型的数据 (数字， `Boolean`， `Char`， `Date`，结构或枚举)。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4d1a-106">备注</span><span class="sxs-lookup"><span data-stu-id="c4d1a-106">Remarks</span></span>  
 <span data-ttu-id="c4d1a-107">`Object`数据类型可以指向任何数据类型，包括应用程序识别的任何对象实例的数据。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="c4d1a-108">使用`Object`时你不知道在编译时哪种数据类型变量可能指向。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="c4d1a-109">默认值`Object`是`Nothing`（空引用）。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c4d1a-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="c4d1a-110">Data Types</span></span>  
 <span data-ttu-id="c4d1a-111">你可以分配变量、 常量或表达式的任何数据类型设置为`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="c4d1a-112">若要确定数据类型`Object`变量当前引用的则可以使用<xref:System.Type.GetTypeCode%2A>方法<xref:System.Type?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c4d1a-113">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="c4d1a-114">`Object`数据类型是引用类型。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="c4d1a-115">但是，Visual Basic 会将`Object`变量为值类型时它指的是值类型的数据。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="c4d1a-116">存储</span><span class="sxs-lookup"><span data-stu-id="c4d1a-116">Storage</span></span>  
 <span data-ttu-id="c4d1a-117">它指任何数据类型`Object`变量不包含数据值本身，但而是指向值的指针。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="c4d1a-118">它始终在计算机内存中，使用四个字节，但这不包括表示变量的值的数据的存储。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="c4d1a-119">由于使用指针来定位数据，代码`Object`持有值类型变量时速度稍慢比访问显式类型化的变量。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="c4d1a-120">编程提示</span><span class="sxs-lookup"><span data-stu-id="c4d1a-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="c4d1a-121">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="c4d1a-121">**Interop Considerations.**</span></span> <span data-ttu-id="c4d1a-122">如果你与不是为.NET Framework 中，如自动化或 COM 对象编写的组件交互请记住在其他环境中的指针类型不兼容使用 Visual Basic`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="c4d1a-123">**性能。**</span><span class="sxs-lookup"><span data-stu-id="c4d1a-123">**Performance.**</span></span> <span data-ttu-id="c4d1a-124">使用声明的变量`Object`类型的灵活程度足以包含的任何对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="c4d1a-125">但是，在调用方法或属性上此类变量时，你始终会产生*后期绑定*（在运行时）。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="c4d1a-126">若要强制*早期绑定*（在编译时） 和更好的性能、 声明变量与特定的类名称，或将其转换为特定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="c4d1a-127">在声明对象变量时，尝试使用特定的类类型，例如<xref:System.OperatingSystem>，而不是通用`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="c4d1a-128">你还应使用最具体的类可用，如<xref:System.Windows.Forms.TextBox>而不是<xref:System.Windows.Forms.Control>，以便你可以访问其属性和方法。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="c4d1a-129">您通常可以使用**类**列入**对象浏览器**来查找可用的类名。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="c4d1a-130">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="c4d1a-130">**Widening.**</span></span> <span data-ttu-id="c4d1a-131">所有数据类型和所有引用类型扩大到`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="c4d1a-132">这意味着你可以将任意类型转换到`Object`而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="c4d1a-133">但是，如果值类型之间进行转换和`Object`，Visual Basic 执行调用的操作*装箱*和*取消装箱*，这使执行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="c4d1a-134">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="c4d1a-134">**Type Characters.**</span></span> <span data-ttu-id="c4d1a-135">`Object`不包含文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="c4d1a-136">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="c4d1a-136">**Framework Type.**</span></span> <span data-ttu-id="c4d1a-137">.NET Framework 中的对应类型是<xref:System.Object?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d1a-138">示例</span><span class="sxs-lookup"><span data-stu-id="c4d1a-138">Example</span></span>  
 <span data-ttu-id="c4d1a-139">下面的示例演示`Object`变量指向的对象实例。</span><span class="sxs-lookup"><span data-stu-id="c4d1a-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4d1a-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4d1a-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="c4d1a-141">数据类型</span><span class="sxs-lookup"><span data-stu-id="c4d1a-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="c4d1a-142">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="c4d1a-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="c4d1a-143">转换摘要</span><span class="sxs-lookup"><span data-stu-id="c4d1a-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="c4d1a-144">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="c4d1a-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="c4d1a-145">如何：确定两个对象是否相关</span><span class="sxs-lookup"><span data-stu-id="c4d1a-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="c4d1a-146">如何：确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="c4d1a-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
