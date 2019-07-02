---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504877"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="4d5f6-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4d5f6-102">Value Types and Reference Types</span></span>
<span data-ttu-id="4d5f6-103">有两种类型的 Visual Basic 中的类型： 引用类型和值类型。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="4d5f6-104">引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="4d5f6-105">对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="4d5f6-106">对于值类型，每个变量都具有其自己数据副本，并且不可能会影响另一个变量上的操作 (的情况下除外[ByRef 参数修饰符](../../../language-reference/modifiers/byref.md))。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="4d5f6-107">值类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-107">Value Types</span></span>  
 <span data-ttu-id="4d5f6-108">数据类型是*值类型*如果它保存在其自己的内存分配中的数据。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="4d5f6-109">值类型包括：</span><span class="sxs-lookup"><span data-stu-id="4d5f6-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="4d5f6-110">所有数值数据类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-110">All numeric data types</span></span>  
  
- <span data-ttu-id="4d5f6-111">`Boolean`、 `Char`和 `Date`</span><span class="sxs-lookup"><span data-stu-id="4d5f6-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="4d5f6-112">所有的结构，即使其成员是引用类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="4d5f6-113">枚举，因为它们的基础类型始终`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或 `ULong`</span><span class="sxs-lookup"><span data-stu-id="4d5f6-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="4d5f6-114">每个结构是值类型，即使它包含引用类型成员。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="4d5f6-115">出于此原因，值类型，如`Char`和`Integer`由.NET Framework 结构实现。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="4d5f6-116">可以通过使用保留的关键字，例如，声明值类型`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="4d5f6-117">此外可以使用`New`关键字初始化值类型。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="4d5f6-118">这是特别有用，如果该类型具有带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="4d5f6-119">这就<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，将生成新`Decimal`从提供的部分的值。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="4d5f6-120">引用类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-120">Reference Types</span></span>  
 <span data-ttu-id="4d5f6-121">一个*引用类型*存储对其数据的引用。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="4d5f6-122">引用类型包括：</span><span class="sxs-lookup"><span data-stu-id="4d5f6-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="4d5f6-123">所有数组，即使其元素是值类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="4d5f6-124">类类型如 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="4d5f6-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="4d5f6-125">委托</span><span class="sxs-lookup"><span data-stu-id="4d5f6-125">Delegates</span></span>  
  
 <span data-ttu-id="4d5f6-126">类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-126">A class is a *reference type*.</span></span> <span data-ttu-id="4d5f6-127">请注意，每个数组是引用类型，即使其成员是值类型。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="4d5f6-128">由于每个引用类型表示的基础的.NET Framework 类，因此必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="4d5f6-129">下面的语句初始化数组。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="4d5f6-130">不是类型的元素</span><span class="sxs-lookup"><span data-stu-id="4d5f6-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="4d5f6-131">以下的编程元素不适合作为类型，因为您不能指定其中任何一个已声明元素的数据类型为：</span><span class="sxs-lookup"><span data-stu-id="4d5f6-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="4d5f6-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="4d5f6-132">Namespaces</span></span>  
  
- <span data-ttu-id="4d5f6-133">模块</span><span class="sxs-lookup"><span data-stu-id="4d5f6-133">Modules</span></span>  
  
- <span data-ttu-id="4d5f6-134">事件</span><span class="sxs-lookup"><span data-stu-id="4d5f6-134">Events</span></span>  
  
- <span data-ttu-id="4d5f6-135">属性和过程</span><span class="sxs-lookup"><span data-stu-id="4d5f6-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="4d5f6-136">变量、 常量和字段</span><span class="sxs-lookup"><span data-stu-id="4d5f6-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="4d5f6-137">使用对象数据类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="4d5f6-138">可以将引用类型或值类型分配给的变量`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="4d5f6-139">`Object`变量始终保留到数据，永远不会数据本身的引用。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="4d5f6-140">但是，如果将分配到值类型`Object`变量，其行为就像它保留其自己的数据。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="4d5f6-141">有关详细信息，请参阅[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="4d5f6-142">您可以确定是否`Object`变量充当引用类型或值类型将其传递到<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>的类<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4d5f6-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返回`True`如果内容的`Object`变量表示引用类型。</span><span class="sxs-lookup"><span data-stu-id="4d5f6-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5f6-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d5f6-144">See also</span></span>

- [<span data-ttu-id="4d5f6-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="4d5f6-146">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="4d5f6-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="4d5f6-147">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4d5f6-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="4d5f6-148">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="4d5f6-149">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="4d5f6-150">数据类型</span><span class="sxs-lookup"><span data-stu-id="4d5f6-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
