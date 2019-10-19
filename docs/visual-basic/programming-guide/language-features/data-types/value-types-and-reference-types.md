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
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582649"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="8e64c-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="8e64c-102">Value Types and Reference Types</span></span>
<span data-ttu-id="8e64c-103">Visual Basic 中有两种类型：引用类型和值类型。</span><span class="sxs-lookup"><span data-stu-id="8e64c-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="8e64c-104">引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。</span><span class="sxs-lookup"><span data-stu-id="8e64c-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="8e64c-105">对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="8e64c-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="8e64c-106">对于值类型，每个变量都有自己的数据副本，对一个变量执行的操作不可能影响另一个变量（在[参数上传递修饰符](../../../language-reference/modifiers/byref.md)的情况除外）。</span><span class="sxs-lookup"><span data-stu-id="8e64c-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="8e64c-107">值类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-107">Value Types</span></span>  
 <span data-ttu-id="8e64c-108">如果数据类型在其自身的内存分配中包含数据，则该数据类型为*值类型*。</span><span class="sxs-lookup"><span data-stu-id="8e64c-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="8e64c-109">值类型包括：</span><span class="sxs-lookup"><span data-stu-id="8e64c-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="8e64c-110">所有数值数据类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-110">All numeric data types</span></span>  
  
- <span data-ttu-id="8e64c-111">`Boolean`、 `Char`和 `Date`</span><span class="sxs-lookup"><span data-stu-id="8e64c-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="8e64c-112">所有结构（即使它们的成员是引用类型）</span><span class="sxs-lookup"><span data-stu-id="8e64c-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="8e64c-113">枚举，因为它们的基础类型始终 `SByte`、`Short`、`Integer`、`Long`、`Byte`、`UShort`、`UInteger` 或 `ULong`</span><span class="sxs-lookup"><span data-stu-id="8e64c-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="8e64c-114">每个结构都是值类型，即使它包含引用类型成员。</span><span class="sxs-lookup"><span data-stu-id="8e64c-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="8e64c-115">出于此原因，值类型（如 `Char` 和 `Integer`）是由 .NET Framework 结构实现的。</span><span class="sxs-lookup"><span data-stu-id="8e64c-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="8e64c-116">您可以使用保留的关键字（例如 `Decimal`）声明值类型。</span><span class="sxs-lookup"><span data-stu-id="8e64c-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="8e64c-117">还可以使用 `New` 关键字初始化值类型。</span><span class="sxs-lookup"><span data-stu-id="8e64c-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="8e64c-118">如果类型具有采用参数的构造函数，则此方法特别有用。</span><span class="sxs-lookup"><span data-stu-id="8e64c-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="8e64c-119">这是 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 构造函数的一个示例，它从提供的部分生成新的 `Decimal` 值。</span><span class="sxs-lookup"><span data-stu-id="8e64c-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="8e64c-120">引用类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-120">Reference Types</span></span>  
 <span data-ttu-id="8e64c-121">*引用类型*存储对其数据的引用。</span><span class="sxs-lookup"><span data-stu-id="8e64c-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="8e64c-122">引用类型包括：</span><span class="sxs-lookup"><span data-stu-id="8e64c-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="8e64c-123">所有数组（即使它们的元素为值类型）</span><span class="sxs-lookup"><span data-stu-id="8e64c-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="8e64c-124">类类型，如 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="8e64c-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="8e64c-125">委托</span><span class="sxs-lookup"><span data-stu-id="8e64c-125">Delegates</span></span>  
  
 <span data-ttu-id="8e64c-126">类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="8e64c-126">A class is a *reference type*.</span></span> <span data-ttu-id="8e64c-127">请注意，每个数组都是引用类型，即使其成员是值类型也是如此。</span><span class="sxs-lookup"><span data-stu-id="8e64c-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="8e64c-128">由于每个引用类型都表示一个基础 .NET Framework 类，因此必须在初始化时使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="8e64c-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="8e64c-129">下面的语句初始化一个数组。</span><span class="sxs-lookup"><span data-stu-id="8e64c-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="8e64c-130">不是类型的元素</span><span class="sxs-lookup"><span data-stu-id="8e64c-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="8e64c-131">下面的编程元素不限定为类型，因为您不能将任何这些元素指定为已声明元素的数据类型：</span><span class="sxs-lookup"><span data-stu-id="8e64c-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="8e64c-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="8e64c-132">Namespaces</span></span>  
  
- <span data-ttu-id="8e64c-133">模块</span><span class="sxs-lookup"><span data-stu-id="8e64c-133">Modules</span></span>  
  
- <span data-ttu-id="8e64c-134">事件</span><span class="sxs-lookup"><span data-stu-id="8e64c-134">Events</span></span>  
  
- <span data-ttu-id="8e64c-135">属性和过程</span><span class="sxs-lookup"><span data-stu-id="8e64c-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="8e64c-136">变量、常量和字段</span><span class="sxs-lookup"><span data-stu-id="8e64c-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="8e64c-137">使用 Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="8e64c-138">可以将引用类型或值类型分配给 `Object` 数据类型的变量。</span><span class="sxs-lookup"><span data-stu-id="8e64c-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="8e64c-139">@No__t_0 变量始终保存对数据的引用，而不是数据本身。</span><span class="sxs-lookup"><span data-stu-id="8e64c-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="8e64c-140">但是，如果将值类型分配给 `Object` 变量，则其行为就像它包含自己的数据一样。</span><span class="sxs-lookup"><span data-stu-id="8e64c-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="8e64c-141">有关详细信息，请参阅[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="8e64c-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="8e64c-142">可以通过将 `Object` 变量传递到 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 命名空间的 <xref:Microsoft.VisualBasic.Information> 类中的 <xref:Microsoft.VisualBasic.Information.IsReference%2A> 方法来确定该变量是作为引用类型还是值类型。</span><span class="sxs-lookup"><span data-stu-id="8e64c-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8e64c-143">如果 `Object` 变量的内容表示引用类型，<xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 将返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="8e64c-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e64c-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e64c-144">See also</span></span>

- [<span data-ttu-id="8e64c-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="8e64c-146">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="8e64c-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="8e64c-147">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="8e64c-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="8e64c-148">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8e64c-149">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="8e64c-150">数据类型</span><span class="sxs-lookup"><span data-stu-id="8e64c-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
