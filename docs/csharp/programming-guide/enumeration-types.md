---
title: "枚举类型（C# 编程指南）"
ms.date: 09/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13ec7d5d2a44cddb2b7f440c8d811c2e4060d432
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="dcdb7-102">枚举类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="dcdb7-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="dcdb7-103">枚举类型（也称为枚举）提供了一种有效的方式来定义可能分配给变量的一组已命名整数常量。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="dcdb7-104">例如，假设你需要定义一个变量，其值表示一周内的某一天。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="dcdb7-105">该变量只会存储七个有意义的值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="dcdb7-106">若要定义这些值，可以使用枚举类型，该类型是使用 [enum](../../csharp/language-reference/keywords/enum.md) 关键字声明的。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="dcdb7-107">默认情况下，枚举中每个元素的基础类型都为 [int](../../csharp/language-reference/keywords/int.md)。可以使用冒号指定另一种整数类型，如上例所示。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-107">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="dcdb7-108">有关可能的类型的完整列表，请参阅 [enum（C# 参考）](../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-108">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="dcdb7-109">可以通过转换为基础类型来验证基础数值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="dcdb7-110">以下是使用枚举而不使用数值类型的好处：</span><span class="sxs-lookup"><span data-stu-id="dcdb7-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="dcdb7-111">明确为客户端代码指定对变量有效的值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="dcdb7-112">在 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 中，IntelliSense 列出了定义的值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-112">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>

<span data-ttu-id="dcdb7-113">如果未为枚举器列表中的元素指定值，则值将自动按 1 递增。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="dcdb7-114">在上例中，`Day.Sunday` 的值为 0，`Day.Monday` 的值为 1，依此类推。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="dcdb7-115">创建新的 `Day` 对象时，如果没有明确为其分配值，它将具有默认值 `Day.Sunday` (0)。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="dcdb7-116">创建枚举时，请选择最有逻辑的默认值，并为其分配值零。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="dcdb7-117">这将导致所有枚举都具有默认值（如果未在创建时显式分配值）。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="dcdb7-118">如果变量 `meetingDay` 的类型为 `Day`，那么在没有显式转换的情况下只能为其分配由 `Day` 定义的值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="dcdb7-119">如果会议日期更改，可以将 `Day` 中的新值分配给 `meetingDay`：</span><span class="sxs-lookup"><span data-stu-id="dcdb7-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="dcdb7-120">可以将任意整数值分配给 `meetingDay`。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="dcdb7-121">例如，代码行 `meetingDay = (Day) 42` 不会产生错误。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="dcdb7-122">但应避免这样做，因为隐式预期是枚举变量只会持有枚举所定义的其中一个值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="dcdb7-123">为枚举类型的变量分配任意值很可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="dcdb7-124">可以为枚举类型的枚举器列表中的元素分配任何值，也可以使用计算值：</span><span class="sxs-lookup"><span data-stu-id="dcdb7-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="dcdb7-125">作为位标志的枚举类型</span><span class="sxs-lookup"><span data-stu-id="dcdb7-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="dcdb7-126">可以使用枚举类型来定义位标志，这使枚举类型的实例能够存储枚举器列表中定义的值的任何组合。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="dcdb7-127">（当然，某些组合在你的程序代码中可能没有意义或不允许使用。）</span><span class="sxs-lookup"><span data-stu-id="dcdb7-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="dcdb7-128">创建位标志枚举的方法是，应用 <xref:System.FlagsAttribute?displayProperty=nameWithType> 属性并适当定义一些值，以便可以对这些值执行 `AND`、`OR`、`NOT` 和 `XOR` 按位运算。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="dcdb7-129">在位标志枚举中，包括一个值为零（表示“未设置任何标志”）的命名常量。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="dcdb7-130">如果零值不表示“未设置任何标志”，请勿为标志指定零值。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="dcdb7-131">在以下示例中，定义了名为 `Days` 枚举的另一个版本，命名为 `Day`。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="dcdb7-132">`Days` 具有 `Flags` 属性，且它的每个值都是 2 的若干次幂，指数依次递增。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="dcdb7-133">这样，你就能够创建值为 `Days.Tuesday | Days.Thursday` 的 `Days` 变量。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="dcdb7-134">若要在枚举上设置标志，请使用按位 `OR` 运算符，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="dcdb7-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="dcdb7-135">若要确定是否设置了特定标志，请使用按位 `AND` 运算，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="dcdb7-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="dcdb7-136">有关使用 <xref:System.FlagsAttribute?displayProperty=nameWithType> 特性定义枚举类型时应考虑事项的详细信息，请参阅 <xref:System.Enum?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="dcdb7-137">使用 System.Enum 方法来发现和操作枚举值</span><span class="sxs-lookup"><span data-stu-id="dcdb7-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="dcdb7-138">所有枚举都是 <xref:System.Enum?displayProperty=nameWithType> 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="dcdb7-139">不能从 <xref:System.Enum?displayProperty=nameWithType> 中派生新类，但可以使用它的方法来发现有关枚举实例中操作值的信息。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="dcdb7-140">有关更多信息，请参见<xref:System.Enum?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="dcdb7-141">还可以使用扩展方法创建枚举的新方法。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="dcdb7-142">有关详细信息，请参阅[如何：为枚举创建新方法](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-142">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcdb7-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcdb7-143">See also</span></span>
 <xref:System.Enum?displayProperty=nameWithType>  
 [<span data-ttu-id="dcdb7-144">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dcdb7-144">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dcdb7-145">enum</span><span class="sxs-lookup"><span data-stu-id="dcdb7-145">enum</span></span>](../../csharp/language-reference/keywords/enum.md)
