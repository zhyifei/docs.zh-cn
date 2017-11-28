---
title: "内置类型表（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9d1e4945526a862074e73e608185696328946be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="52eef-102">内置类型表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="52eef-102">Built-In Types Table (C# Reference)</span></span>
<span data-ttu-id="52eef-103">下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名。</span><span class="sxs-lookup"><span data-stu-id="52eef-103">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="52eef-104">C# 类型</span><span class="sxs-lookup"><span data-stu-id="52eef-104">C# Type</span></span>|<span data-ttu-id="52eef-105">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="52eef-105">.NET Framework Type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="52eef-106">bool</span><span class="sxs-lookup"><span data-stu-id="52eef-106">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[<span data-ttu-id="52eef-107">byte</span><span class="sxs-lookup"><span data-stu-id="52eef-107">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[<span data-ttu-id="52eef-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="52eef-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[<span data-ttu-id="52eef-109">char</span><span class="sxs-lookup"><span data-stu-id="52eef-109">char</span></span>](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[<span data-ttu-id="52eef-110">小数</span><span class="sxs-lookup"><span data-stu-id="52eef-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[<span data-ttu-id="52eef-111">double</span><span class="sxs-lookup"><span data-stu-id="52eef-111">double</span></span>](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[<span data-ttu-id="52eef-112">float</span><span class="sxs-lookup"><span data-stu-id="52eef-112">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[<span data-ttu-id="52eef-113">int</span><span class="sxs-lookup"><span data-stu-id="52eef-113">int</span></span>](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[<span data-ttu-id="52eef-114">uint</span><span class="sxs-lookup"><span data-stu-id="52eef-114">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[<span data-ttu-id="52eef-115">long</span><span class="sxs-lookup"><span data-stu-id="52eef-115">long</span></span>](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[<span data-ttu-id="52eef-116">ulong</span><span class="sxs-lookup"><span data-stu-id="52eef-116">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[<span data-ttu-id="52eef-117">对象</span><span class="sxs-lookup"><span data-stu-id="52eef-117">object</span></span>](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[<span data-ttu-id="52eef-118">short</span><span class="sxs-lookup"><span data-stu-id="52eef-118">short</span></span>](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[<span data-ttu-id="52eef-119">ushort</span><span class="sxs-lookup"><span data-stu-id="52eef-119">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[<span data-ttu-id="52eef-120">字符串</span><span class="sxs-lookup"><span data-stu-id="52eef-120">string</span></span>](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a><span data-ttu-id="52eef-121">备注</span><span class="sxs-lookup"><span data-stu-id="52eef-121">Remarks</span></span>  
 <span data-ttu-id="52eef-122">此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。</span><span class="sxs-lookup"><span data-stu-id="52eef-122">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
 <span data-ttu-id="52eef-123">C# 类型关键字及其别名可互换。</span><span class="sxs-lookup"><span data-stu-id="52eef-123">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="52eef-124">例如，可通过使用以下任意一个声明来声明整型变量：</span><span class="sxs-lookup"><span data-stu-id="52eef-124">For example, you can declare an integer variable by using either of the following declarations:</span></span>  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 <span data-ttu-id="52eef-125">要显示任何 C# 类型的实际类型，请使用系统方法 `GetType()`。</span><span class="sxs-lookup"><span data-stu-id="52eef-125">To display the actual type for any C# type, use the system method `GetType()`.</span></span> <span data-ttu-id="52eef-126">例如，如下语句显示表示 `myVariable` 类型的系统别名：</span><span class="sxs-lookup"><span data-stu-id="52eef-126">For example, the following statement displays the system alias that represents the type of `myVariable`:</span></span>  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 <span data-ttu-id="52eef-127">也可使用 [typeof](../../../csharp/language-reference/keywords/typeof.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="52eef-127">You can also use the [typeof](../../../csharp/language-reference/keywords/typeof.md) operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52eef-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52eef-128">See Also</span></span>  
 [<span data-ttu-id="52eef-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="52eef-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="52eef-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="52eef-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="52eef-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="52eef-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="52eef-132">值类型</span><span class="sxs-lookup"><span data-stu-id="52eef-132">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="52eef-133">默认值表</span><span class="sxs-lookup"><span data-stu-id="52eef-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="52eef-134">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="52eef-134">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [<span data-ttu-id="52eef-135">动态</span><span class="sxs-lookup"><span data-stu-id="52eef-135">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="52eef-136">类型参考表</span><span class="sxs-lookup"><span data-stu-id="52eef-136">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
