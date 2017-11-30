---
title: Value Types and Reference Types
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b54945d27d186771e8b5353e753afd74c56d71b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="4dc32-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4dc32-102">Value Types and Reference Types</span></span>
<span data-ttu-id="4dc32-103">在 Visual Basic 中，数据类型是基于其分类来实现的。</span><span class="sxs-lookup"><span data-stu-id="4dc32-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="4dc32-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]数据类型可依据特定类型的变量存储其自己的数据或指向的数据进行分类。</span><span class="sxs-lookup"><span data-stu-id="4dc32-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="4dc32-105">如果它存储其自己的数据则*值类型*; 如果它保留一个指向它的内存中其他位置的数据*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="4dc32-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="4dc32-106">值类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-106">Value Types</span></span>  
 <span data-ttu-id="4dc32-107">数据类型是*值类型*如果它包含在其自己的内存分配数据。</span><span class="sxs-lookup"><span data-stu-id="4dc32-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="4dc32-108">值类型包括：</span><span class="sxs-lookup"><span data-stu-id="4dc32-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="4dc32-109">所有数值数据类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="4dc32-110">`Boolean`、`Char` 和 `Date`</span><span class="sxs-lookup"><span data-stu-id="4dc32-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="4dc32-111">所有的结构，即使其成员是引用类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="4dc32-112">枚举，因为其基础类型始终是`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或`ULong`</span><span class="sxs-lookup"><span data-stu-id="4dc32-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="4dc32-113">每个结构是值类型，即使它包含引用类型成员。</span><span class="sxs-lookup"><span data-stu-id="4dc32-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="4dc32-114">为此，值类型，如`Char`和`Integer`由.NET Framework 结构实现。</span><span class="sxs-lookup"><span data-stu-id="4dc32-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="4dc32-115">你可以使用保留的关键字，例如，声明值类型`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="4dc32-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="4dc32-116">你还可以使用`New`关键字初始化值类型。</span><span class="sxs-lookup"><span data-stu-id="4dc32-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="4dc32-117">这是特别有用，如果该类型具有的构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="4dc32-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="4dc32-118">此示例是<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，它将生成新`Decimal`从提供的部分的值。</span><span class="sxs-lookup"><span data-stu-id="4dc32-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="4dc32-119">引用类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-119">Reference Types</span></span>  
 <span data-ttu-id="4dc32-120">A*引用类型*包含保存的数据的另一个内存位置的指针。</span><span class="sxs-lookup"><span data-stu-id="4dc32-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="4dc32-121">引用类型包括：</span><span class="sxs-lookup"><span data-stu-id="4dc32-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="4dc32-122">所有数组，即使其元素为值类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="4dc32-123">类类型如<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="4dc32-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="4dc32-124">委托</span><span class="sxs-lookup"><span data-stu-id="4dc32-124">Delegates</span></span>  
  
 <span data-ttu-id="4dc32-125">类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="4dc32-125">A class is a *reference type*.</span></span> <span data-ttu-id="4dc32-126">为此，引用类型如`Object`和`String`支持[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类。</span><span class="sxs-lookup"><span data-stu-id="4dc32-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="4dc32-127">请注意，每个数组是引用类型，即使其成员是值类型。</span><span class="sxs-lookup"><span data-stu-id="4dc32-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="4dc32-128">由于每个引用类型表示的基础的.NET Framework 类，你必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="4dc32-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="4dc32-129">下面的语句初始化数组。</span><span class="sxs-lookup"><span data-stu-id="4dc32-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="4dc32-130">不支持类型的元素</span><span class="sxs-lookup"><span data-stu-id="4dc32-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="4dc32-131">以下编程元素不适合作为类型，因为不能指定其中任何为声明的元素的数据类型：</span><span class="sxs-lookup"><span data-stu-id="4dc32-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="4dc32-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="4dc32-132">Namespaces</span></span>  
  
-   <span data-ttu-id="4dc32-133">模块</span><span class="sxs-lookup"><span data-stu-id="4dc32-133">Modules</span></span>  
  
-   <span data-ttu-id="4dc32-134">事件</span><span class="sxs-lookup"><span data-stu-id="4dc32-134">Events</span></span>  
  
-   <span data-ttu-id="4dc32-135">属性和过程</span><span class="sxs-lookup"><span data-stu-id="4dc32-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="4dc32-136">变量、 常量和字段</span><span class="sxs-lookup"><span data-stu-id="4dc32-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="4dc32-137">使用对象数据类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="4dc32-138">可以将引用类型或值类型分配给变量的`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="4dc32-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="4dc32-139">`Object`变量始终保留一个指向的数据，永远不会数据本身。</span><span class="sxs-lookup"><span data-stu-id="4dc32-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="4dc32-140">但是，如果将分配到的值类型`Object`变量，其行为就像它包含其自己的数据。</span><span class="sxs-lookup"><span data-stu-id="4dc32-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="4dc32-141">有关详细信息，请参阅[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc32-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="4dc32-142">你可以找出是否`Object`变量作为引用类型或值类型将其传递到<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>类<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="4dc32-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4dc32-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>返回`True`如果的内容`Object`变量表示引用类型。</span><span class="sxs-lookup"><span data-stu-id="4dc32-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc32-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc32-144">See Also</span></span>  
 [<span data-ttu-id="4dc32-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="4dc32-146">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="4dc32-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="4dc32-147">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4dc32-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="4dc32-148">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="4dc32-149">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="4dc32-150">数据类型</span><span class="sxs-lookup"><span data-stu-id="4dc32-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
