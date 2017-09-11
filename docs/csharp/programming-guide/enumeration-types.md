---
title: "枚举类型（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="5890c-102">枚举类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5890c-102">Enumeration Types (C# Programming Guide)</span></span>
<span data-ttu-id="5890c-103">枚举类型（也称为枚举）提供了一种有效的方式来定义可能分配给变量的一组已命名整数常量。</span><span class="sxs-lookup"><span data-stu-id="5890c-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="5890c-104">例如，假设你需要定义一个变量，其值表示一周内的某一天。</span><span class="sxs-lookup"><span data-stu-id="5890c-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="5890c-105">该变量只会存储七个有意义的值。</span><span class="sxs-lookup"><span data-stu-id="5890c-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="5890c-106">若要定义这些值，可以使用枚举类型，该类型是使用 [enum](../../csharp/language-reference/keywords/enum.md) 关键字声明的。</span><span class="sxs-lookup"><span data-stu-id="5890c-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>  
  
 <span data-ttu-id="5890c-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span></span>  
  
 <span data-ttu-id="5890c-108">默认情况下，枚举中每个元素的基础类型都为 [int](../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="5890c-108">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="5890c-109">可以使用冒号指定另一种整数类型，如上例所示。</span><span class="sxs-lookup"><span data-stu-id="5890c-109">You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="5890c-110">有关可能的类型的完整列表，请参阅 [enum（C# 参考）](../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="5890c-110">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="5890c-111">可以通过转换为基础类型来验证基础数值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="5890c-111">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 <span data-ttu-id="5890c-112">以下是使用枚举而不使用数值类型的好处：</span><span class="sxs-lookup"><span data-stu-id="5890c-112">The following are advantages of using an enum instead of a numeric type:</span></span>  
  
-   <span data-ttu-id="5890c-113">明确为客户端代码指定对变量有效的值。</span><span class="sxs-lookup"><span data-stu-id="5890c-113">You clearly specify for client code which values are valid for the variable.</span></span>  
  
-   <span data-ttu-id="5890c-114">在 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 中，IntelliSense 列出了定义的值。</span><span class="sxs-lookup"><span data-stu-id="5890c-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>  
  
 <span data-ttu-id="5890c-115">如果未为枚举器列表中的元素指定值，则值将自动按 1 递增。</span><span class="sxs-lookup"><span data-stu-id="5890c-115">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="5890c-116">在上例中，`Days.Sunday` 的值为 0，`Days.Monday` 的值为 1，依此类推。</span><span class="sxs-lookup"><span data-stu-id="5890c-116">In the previous example, `Days.Sunday` has a value of 0, `Days.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="5890c-117">创建新的 `Days` 对象时，如果没有明确为其分配值，它将具有默认值 `Days.Sunday` (0)。</span><span class="sxs-lookup"><span data-stu-id="5890c-117">When you create a new `Days` object, it will have a default value of `Days.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="5890c-118">创建枚举时，请选择最有逻辑的默认值，并为其分配值零。</span><span class="sxs-lookup"><span data-stu-id="5890c-118">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="5890c-119">这将导致所有枚举都具有默认值（如果未在创建时显式分配值）。</span><span class="sxs-lookup"><span data-stu-id="5890c-119">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>  
  
 <span data-ttu-id="5890c-120">如果变量 `meetingDay` 的类型为 `Days`，那么在没有显式转换的情况下只能为其分配由 `Days` 定义的值。</span><span class="sxs-lookup"><span data-stu-id="5890c-120">If the variable `meetingDay` is of type `Days`, then (without an explicit cast) you can only assign it one of the values defined by `Days`.</span></span> <span data-ttu-id="5890c-121">如果会议日期更改，可以将 `Days` 中的新值分配给 `meetingDay`：</span><span class="sxs-lookup"><span data-stu-id="5890c-121">And if the meeting day changes, you can assign a new value from `Days` to `meetingDay`:</span></span>  
  
 <span data-ttu-id="5890c-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5890c-123">可以将任意整数值分配给 `meetingDay`。</span><span class="sxs-lookup"><span data-stu-id="5890c-123">It is possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="5890c-124">例如，代码行 `meetingDay = (Days) 42` 不会产生错误。</span><span class="sxs-lookup"><span data-stu-id="5890c-124">For example, this line of code does not produce an error: `meetingDay = (Days) 42`.</span></span> <span data-ttu-id="5890c-125">但应避免这样做，因为隐式预期是枚举变量只会持有枚举所定义的其中一个值。</span><span class="sxs-lookup"><span data-stu-id="5890c-125">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="5890c-126">为枚举类型的变量分配任意值很可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="5890c-126">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>  
  
 <span data-ttu-id="5890c-127">可以为枚举类型的枚举器列表中的元素分配任何值，也可以使用计算值：</span><span class="sxs-lookup"><span data-stu-id="5890c-127">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>  
  
 <span data-ttu-id="5890c-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span></span>  
  
## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="5890c-129">作为位标志的枚举类型</span><span class="sxs-lookup"><span data-stu-id="5890c-129">Enumeration Types as Bit Flags</span></span>  
 <span data-ttu-id="5890c-130">可以使用枚举类型来定义位标志，这使枚举类型的实例能够存储枚举器列表中定义的值的任何组合。</span><span class="sxs-lookup"><span data-stu-id="5890c-130">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="5890c-131">（当然，某些组合在你的程序代码中可能没有意义或不允许使用。）</span><span class="sxs-lookup"><span data-stu-id="5890c-131">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>  
  
 <span data-ttu-id="5890c-132">创建位标志枚举的方法是，应用 <xref:System.FlagsAttribute?displayProperty=fullName> 属性并适当定义一些值，以便可以对这些值执行 `AND`、`OR`、`NOT` 和 `XOR` 按位运算。</span><span class="sxs-lookup"><span data-stu-id="5890c-132">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=fullName> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="5890c-133">在位标志枚举中，包括一个值为零（表示“未设置任何标志”）的命名常量。</span><span class="sxs-lookup"><span data-stu-id="5890c-133">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="5890c-134">如果零值不表示“未设置任何标志”，请勿为标志指定零值。</span><span class="sxs-lookup"><span data-stu-id="5890c-134">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>  
  
 <span data-ttu-id="5890c-135">在以下示例中，定义了名为 `Days2` 枚举的另一个版本，命名为 `Days`。</span><span class="sxs-lookup"><span data-stu-id="5890c-135">In the following example, another version of the `Days` enum, which is named `Days2`, is defined.</span></span> <span data-ttu-id="5890c-136">`Days2` 具有 `Flags` 属性，且它的每个值都是 2 的若干次幂，指数依次递增。</span><span class="sxs-lookup"><span data-stu-id="5890c-136">`Days2` has the `Flags` attribute and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="5890c-137">这样，你就能够创建值为 `Days2.Tuesday` 和 `Days2.Thursday` 的 `Days2` 变量。</span><span class="sxs-lookup"><span data-stu-id="5890c-137">This enables you to create a `Days2` variable whose value is `Days2.Tuesday` and `Days2.Thursday`.</span></span>  
  
 <span data-ttu-id="5890c-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span></span>  
  
 <span data-ttu-id="5890c-139">若要在枚举上设置标志，请使用按位 `OR` 运算符，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5890c-139">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>  
  
 <span data-ttu-id="5890c-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span></span>  
  
 <span data-ttu-id="5890c-141">若要确定是否设置了特定标志，请使用按位 `AND` 运算，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5890c-141">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>  
  
 <span data-ttu-id="5890c-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span></span>  
  
 <span data-ttu-id="5890c-143">有关使用 <xref:System.FlagsAttribute?displayProperty=fullName> 特性定义枚举类型时应考虑事项的详细信息，请参阅 <xref:System.Enum?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="5890c-143">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=fullName> attribute, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="5890c-144">使用 System.Enum 方法来发现和操作枚举值</span><span class="sxs-lookup"><span data-stu-id="5890c-144">Using the System.Enum Methods to Discover and Manipulate Enum Values</span></span>  
 <span data-ttu-id="5890c-145">所有枚举都是 <xref:System.Enum?displayProperty=fullName> 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5890c-145">All enums are instances of the <xref:System.Enum?displayProperty=fullName> type.</span></span> <span data-ttu-id="5890c-146">不能从 <xref:System.Enum?displayProperty=fullName> 中派生新类，但可以使用它的方法来发现有关枚举实例中操作值的信息。</span><span class="sxs-lookup"><span data-stu-id="5890c-146">You cannot derive new classes from <xref:System.Enum?displayProperty=fullName>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>  
  
 <span data-ttu-id="5890c-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="5890c-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span></span>  
  
 <span data-ttu-id="5890c-148">有关更多信息，请参见<xref:System.Enum?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="5890c-148">For more information, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="5890c-149">还可以使用扩展方法创建枚举的新方法。</span><span class="sxs-lookup"><span data-stu-id="5890c-149">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="5890c-150">有关详细信息，请参阅[如何：为枚举创建新方法](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="5890c-150">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="5890c-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5890c-151">See Also</span></span>  
 <span data-ttu-id="5890c-152"><xref:System.Enum?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5890c-152"><xref:System.Enum?displayProperty=fullName></span></span>   
 <span data-ttu-id="5890c-153">[C# 编程指南](../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5890c-153">[C# Programming Guide](../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5890c-154">enum</span><span class="sxs-lookup"><span data-stu-id="5890c-154">enum</span></span>](../../csharp/language-reference/keywords/enum.md)

