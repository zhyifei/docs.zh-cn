---
title: "在 .NET 中分析字符串"
description: "在 .NET 中分析字符串"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.contentlocale: zh-cn
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a><span data-ttu-id="f92c0-104">在 .NET 中分析字符串</span><span class="sxs-lookup"><span data-stu-id="f92c0-104">Parsing strings in .NET</span></span>

<span data-ttu-id="f92c0-105">分析操作将表示某种 .NET 基类型的字符串转换为该基类型。</span><span class="sxs-lookup"><span data-stu-id="f92c0-105">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="f92c0-106">例如，分析操作用于将字符串转换为浮点数字或日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="f92c0-106">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="f92c0-107">最常用于执行分析操作的方法是 `Parse` 方法。</span><span class="sxs-lookup"><span data-stu-id="f92c0-107">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="f92c0-108">因为分析是格式设置（涉及将基类型转换为其字符串表示形式）的反向操作，所以有许多相同规则和约定适用。</span><span class="sxs-lookup"><span data-stu-id="f92c0-108">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="f92c0-109">正如格式设置使用实现 [IFormatProvider](xref:System.IFormatProvider) 接口的对象提供区分区域性的格式设置信息一样，分析也使用实现 [IFormatProvider](xref:System.IFormatProvider) 接口的对象确定如何解释字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="f92c0-109">Just as formatting uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to provide culture-sensitive formatting information, parsing also uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="f92c0-110">有关更多信息，请参见 [.NET 中的格式设置类型](formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f92c0-110">For more information, see [Formatting Types in .NET](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f92c0-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f92c0-111">In This Section</span></span>

<span data-ttu-id="f92c0-112">[在 .NET 中分析数字字符串](parsing-numeric.md) - 介绍如何将字符串转换成 .NET 数字类型。</span><span class="sxs-lookup"><span data-stu-id="f92c0-112">[Parsing Numeric Strings in .NET](parsing-numeric.md) - Describes how to convert strings into .NET numeric types.</span></span>

<span data-ttu-id="f92c0-113">[在 .NET 中分析日期和时间字符串](parsing-datetime.md) - 介绍如何将字符串转换成 .NET `DateTime` 类型。</span><span class="sxs-lookup"><span data-stu-id="f92c0-113">[Parsing Date and Time Strings in .NET](parsing-datetime.md) - Describes how to convert strings into .NET `DateTime` types.</span></span>

<span data-ttu-id="f92c0-114">[在 .NET 中分析其他字符串](parsing-other.md) - 介绍如何将字符串转换为 [Char](xref:System.Char)、[Boolean](xref:System.Boolean) 和 [Enum](xref:System.Enum) 类型。</span><span class="sxs-lookup"><span data-stu-id="f92c0-114">[Parsing Other Strings in .NET](parsing-other.md) - Describes how to convert strings into [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) types.</span></span>

<span data-ttu-id="f92c0-115">[.NET 中的格式设置类型](formatting-types.md) - 介绍基本格式设置概念，如格式说明符和格式提供程序。</span><span class="sxs-lookup"><span data-stu-id="f92c0-115">[Formatting Types in .NET](formatting-types.md) - Describes basic formatting concepts like format specifiers and format providers.</span></span>

<span data-ttu-id="f92c0-116">[.NET 中的类型转换](type-conversion.md) - 介绍如何转换类型。</span><span class="sxs-lookup"><span data-stu-id="f92c0-116">[Type Conversion in .NET](type-conversion.md) - Describes how to convert types.</span></span>

<span data-ttu-id="f92c0-117">[在 .NET 中处理基类型](index.md) - 介绍可以对 .NET 基类型执行的常见操作。</span><span class="sxs-lookup"><span data-stu-id="f92c0-117">[Working with Base Types in .NET](index.md) - Describes common operations that you can perform on .NET base types.</span></span>


