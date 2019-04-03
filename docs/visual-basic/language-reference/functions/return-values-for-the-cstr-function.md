---
title: 返回 CStr 函数的值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819510"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="6fc45-102">返回 CStr 函数的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fc45-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="6fc45-103">下表介绍的返回值`CStr`为不同的数据类型的`expression`。</span><span class="sxs-lookup"><span data-stu-id="6fc45-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="6fc45-104">如果`expression`类型是</span><span class="sxs-lookup"><span data-stu-id="6fc45-104">If `expression` type is</span></span>|<span data-ttu-id="6fc45-105">`CStr` 返回</span><span class="sxs-lookup"><span data-stu-id="6fc45-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="6fc45-106">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="6fc45-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="6fc45-107">包含"True"或者"False"。</span><span class="sxs-lookup"><span data-stu-id="6fc45-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="6fc45-108">Date 数据类型</span><span class="sxs-lookup"><span data-stu-id="6fc45-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="6fc45-109">一个字符串，包含`Date`系统的短日期格式的值 （日期和时间）。</span><span class="sxs-lookup"><span data-stu-id="6fc45-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="6fc45-110">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="6fc45-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="6fc45-111">表示数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="6fc45-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="6fc45-112">CStr 和日期</span><span class="sxs-lookup"><span data-stu-id="6fc45-112">CStr and Date</span></span>  
 <span data-ttu-id="6fc45-113">`Date`类型始终包含日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="6fc45-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="6fc45-114">为进行类型转换，Visual Basic 将 1/1/0001 (年 1 月 1 年 1) 要*中性值*次为非特定值的日期，和 00:00:00 （午夜）。</span><span class="sxs-lookup"><span data-stu-id="6fc45-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="6fc45-115">`CStr` 不在生成的字符串中包括非特定值。</span><span class="sxs-lookup"><span data-stu-id="6fc45-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="6fc45-116">例如，如果您将转换`#January 1, 0001 9:30:00#`为一个字符串，则结果为"9:30:00 AM"; 禁止显示日期信息。</span><span class="sxs-lookup"><span data-stu-id="6fc45-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="6fc45-117">但是，日期信息仍会在原始`Date`值和可恢复函数如<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>。</span><span class="sxs-lookup"><span data-stu-id="6fc45-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc45-118">`CStr`函数不执行基于应用程序的当前区域性设置其转换。</span><span class="sxs-lookup"><span data-stu-id="6fc45-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="6fc45-119">若要获取特定区域性中的数字的字符串表示形式，请使用数字的`ToString(IFormatProvider)`方法。</span><span class="sxs-lookup"><span data-stu-id="6fc45-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="6fc45-120">例如，使用<xref:System.Double.ToString%2A?displayProperty=nameWithType>类型的值转换时`Double`到`String`。</span><span class="sxs-lookup"><span data-stu-id="6fc45-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc45-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fc45-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="6fc45-122">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="6fc45-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="6fc45-123">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="6fc45-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="6fc45-124">Date 数据类型</span><span class="sxs-lookup"><span data-stu-id="6fc45-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
