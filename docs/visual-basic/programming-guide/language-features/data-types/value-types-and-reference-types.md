---
title: "值类型和引用类型 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8136f58b2e7fce15e959e04b84b05f64d078d662
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="686df-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="686df-102">Value Types and Reference Types</span></span>
<span data-ttu-id="686df-103">在 Visual Basic 中，基于分类实现数据类型。</span><span class="sxs-lookup"><span data-stu-id="686df-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="686df-104">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可以根据特定类型的变量存储其自己的数据或指向的数据的数据类型进行分类。</span><span class="sxs-lookup"><span data-stu-id="686df-104">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="686df-105">如果将存储其自己的数据则*值类型*; 如果它是的内存中其他位置的数据保留一个指针*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="686df-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="686df-106">值类型</span><span class="sxs-lookup"><span data-stu-id="686df-106">Value Types</span></span>  
 <span data-ttu-id="686df-107">数据类型是*值类型*是否包含在其自己的内存分配中的数据。</span><span class="sxs-lookup"><span data-stu-id="686df-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="686df-108">值类型包括︰</span><span class="sxs-lookup"><span data-stu-id="686df-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="686df-109">所有数值数据类型</span><span class="sxs-lookup"><span data-stu-id="686df-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="686df-110">`Boolean`、`Char` 和 `Date`</span><span class="sxs-lookup"><span data-stu-id="686df-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="686df-111">所有结构，即使其成员是都引用类型</span><span class="sxs-lookup"><span data-stu-id="686df-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="686df-112">枚举，因为它们的基础类型始终`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或`ULong`</span><span class="sxs-lookup"><span data-stu-id="686df-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="686df-113">每个结构是值类型，即使它包含引用类型成员。</span><span class="sxs-lookup"><span data-stu-id="686df-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="686df-114">出于此原因，值类型，如`Char`和`Integer`由.NET Framework 结构实现。</span><span class="sxs-lookup"><span data-stu-id="686df-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="686df-115">您可以通过使用保留的关键字，例如，声明值类型`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="686df-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="686df-116">您还可以使用`New`关键字来初始化值类型。</span><span class="sxs-lookup"><span data-stu-id="686df-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="686df-117">这是特别有用，如果该类型具有带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="686df-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="686df-118">此示例是<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，它将生成新`Decimal`值从提供的部分。</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29></span><span class="sxs-lookup"><span data-stu-id="686df-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="686df-119">引用类型</span><span class="sxs-lookup"><span data-stu-id="686df-119">Reference Types</span></span>  
 <span data-ttu-id="686df-120">一个*引用类型*包含指向另一个保存的数据的内存位置的指针。</span><span class="sxs-lookup"><span data-stu-id="686df-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="686df-121">引用类型包括︰</span><span class="sxs-lookup"><span data-stu-id="686df-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="686df-122">所有数组，即使其元素是都值类型</span><span class="sxs-lookup"><span data-stu-id="686df-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="686df-123">类类型如<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="686df-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="686df-124">委托</span><span class="sxs-lookup"><span data-stu-id="686df-124">Delegates</span></span>  
  
 <span data-ttu-id="686df-125">类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="686df-125">A class is a *reference type*.</span></span> <span data-ttu-id="686df-126">出于此原因，引用类型如`Object`和`String`支持[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]类。</span><span class="sxs-lookup"><span data-stu-id="686df-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes.</span></span> <span data-ttu-id="686df-127">请注意每个数组是引用类型，即使其成员都是值类型。</span><span class="sxs-lookup"><span data-stu-id="686df-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="686df-128">由于每个引用类型表示基础.NET Framework 类时，必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时将其初始化。</span><span class="sxs-lookup"><span data-stu-id="686df-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="686df-129">下面的语句初始化数组。</span><span class="sxs-lookup"><span data-stu-id="686df-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="686df-130">不是类型的元素</span><span class="sxs-lookup"><span data-stu-id="686df-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="686df-131">下面的编程元素不适合作为类型，因为您不能指定其中的任何已声明元素的数据类型︰</span><span class="sxs-lookup"><span data-stu-id="686df-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="686df-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="686df-132">Namespaces</span></span>  
  
-   <span data-ttu-id="686df-133">模块</span><span class="sxs-lookup"><span data-stu-id="686df-133">Modules</span></span>  
  
-   <span data-ttu-id="686df-134">事件</span><span class="sxs-lookup"><span data-stu-id="686df-134">Events</span></span>  
  
-   <span data-ttu-id="686df-135">属性和过程</span><span class="sxs-lookup"><span data-stu-id="686df-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="686df-136">变量、 常量和字段</span><span class="sxs-lookup"><span data-stu-id="686df-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="686df-137">使用对象数据类型</span><span class="sxs-lookup"><span data-stu-id="686df-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="686df-138">可以将引用类型还是值类型分配给的变量`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="686df-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="686df-139">`Object`变量始终保留一个指向数据永远不会数据本身。</span><span class="sxs-lookup"><span data-stu-id="686df-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="686df-140">但是，如果将分配到的值类型`Object`变量时，其行为就像它包含其自己的数据。</span><span class="sxs-lookup"><span data-stu-id="686df-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="686df-141">有关详细信息，请参阅[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="686df-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="686df-142">你可以查明是否`Object`变量作为引用类型或值类型将其传递给<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>的类<xref:Microsoft.VisualBasic?displayProperty=fullName>命名空间。</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="686df-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="686df-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>返回`True`如果的内容`Object`变量表示引用类型。</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="686df-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="686df-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="686df-144">See Also</span></span>  
 <span data-ttu-id="686df-145">[可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="686df-145">[Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="686df-146"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="686df-146"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="686df-147"> [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="686df-147"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="686df-148"> [有效使用数据类型](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="686df-148"> [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span></span>  
<span data-ttu-id="686df-149"> [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="686df-149"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="686df-150"> [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="686df-150"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
