---
title: "默认值表（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d609403269a5cbfe6715647a240c44b254a4d8f9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="8d8c4-102">默认值表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8d8c4-102">Default Values Table (C# Reference)</span></span>
<span data-ttu-id="8d8c4-103">下表显示默认构造函数返回的值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="8d8c4-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="8d8c4-104">默认构造函数使用 `new` 运算符进行调用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d8c4-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="8d8c4-105">上一语句与如下语句效果相同：</span><span class="sxs-lookup"><span data-stu-id="8d8c4-105">The preceding statement has the same effect as the following statement:</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="8d8c4-106">请记住：不允许在 C# 中使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="8d8c4-106">Remember that using uninitialized variables in C# is not allowed.</span></span>  
  
|<span data-ttu-id="8d8c4-107">值类型</span><span class="sxs-lookup"><span data-stu-id="8d8c4-107">Value type</span></span>|<span data-ttu-id="8d8c4-108">默认值</span><span class="sxs-lookup"><span data-stu-id="8d8c4-108">Default value</span></span>|  
|----------------|-------------------|  
|[<span data-ttu-id="8d8c4-109">bool</span><span class="sxs-lookup"><span data-stu-id="8d8c4-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|  
|[<span data-ttu-id="8d8c4-110">byte</span><span class="sxs-lookup"><span data-stu-id="8d8c4-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="8d8c4-111">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-111">0</span></span>|  
|[<span data-ttu-id="8d8c4-112">char</span><span class="sxs-lookup"><span data-stu-id="8d8c4-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="8d8c4-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="8d8c4-113">'\0'</span></span>|  
|[<span data-ttu-id="8d8c4-114">小数</span><span class="sxs-lookup"><span data-stu-id="8d8c4-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="8d8c4-115">0.0M</span><span class="sxs-lookup"><span data-stu-id="8d8c4-115">0.0M</span></span>|  
|[<span data-ttu-id="8d8c4-116">double</span><span class="sxs-lookup"><span data-stu-id="8d8c4-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="8d8c4-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="8d8c4-117">0.0D</span></span>|  
|[<span data-ttu-id="8d8c4-118">enum</span><span class="sxs-lookup"><span data-stu-id="8d8c4-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="8d8c4-119">表达式 (E)0 生成的值，其中 E 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="8d8c4-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|  
|[<span data-ttu-id="8d8c4-120">float</span><span class="sxs-lookup"><span data-stu-id="8d8c4-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="8d8c4-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="8d8c4-121">0.0F</span></span>|  
|[<span data-ttu-id="8d8c4-122">int</span><span class="sxs-lookup"><span data-stu-id="8d8c4-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="8d8c4-123">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-123">0</span></span>|  
|[<span data-ttu-id="8d8c4-124">long</span><span class="sxs-lookup"><span data-stu-id="8d8c4-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="8d8c4-125">0L</span><span class="sxs-lookup"><span data-stu-id="8d8c4-125">0L</span></span>|  
|[<span data-ttu-id="8d8c4-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="8d8c4-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="8d8c4-127">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-127">0</span></span>|  
|[<span data-ttu-id="8d8c4-128">short</span><span class="sxs-lookup"><span data-stu-id="8d8c4-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="8d8c4-129">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-129">0</span></span>|  
|[<span data-ttu-id="8d8c4-130">struct</span><span class="sxs-lookup"><span data-stu-id="8d8c4-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="8d8c4-131">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="8d8c4-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|  
|[<span data-ttu-id="8d8c4-132">uint</span><span class="sxs-lookup"><span data-stu-id="8d8c4-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="8d8c4-133">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-133">0</span></span>|  
|[<span data-ttu-id="8d8c4-134">ulong</span><span class="sxs-lookup"><span data-stu-id="8d8c4-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="8d8c4-135">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-135">0</span></span>|  
|[<span data-ttu-id="8d8c4-136">ushort</span><span class="sxs-lookup"><span data-stu-id="8d8c4-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="8d8c4-137">0</span><span class="sxs-lookup"><span data-stu-id="8d8c4-137">0</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d8c4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d8c4-138">See Also</span></span>  
 <span data-ttu-id="8d8c4-139">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d8c4-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8d8c4-140">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d8c4-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8d8c4-141">[值类型表](../../../csharp/language-reference/keywords/value-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="8d8c4-141">[Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md) </span></span>  
 <span data-ttu-id="8d8c4-142">[值类型](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="8d8c4-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="8d8c4-143">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="8d8c4-143">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="8d8c4-144">类型参考表</span><span class="sxs-lookup"><span data-stu-id="8d8c4-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

