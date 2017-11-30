---
title: "在.NET 中分析字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="76fdf-102">在.NET 中分析字符串</span><span class="sxs-lookup"><span data-stu-id="76fdf-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="76fdf-103">分析操作将表示某种 .NET 基类型的字符串转换为该基类型。</span><span class="sxs-lookup"><span data-stu-id="76fdf-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="76fdf-104">例如，分析操作用于将字符串转换为浮点数字或日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="76fdf-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="76fdf-105">最常用于执行分析操作的方法是 `Parse` 方法。</span><span class="sxs-lookup"><span data-stu-id="76fdf-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="76fdf-106">因为分析是格式设置（涉及将基类型转换为其字符串表示形式）的反向操作，所以有许多相同规则和约定适用。</span><span class="sxs-lookup"><span data-stu-id="76fdf-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="76fdf-107">正如格式设置使用实现的对象<xref:System.IFormatProvider>接口以提供实现的对象的区分区域性的格式设置信息，分析也使用<xref:System.IFormatProvider>接口来确定如何解释的字符串表示形式.</span><span class="sxs-lookup"><span data-stu-id="76fdf-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="76fdf-108">有关详细信息，请参阅[格式化类型](../../../docs/standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="76fdf-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76fdf-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="76fdf-109">In This Section</span></span>  
 [<span data-ttu-id="76fdf-110">分析数值字符串</span><span class="sxs-lookup"><span data-stu-id="76fdf-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="76fdf-111">描述如何将字符串转换为.NET 数值类型。</span><span class="sxs-lookup"><span data-stu-id="76fdf-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="76fdf-112">分析日期和时间字符串</span><span class="sxs-lookup"><span data-stu-id="76fdf-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="76fdf-113">描述如何将字符串转换为.NET **DateTime**类型。</span><span class="sxs-lookup"><span data-stu-id="76fdf-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="76fdf-114">分析其他字符串</span><span class="sxs-lookup"><span data-stu-id="76fdf-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="76fdf-115">描述如何将转换将字符串读入**Char**，**布尔**，和**枚举**类型。</span><span class="sxs-lookup"><span data-stu-id="76fdf-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="76fdf-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="76fdf-116">Related Sections</span></span>  
 [<span data-ttu-id="76fdf-117">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="76fdf-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="76fdf-118">描述基本格式设置的概念，如格式说明符和格式提供程序。</span><span class="sxs-lookup"><span data-stu-id="76fdf-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="76fdf-119">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="76fdf-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="76fdf-120">描述如何将类型转换。</span><span class="sxs-lookup"><span data-stu-id="76fdf-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="76fdf-121">基类型</span><span class="sxs-lookup"><span data-stu-id="76fdf-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="76fdf-122">描述你可以对.NET 基类型执行的常见操作。</span><span class="sxs-lookup"><span data-stu-id="76fdf-122">Describes common operations that you can perform on .NET base types.</span></span>
