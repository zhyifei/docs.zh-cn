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
ms.openlocfilehash: 2f09a2842edfa9471267f294c9b64229ae824098
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738743"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="72927-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="72927-102">Value Types and Reference Types</span></span>
<span data-ttu-id="72927-103">在 Visual Basic 中，基于分类实施数据类型。</span><span class="sxs-lookup"><span data-stu-id="72927-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="72927-104">Visual Basic 数据类型可以根据特定类型的变量存储其自己的数据或指向的数据分类。</span><span class="sxs-lookup"><span data-stu-id="72927-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="72927-105">如果将存储其自己的数据很*值类型*; 如果它包含一个指针，它是的内存中的其他位置的数据*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="72927-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="72927-106">值类型</span><span class="sxs-lookup"><span data-stu-id="72927-106">Value Types</span></span>  
 <span data-ttu-id="72927-107">数据类型是*值类型*如果它保存在其自己的内存分配中的数据。</span><span class="sxs-lookup"><span data-stu-id="72927-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="72927-108">值类型包括：</span><span class="sxs-lookup"><span data-stu-id="72927-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="72927-109">所有数值数据类型</span><span class="sxs-lookup"><span data-stu-id="72927-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="72927-110">`Boolean`、 `Char`和 `Date`</span><span class="sxs-lookup"><span data-stu-id="72927-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="72927-111">所有的结构，即使其成员是引用类型</span><span class="sxs-lookup"><span data-stu-id="72927-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="72927-112">枚举，因为它们的基础类型始终`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或 `ULong`</span><span class="sxs-lookup"><span data-stu-id="72927-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="72927-113">每个结构是值类型，即使它包含引用类型成员。</span><span class="sxs-lookup"><span data-stu-id="72927-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="72927-114">出于此原因，值类型，如`Char`和`Integer`由.NET Framework 结构实现。</span><span class="sxs-lookup"><span data-stu-id="72927-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="72927-115">可以通过使用保留的关键字，例如，声明值类型`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="72927-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="72927-116">此外可以使用`New`关键字初始化值类型。</span><span class="sxs-lookup"><span data-stu-id="72927-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="72927-117">这是特别有用，如果该类型具有带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="72927-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="72927-118">这就<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，将生成新`Decimal`从提供的部分的值。</span><span class="sxs-lookup"><span data-stu-id="72927-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="72927-119">引用类型</span><span class="sxs-lookup"><span data-stu-id="72927-119">Reference Types</span></span>  
 <span data-ttu-id="72927-120">一个*引用类型*包含保存的数据的另一个内存位置的指针。</span><span class="sxs-lookup"><span data-stu-id="72927-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="72927-121">引用类型包括：</span><span class="sxs-lookup"><span data-stu-id="72927-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="72927-122">所有数组，即使其元素是值类型</span><span class="sxs-lookup"><span data-stu-id="72927-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="72927-123">类类型如 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="72927-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="72927-124">委托</span><span class="sxs-lookup"><span data-stu-id="72927-124">Delegates</span></span>  
  
 <span data-ttu-id="72927-125">类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="72927-125">A class is a *reference type*.</span></span> <span data-ttu-id="72927-126">出于此原因，如引用类型`Object`并`String`支持的[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类。</span><span class="sxs-lookup"><span data-stu-id="72927-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="72927-127">请注意，每个数组是引用类型，即使其成员是值类型。</span><span class="sxs-lookup"><span data-stu-id="72927-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="72927-128">由于每个引用类型表示的基础的.NET Framework 类，因此必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="72927-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="72927-129">下面的语句初始化数组。</span><span class="sxs-lookup"><span data-stu-id="72927-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="72927-130">不是类型的元素</span><span class="sxs-lookup"><span data-stu-id="72927-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="72927-131">以下的编程元素不适合作为类型，因为您不能指定其中任何一个已声明元素的数据类型为：</span><span class="sxs-lookup"><span data-stu-id="72927-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="72927-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="72927-132">Namespaces</span></span>  
  
-   <span data-ttu-id="72927-133">模块</span><span class="sxs-lookup"><span data-stu-id="72927-133">Modules</span></span>  
  
-   <span data-ttu-id="72927-134">事件</span><span class="sxs-lookup"><span data-stu-id="72927-134">Events</span></span>  
  
-   <span data-ttu-id="72927-135">属性和过程</span><span class="sxs-lookup"><span data-stu-id="72927-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="72927-136">变量、 常量和字段</span><span class="sxs-lookup"><span data-stu-id="72927-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="72927-137">使用对象数据类型</span><span class="sxs-lookup"><span data-stu-id="72927-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="72927-138">可以将引用类型或值类型分配给的变量`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="72927-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="72927-139">`Object`变量始终保存一个指针，该数据，永远不会数据本身。</span><span class="sxs-lookup"><span data-stu-id="72927-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="72927-140">但是，如果将分配到值类型`Object`变量，其行为就像它保留其自己的数据。</span><span class="sxs-lookup"><span data-stu-id="72927-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="72927-141">有关详细信息，请参阅[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="72927-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="72927-142">您可以确定是否`Object`变量充当引用类型或值类型将其传递到<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>的类<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="72927-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="72927-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返回`True`如果内容的`Object`变量表示引用类型。</span><span class="sxs-lookup"><span data-stu-id="72927-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72927-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="72927-144">See also</span></span>
- [<span data-ttu-id="72927-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="72927-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="72927-146">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="72927-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="72927-147">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="72927-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="72927-148">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="72927-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="72927-149">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="72927-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="72927-150">数据类型</span><span class="sxs-lookup"><span data-stu-id="72927-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
