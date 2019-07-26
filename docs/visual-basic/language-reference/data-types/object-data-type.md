---
title: Object 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513048"
---
# <a name="object-data-type"></a><span data-ttu-id="13ec8-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="13ec8-102">Object Data Type</span></span>

<span data-ttu-id="13ec8-103">保存引用对象的地址。</span><span class="sxs-lookup"><span data-stu-id="13ec8-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="13ec8-104">可以将任何引用类型 (字符串、数组、类或接口) 分配给`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="13ec8-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="13ec8-105">变量还可以引用任意值类型的数据 ( `Char`数值、 `Boolean`、、 `Date`、结构或枚举)。 `Object`</span><span class="sxs-lookup"><span data-stu-id="13ec8-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="13ec8-106">备注</span><span class="sxs-lookup"><span data-stu-id="13ec8-106">Remarks</span></span>

<span data-ttu-id="13ec8-107">`Object`数据类型可以指向任何数据类型的数据, 包括应用程序识别的任何对象实例。</span><span class="sxs-lookup"><span data-stu-id="13ec8-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="13ec8-108">在`Object`编译时不知道变量可能指向的数据类型时, 请使用。</span><span class="sxs-lookup"><span data-stu-id="13ec8-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="13ec8-109">的默认值`Object`为`Nothing` (空引用)。</span><span class="sxs-lookup"><span data-stu-id="13ec8-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="13ec8-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="13ec8-110">Data Types</span></span>

<span data-ttu-id="13ec8-111">可以将任何数据类型的变量、常量或表达式分配给`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="13ec8-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="13ec8-112">若要确定`Object`变量当前引用的数据类型, 可以<xref:System.Type.GetTypeCode%2A>使用<xref:System.Type?displayProperty=nameWithType>类的方法。</span><span class="sxs-lookup"><span data-stu-id="13ec8-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="13ec8-113">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="13ec8-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="13ec8-114">`Object`数据类型为引用类型。</span><span class="sxs-lookup"><span data-stu-id="13ec8-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="13ec8-115">但是, 当`Object`变量引用值类型的数据时, Visual Basic 将变量视为值类型。</span><span class="sxs-lookup"><span data-stu-id="13ec8-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="13ec8-116">存储</span><span class="sxs-lookup"><span data-stu-id="13ec8-116">Storage</span></span>

<span data-ttu-id="13ec8-117">无论它引用哪种数据类型, `Object`变量都不包含数据值本身, 而是指向值的指针。</span><span class="sxs-lookup"><span data-stu-id="13ec8-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="13ec8-118">它在计算机内存中始终使用四个字节, 但这不包括表示变量值的数据的存储。</span><span class="sxs-lookup"><span data-stu-id="13ec8-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="13ec8-119">由于使用指针查找数据的代码, `Object`保存值类型的变量比显式类型化变量略慢。</span><span class="sxs-lookup"><span data-stu-id="13ec8-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="13ec8-120">编程提示</span><span class="sxs-lookup"><span data-stu-id="13ec8-120">Programming Tips</span></span>

- <span data-ttu-id="13ec8-121">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="13ec8-121">**Interop Considerations.**</span></span> <span data-ttu-id="13ec8-122">如果与不是为 .NET Framework 编写的组件 (如自动化或 COM 对象) 交互, 请记住, 其他环境中的指针类型与 Visual Basic `Object`类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="13ec8-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="13ec8-123">**性能。**</span><span class="sxs-lookup"><span data-stu-id="13ec8-123">**Performance.**</span></span> <span data-ttu-id="13ec8-124">用`Object`类型声明的变量的灵活性足以包含对任何对象的引用。</span><span class="sxs-lookup"><span data-stu-id="13ec8-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="13ec8-125">但是, 在此类变量上调用方法或属性时, 始终会产生*后期绑定*(在运行时)。</span><span class="sxs-lookup"><span data-stu-id="13ec8-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="13ec8-126">若要强制进行*早期绑定*(在编译时) 和更好的性能, 请使用特定类名称声明变量, 或将其转换为特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="13ec8-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="13ec8-127">声明对象变量时, 请尝试使用特定类类型, <xref:System.OperatingSystem>而不是通用`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="13ec8-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="13ec8-128">还应使用最具体的类, 如<xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control>而不是, 以便您可以访问其属性和方法。</span><span class="sxs-lookup"><span data-stu-id="13ec8-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="13ec8-129">通常可以使用**对象浏览器**中的 "**类**" 列表来查找可用的类名。</span><span class="sxs-lookup"><span data-stu-id="13ec8-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="13ec8-130">**扩大.**</span><span class="sxs-lookup"><span data-stu-id="13ec8-130">**Widening.**</span></span> <span data-ttu-id="13ec8-131">所有数据类型和所有引用类型都扩大到`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="13ec8-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="13ec8-132">这意味着, 可以将任何类型转换`Object`为, 而<xref:System.OverflowException?displayProperty=nameWithType>不会遇到错误。</span><span class="sxs-lookup"><span data-stu-id="13ec8-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="13ec8-133">但是, 如果在值类型和`Object`之间进行转换, Visual Basic 将执行称为*装箱*和*取消装箱*的操作, 这会使执行速度变慢。</span><span class="sxs-lookup"><span data-stu-id="13ec8-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="13ec8-134">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="13ec8-134">**Type Characters.**</span></span> <span data-ttu-id="13ec8-135">`Object`没有文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="13ec8-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="13ec8-136">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="13ec8-136">**Framework Type.**</span></span> <span data-ttu-id="13ec8-137">.NET Framework 中的相应类型是<xref:System.Object?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="13ec8-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="13ec8-138">示例</span><span class="sxs-lookup"><span data-stu-id="13ec8-138">Example</span></span>

<span data-ttu-id="13ec8-139">下面的示例演示指向`Object`对象实例的变量。</span><span class="sxs-lookup"><span data-stu-id="13ec8-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="13ec8-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="13ec8-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="13ec8-141">数据类型</span><span class="sxs-lookup"><span data-stu-id="13ec8-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="13ec8-142">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="13ec8-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="13ec8-143">转换摘要</span><span class="sxs-lookup"><span data-stu-id="13ec8-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="13ec8-144">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="13ec8-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="13ec8-145">如何：确定两个对象是否相关</span><span class="sxs-lookup"><span data-stu-id="13ec8-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="13ec8-146">如何：确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="13ec8-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
