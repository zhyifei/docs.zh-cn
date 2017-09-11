---
title: "在 .NET 中分析其他字符串"
description: "在 .NET 中分析其他字符串"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: db80cc5f37e814f224ff76b14a906bb4d41064fb
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="b5897-104">在 .NET 中分析其他字符串</span><span class="sxs-lookup"><span data-stu-id="b5897-104">Parsing other strings in .NET</span></span>

<span data-ttu-id="b5897-105">除了数字和 [DateTime](xref:System.DateTime) 字符串之外，还可以将表示类型 [Char](xref:System.Char)、[Boolean](xref:System.Boolean) 和 [Enum](xref:System.Enum) 的字符串分析为数据类型。</span><span class="sxs-lookup"><span data-stu-id="b5897-105">In addition to numeric and [DateTime](xref:System.DateTime) strings, you can also parse strings that represent the types [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) into data types.</span></span>

## <a name="char"></a><span data-ttu-id="b5897-106">Char</span><span class="sxs-lookup"><span data-stu-id="b5897-106">Char</span></span>

<span data-ttu-id="b5897-107">与 [Char](xref:System.Char) 数据类型关联的静态分析方法 可用于将包含单个字符的字符串转换为其 Unicode 值。</span><span class="sxs-lookup"><span data-stu-id="b5897-107">The static parse method associated with the [Char](xref:System.Char) data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="b5897-108">下面的代码示例将字符串分析为 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="b5897-108">The following code example parses a string into a Unicode character.</span></span>

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a><span data-ttu-id="b5897-109">Boolean</span><span class="sxs-lookup"><span data-stu-id="b5897-109">Boolean</span></span>

<span data-ttu-id="b5897-110">[Boolean](xref:System.Boolean) 数据类型包含 [Parse](xref:System.Boolean.Parse(System.String)) 方法，可以用于将表示 `Boolean` 值的字符串转换为实际 `Boolean` 类型。</span><span class="sxs-lookup"><span data-stu-id="b5897-110">The [Boolean](xref:System.Boolean) data type contains a [Parse](xref:System.Boolean.Parse(System.String)) method that you can use to convert a string that represents a `Boolean` value into an actual `Boolean` type.</span></span> <span data-ttu-id="b5897-111">此方法不区分大小写，可以成功分析包含“True”或“False”的字符串。</span><span class="sxs-lookup"><span data-stu-id="b5897-111">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="b5897-112">与 `Boolean` 类型关联的 `Parse` 方法还可以分析两端是空格的字符串。</span><span class="sxs-lookup"><span data-stu-id="b5897-112">The `Parse` method associated with the `Boolean` type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="b5897-113">如果传递任何其他字符串，则会引发 [FormatException](xref:System.FormatException)。</span><span class="sxs-lookup"><span data-stu-id="b5897-113">If any other string is passed, a [FormatException](xref:System.FormatException) is thrown.</span></span>

<span data-ttu-id="b5897-114">下面的代码示例使用 `Parse` 方法将字符串转换为 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="b5897-114">The following code example uses the `Parse` method to convert a string into a `Boolean` value.</span></span>

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a><span data-ttu-id="b5897-115">枚举</span><span class="sxs-lookup"><span data-stu-id="b5897-115">Enumeration</span></span>

<span data-ttu-id="b5897-116">可以使用静态 [Parse](xref:System.Enum.Parse(System.Type,System.String)) 方法将枚举类型初始化为字符串的值。</span><span class="sxs-lookup"><span data-stu-id="b5897-116">You can use the static [Parse](xref:System.Enum.Parse(System.Type,System.String)) method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="b5897-117">此方法接受所分析的枚举类型、要分析的字符串和可选 `Boolean` 标志（指示分析是否区分大小写）。</span><span class="sxs-lookup"><span data-stu-id="b5897-117">This method accepts the enumeration type you are parsing, the string to parse, and an optional `Boolean` flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="b5897-118">所分析的字符串可以包含用逗号分隔的多个值，这些值前面或后面可以是一个或多个空白（也称为空格）。</span><span class="sxs-lookup"><span data-stu-id="b5897-118">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="b5897-119">当字符串包含多个值时，返回的对象的值是所有指定值通过按位 OR 运算组合的值。</span><span class="sxs-lookup"><span data-stu-id="b5897-119">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>

<span data-ttu-id="b5897-120">下面的示例使用 `Parse` 方法将字符串表示形式转换为枚举值。</span><span class="sxs-lookup"><span data-stu-id="b5897-120">The following example uses the `Parse` method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="b5897-121">[DayOfWeek](xref:System.DayOfWeek) 枚举从星期四初始化为字符串。</span><span class="sxs-lookup"><span data-stu-id="b5897-121">The [DayOfWeek](xref:System.DayOfWeek) enumeration is initialized to Thursday from a string.</span></span>

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a><span data-ttu-id="b5897-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5897-122">See Also</span></span>

[<span data-ttu-id="b5897-123">在 .NET 中分析字符串</span><span class="sxs-lookup"><span data-stu-id="b5897-123">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="b5897-124">.NET 中的格式设置类型</span><span class="sxs-lookup"><span data-stu-id="b5897-124">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="b5897-125">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="b5897-125">Type conversion in .NET</span></span>](type-conversion.md)


