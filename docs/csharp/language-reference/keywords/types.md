---
title: "类型（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2816a5dd86e71641198a340b3a72094dffc93bdf
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="types-c-reference"></a><span data-ttu-id="61a44-102">类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="61a44-102">Types (C# Reference)</span></span>
<span data-ttu-id="61a44-103">C# 类型化系统包含以下类别：</span><span class="sxs-lookup"><span data-stu-id="61a44-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="61a44-104">值类型</span><span class="sxs-lookup"><span data-stu-id="61a44-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="61a44-105">引用类型</span><span class="sxs-lookup"><span data-stu-id="61a44-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="61a44-106">指针类型</span><span class="sxs-lookup"><span data-stu-id="61a44-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="61a44-107">值类型的变量可存储数据，引用类型的变量可存储对实际数据的引用。</span><span class="sxs-lookup"><span data-stu-id="61a44-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="61a44-108">引用类型也被称作对象。</span><span class="sxs-lookup"><span data-stu-id="61a44-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="61a44-109">仅在[不安全](../../../csharp/language-reference/keywords/unsafe.md)模式下才可使用指针类型。</span><span class="sxs-lookup"><span data-stu-id="61a44-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="61a44-110">可将值类型转换为引用类型，并通过[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)再次转换回值类型。</span><span class="sxs-lookup"><span data-stu-id="61a44-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="61a44-111">除已装箱值类型外，不可将引用类型转换为值类型。</span><span class="sxs-lookup"><span data-stu-id="61a44-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="61a44-112">本部分还介绍了 [void](../../../csharp/language-reference/keywords/void.md)。</span><span class="sxs-lookup"><span data-stu-id="61a44-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="61a44-113">值类型可为空，即是说它们可以存储其他非值状态。</span><span class="sxs-lookup"><span data-stu-id="61a44-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="61a44-114">有关详细信息，请参阅[可以为 Null 的类型](../../../csharp/programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="61a44-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a44-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61a44-115">See Also</span></span>  
 <span data-ttu-id="61a44-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="61a44-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="61a44-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="61a44-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="61a44-118">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="61a44-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="61a44-119">[类型参考表](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="61a44-119">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 <span data-ttu-id="61a44-120">[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="61a44-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="61a44-121">类型</span><span class="sxs-lookup"><span data-stu-id="61a44-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)

