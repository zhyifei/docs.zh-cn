---
title: 内置类型表（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 120347e5bff7f0d6c7120af0cb250936ca39ea16
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172261"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="a9ed2-102">内置类型表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a9ed2-102">Built-In Types Table (C# Reference)</span></span>
<span data-ttu-id="a9ed2-103">下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名。</span><span class="sxs-lookup"><span data-stu-id="a9ed2-103">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="a9ed2-104">C# 类型</span><span class="sxs-lookup"><span data-stu-id="a9ed2-104">C# Type</span></span>|<span data-ttu-id="a9ed2-105">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="a9ed2-105">.NET Framework Type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="a9ed2-106">bool</span><span class="sxs-lookup"><span data-stu-id="a9ed2-106">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[<span data-ttu-id="a9ed2-107">byte</span><span class="sxs-lookup"><span data-stu-id="a9ed2-107">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[<span data-ttu-id="a9ed2-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="a9ed2-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[<span data-ttu-id="a9ed2-109">char</span><span class="sxs-lookup"><span data-stu-id="a9ed2-109">char</span></span>](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[<span data-ttu-id="a9ed2-110">decimal</span><span class="sxs-lookup"><span data-stu-id="a9ed2-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[<span data-ttu-id="a9ed2-111">double</span><span class="sxs-lookup"><span data-stu-id="a9ed2-111">double</span></span>](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[<span data-ttu-id="a9ed2-112">float</span><span class="sxs-lookup"><span data-stu-id="a9ed2-112">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[<span data-ttu-id="a9ed2-113">int</span><span class="sxs-lookup"><span data-stu-id="a9ed2-113">int</span></span>](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[<span data-ttu-id="a9ed2-114">uint</span><span class="sxs-lookup"><span data-stu-id="a9ed2-114">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[<span data-ttu-id="a9ed2-115">long</span><span class="sxs-lookup"><span data-stu-id="a9ed2-115">long</span></span>](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[<span data-ttu-id="a9ed2-116">ulong</span><span class="sxs-lookup"><span data-stu-id="a9ed2-116">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[<span data-ttu-id="a9ed2-117">object</span><span class="sxs-lookup"><span data-stu-id="a9ed2-117">object</span></span>](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[<span data-ttu-id="a9ed2-118">short</span><span class="sxs-lookup"><span data-stu-id="a9ed2-118">short</span></span>](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[<span data-ttu-id="a9ed2-119">ushort</span><span class="sxs-lookup"><span data-stu-id="a9ed2-119">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[<span data-ttu-id="a9ed2-120">string</span><span class="sxs-lookup"><span data-stu-id="a9ed2-120">string</span></span>](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a><span data-ttu-id="a9ed2-121">备注</span><span class="sxs-lookup"><span data-stu-id="a9ed2-121">Remarks</span></span>  
 <span data-ttu-id="a9ed2-122">此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。</span><span class="sxs-lookup"><span data-stu-id="a9ed2-122">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
 <span data-ttu-id="a9ed2-123">C# 类型关键字及其别名可互换。</span><span class="sxs-lookup"><span data-stu-id="a9ed2-123">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="a9ed2-124">例如，可通过使用以下任意一个声明来声明整型变量：</span><span class="sxs-lookup"><span data-stu-id="a9ed2-124">For example, you can declare an integer variable by using either of the following declarations:</span></span>  
  
```csharp  
int x = 123;  
System.Int32 x = 123;  
```  
  
 <span data-ttu-id="a9ed2-125">要显示任何 C# 类型的实际类型，请使用系统方法 `GetType()`。</span><span class="sxs-lookup"><span data-stu-id="a9ed2-125">To display the actual type for any C# type, use the system method `GetType()`.</span></span> <span data-ttu-id="a9ed2-126">例如，如下语句显示表示 `myVariable` 类型的系统别名：</span><span class="sxs-lookup"><span data-stu-id="a9ed2-126">For example, the following statement displays the system alias that represents the type of `myVariable`:</span></span>  
  
```csharp  
Console.WriteLine(myVariable.GetType());  
```  
  
 <span data-ttu-id="a9ed2-127">也可使用 [typeof](../../../csharp/language-reference/keywords/typeof.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="a9ed2-127">You can also use the [typeof](../../../csharp/language-reference/keywords/typeof.md) operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ed2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ed2-128">See Also</span></span>  
 [<span data-ttu-id="a9ed2-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a9ed2-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a9ed2-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a9ed2-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a9ed2-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a9ed2-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a9ed2-132">值类型</span><span class="sxs-lookup"><span data-stu-id="a9ed2-132">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="a9ed2-133">默认值表</span><span class="sxs-lookup"><span data-stu-id="a9ed2-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="a9ed2-134">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="a9ed2-134">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [<span data-ttu-id="a9ed2-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="a9ed2-135">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="a9ed2-136">类型参考表</span><span class="sxs-lookup"><span data-stu-id="a9ed2-136">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
