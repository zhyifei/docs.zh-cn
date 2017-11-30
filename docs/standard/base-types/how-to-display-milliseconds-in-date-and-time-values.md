---
title: "如何：显示日期和时间值中的毫秒"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="f1c87-102">如何：显示日期和时间值中的毫秒</span><span class="sxs-lookup"><span data-stu-id="f1c87-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="f1c87-103">默认日期和时间格式设置方法，如<xref:System.DateTime.ToString?displayProperty=nameWithType>，包括小时、 分钟和秒的时间值，但排除它的毫秒部分。</span><span class="sxs-lookup"><span data-stu-id="f1c87-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="f1c87-104">本主题说明如何在格式化日期和时间字符串中包含日期和时间的毫秒部分。</span><span class="sxs-lookup"><span data-stu-id="f1c87-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="f1c87-105">显示的 DateTime 值的毫秒部分</span><span class="sxs-lookup"><span data-stu-id="f1c87-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="f1c87-106">如果要使用日期的字符串表示形式，请使用静态 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 方法将其转换为 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="f1c87-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="f1c87-107">若要提取的字符串表示形式时间的毫秒组成部分，请调用日期和时间值的<xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>或<xref:System.DateTimeOffset.ToString%2A>方法，并传入`fff`或`FFF`单独使用或与其他自定义格式的自定义格式模式说明符作为`format`参数。</span><span class="sxs-lookup"><span data-stu-id="f1c87-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1c87-108">示例</span><span class="sxs-lookup"><span data-stu-id="f1c87-108">Example</span></span>  
 <span data-ttu-id="f1c87-109">该示例显示的毫秒数部分<xref:System.DateTime>和<xref:System.DateTimeOffset>到控制台，单独与在较长的日期和时间字符串中提供的值。</span><span class="sxs-lookup"><span data-stu-id="f1c87-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="f1c87-110">`fff` 格式模式包含毫秒值中的任何尾随零。</span><span class="sxs-lookup"><span data-stu-id="f1c87-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="f1c87-111">`FFF` 格式模式禁止显示它们。</span><span class="sxs-lookup"><span data-stu-id="f1c87-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="f1c87-112">下面的示例阐释了差异。</span><span class="sxs-lookup"><span data-stu-id="f1c87-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="f1c87-113">与定义包含日期和时间的毫秒部分的完整自定义格式说明符有关的一个问题在于，它定义可能与应用程序当前区域性中的时间元素排列不对应的硬编码格式。</span><span class="sxs-lookup"><span data-stu-id="f1c87-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="f1c87-114">更好的选择是要检索的某个日期和时间定义由当前区域性的显示模式<xref:System.Globalization.DateTimeFormatInfo>对象，并修改它以包含毫秒。</span><span class="sxs-lookup"><span data-stu-id="f1c87-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="f1c87-115">该示例也阐释了这种方法。</span><span class="sxs-lookup"><span data-stu-id="f1c87-115">The example also illustrates this approach.</span></span> <span data-ttu-id="f1c87-116">它检索当前区域性的完整的日期和时间模式从<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>属性，然后将自定义模式`.ffff`其秒钟模式后面。</span><span class="sxs-lookup"><span data-stu-id="f1c87-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="f1c87-117">请注意，该示例使用正则表达式在单个方法调用中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f1c87-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="f1c87-118">还可以使用自定义格式说明符来显示毫秒之外的秒的小数部分。</span><span class="sxs-lookup"><span data-stu-id="f1c87-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="f1c87-119">例如，`f` 或 `F` 自定义格式说明符显示十分之几秒，`ff` 或 `FF` 自定义格式说明符显示百分之几秒，`ffff` 或 `FFFF` 自定义格式说明符显示万分之几秒。</span><span class="sxs-lookup"><span data-stu-id="f1c87-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="f1c87-120">毫秒的小数部分在返回的字符串中会进行截断而不是舍入。</span><span class="sxs-lookup"><span data-stu-id="f1c87-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="f1c87-121">下面的示例中使用了这些格式说明符。</span><span class="sxs-lookup"><span data-stu-id="f1c87-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="f1c87-122">可以显示秒的非常小的小数单位，如万分之几秒或十万分之几秒。</span><span class="sxs-lookup"><span data-stu-id="f1c87-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="f1c87-123">但是，这些值可能没有意义。</span><span class="sxs-lookup"><span data-stu-id="f1c87-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="f1c87-124">日期和时间值的精度取决于系统时钟的分辨率。</span><span class="sxs-lookup"><span data-stu-id="f1c87-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="f1c87-125">在 Windows NT 3.5 和更高版本，和[!INCLUDE[windowsver](../../../includes/windowsver-md.md)]操作系统上，时钟的分辨率为大约 10-15 毫秒。</span><span class="sxs-lookup"><span data-stu-id="f1c87-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1c87-126">编译代码</span><span class="sxs-lookup"><span data-stu-id="f1c87-126">Compiling the Code</span></span>  
 <span data-ttu-id="f1c87-127">在命令行上使用 csc.exe 或 vb.exe 代码编译。</span><span class="sxs-lookup"><span data-stu-id="f1c87-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="f1c87-128">若要编译中的代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，将其放入控制台应用程序项目模板。</span><span class="sxs-lookup"><span data-stu-id="f1c87-128">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c87-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c87-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="f1c87-130">Custom Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="f1c87-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
