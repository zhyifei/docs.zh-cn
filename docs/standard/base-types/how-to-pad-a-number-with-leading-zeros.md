---
title: "如何：用前导零填充数字"
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
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6266807a01e8119ae1410a1ba09cab55c788b4d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="11960-102">如何：用前导零填充数字</span><span class="sxs-lookup"><span data-stu-id="11960-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="11960-103">通过结合使用“D”[标准数字格式字符串](../../../docs/standard/base-types/standard-numeric-format-strings.md)和精度说明符，将前导零添加到整数。</span><span class="sxs-lookup"><span data-stu-id="11960-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="11960-104">你可以通过使用[自定义数字格式字符串](../../../docs/standard/base-types/custom-numeric-format-strings.md)，将前导零添加到整数和浮点数。</span><span class="sxs-lookup"><span data-stu-id="11960-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="11960-105">本主题介绍如何通过这两种方法用前导零填充数字。</span><span class="sxs-lookup"><span data-stu-id="11960-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="11960-106">使用前导零将整数填充到特定的长度</span><span class="sxs-lookup"><span data-stu-id="11960-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="11960-107">确定整数值要显示的最小位数。</span><span class="sxs-lookup"><span data-stu-id="11960-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="11960-108">在此数字中包括任何前导位。</span><span class="sxs-lookup"><span data-stu-id="11960-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="11960-109">确定是要将整数显示为十进制值还是十六进制值。</span><span class="sxs-lookup"><span data-stu-id="11960-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="11960-110">若要将整数显示为十进制值，调用其`ToString(String)`方法，并传递字符串"D*n*"的值作为`format`参数，其中 *n* 表示字符串的最小长度。</span><span class="sxs-lookup"><span data-stu-id="11960-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="11960-111">若要将整数显示为十六进制值，调用其`ToString(String)`方法并传递字符串"X*n*"的值作为`format`参数，其中 *n* 表示字符串的最小长度。</span><span class="sxs-lookup"><span data-stu-id="11960-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="11960-112">你还可以使用格式字符串在方法中，如<xref:System.String.Format%2A>或<xref:System.Console.WriteLine%2A>，使用[复合格式设置](../../../docs/standard/base-types/composite-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="11960-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="11960-113">以下示例使用前导零设置若干整数值的格式，以便格式化数字的总长度至少为八个字符。</span><span class="sxs-lookup"><span data-stu-id="11960-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="11960-114">使用特定数目的前导零填充整数</span><span class="sxs-lookup"><span data-stu-id="11960-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="11960-115">确定希望整数值显示多少个前导零。</span><span class="sxs-lookup"><span data-stu-id="11960-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="11960-116">确定是要将整数显示为十进制值还是十六进制值。</span><span class="sxs-lookup"><span data-stu-id="11960-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="11960-117">将整数格式化为十进制值需要使用“D”标准格式说明符；将整数格式化为十六进制值需要使用“X”标准格式说明符。</span><span class="sxs-lookup"><span data-stu-id="11960-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="11960-118">通过调用整数值的 `ToString("D").Length` 或 `ToString("X").Length` 方法，确定未填充的数字字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="11960-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="11960-119">将你要在格式化字符串中包括的前导零的数目添加到未填充的数字字符串的长度上。</span><span class="sxs-lookup"><span data-stu-id="11960-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="11960-120">这定义了填充字符串的总长度。</span><span class="sxs-lookup"><span data-stu-id="11960-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="11960-121">调用整数值的`ToString(String)`方法，并传递字符串"D*n*"对于十进制字符串和"X*n*"对于十六进制字符串，其中 *n*表示填充的字符串的总长度。</span><span class="sxs-lookup"><span data-stu-id="11960-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="11960-122">你还可以使用"D*n*"或"X*n*"格式在支持复合格式设置的方法的字符串。</span><span class="sxs-lookup"><span data-stu-id="11960-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="11960-123">下面的示例使用五个前导零来填充整数值。</span><span class="sxs-lookup"><span data-stu-id="11960-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="11960-124">使用前导零将数值填充到特定的长度</span><span class="sxs-lookup"><span data-stu-id="11960-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="11960-125">确定数字的字符串表示形式要在小数点的左侧保留的位数。</span><span class="sxs-lookup"><span data-stu-id="11960-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="11960-126">在此总位数中包括任何前导零。</span><span class="sxs-lookup"><span data-stu-id="11960-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="11960-127">定义使用零占位符 ("0") 来表示零的最小数目的自定义数字格式字符串。</span><span class="sxs-lookup"><span data-stu-id="11960-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="11960-128">调用数字的 `ToString(String)` 方法并向其传递自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="11960-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="11960-129">也可以将自定义格式字符串与支持复合格式设置的方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="11960-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="11960-130">以下示例使用前导零设置若干数值的格式，以便格式化数字的总长度在小数点的左侧至少为八位。</span><span class="sxs-lookup"><span data-stu-id="11960-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="11960-131">使用特定数目的前导零填充数值</span><span class="sxs-lookup"><span data-stu-id="11960-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="11960-132">确定希望数值具有多少个前导零。</span><span class="sxs-lookup"><span data-stu-id="11960-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="11960-133">确定未填充数字字符串中小数点左侧的位数。</span><span class="sxs-lookup"><span data-stu-id="11960-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="11960-134">具体方法为：</span><span class="sxs-lookup"><span data-stu-id="11960-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="11960-135">确定数字的字符串表示形式是否包括小数点符号。</span><span class="sxs-lookup"><span data-stu-id="11960-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="11960-136">如果它包括小数点符号，则确定小数点左侧的字符数。</span><span class="sxs-lookup"><span data-stu-id="11960-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="11960-137">- 或 -</span><span class="sxs-lookup"><span data-stu-id="11960-137">-or-</span></span>  
  
         <span data-ttu-id="11960-138">如果它不包括小数点符号，则确定字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="11960-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="11960-139">创建一个自定义格式字符串，它为在字符串中出现的每个前导零使用零占位符（"0"），并且使用零占位符或位占位符（"#"）来表示默认字符串中的每一位。</span><span class="sxs-lookup"><span data-stu-id="11960-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="11960-140">将自定义格式字符串作为对数字的 `ToString(String)` 方法或支持复合格式设置的方法的参数提供。</span><span class="sxs-lookup"><span data-stu-id="11960-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="11960-141">下面的示例使用五个前导零来填充两个 <xref:System.Double> 值。</span><span class="sxs-lookup"><span data-stu-id="11960-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="11960-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11960-142">See Also</span></span>  
 [<span data-ttu-id="11960-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="11960-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [<span data-ttu-id="11960-144">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="11960-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="11960-145">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="11960-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
