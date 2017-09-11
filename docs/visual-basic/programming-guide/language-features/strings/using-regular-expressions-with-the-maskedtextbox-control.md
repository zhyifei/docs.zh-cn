---
title: "在 Visual Basic 中 MaskedTextBox 控件中使用正则表达式 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 66f61eed8bc8431392d7216ffb799b221489f332
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a><span data-ttu-id="be541-102">在 MaskedTextBox 控件中使用正则表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be541-102">Using Regular Expressions with the MaskedTextBox Control in Visual Basic</span></span>
<span data-ttu-id="be541-103">此示例演示如何转换简单的正则表达式，以使用<xref:System.Windows.Forms.MaskedTextBox>控件。</xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="be541-103">This example demonstrates how to convert simple regular expressions to work with the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
## <a name="description-of-the-masking-language"></a><span data-ttu-id="be541-104">掩码语言的说明</span><span class="sxs-lookup"><span data-stu-id="be541-104">Description of the Masking Language</span></span>  
 <span data-ttu-id="be541-105">标准<xref:System.Windows.Forms.MaskedTextBox>掩码语言取决于使用的`Masked Edit`控制[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]6.0 应该熟悉该平台中迁移的用户。</xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="be541-105">The standard <xref:System.Windows.Forms.MaskedTextBox> masking language is based on the one used by the `Masked Edit` control in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 and should be familiar to users migrating from that platform.</span></span>  
  
 <span data-ttu-id="be541-106"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性<xref:System.Windows.Forms.MaskedTextBox>控件指定要使用哪些输入的掩码。</xref:System.Windows.Forms.MaskedTextBox> </xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span><span class="sxs-lookup"><span data-stu-id="be541-106">The <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of the <xref:System.Windows.Forms.MaskedTextBox> control specifies what input mask to use.</span></span> <span data-ttu-id="be541-107">掩码必须是一个或多个从下表中的屏蔽元素构成的字符串。</span><span class="sxs-lookup"><span data-stu-id="be541-107">The mask must be a string composed of one or more of the masking elements from the following table.</span></span>  
  
|<span data-ttu-id="be541-108">屏蔽元素</span><span class="sxs-lookup"><span data-stu-id="be541-108">Masking element</span></span>|<span data-ttu-id="be541-109">描述</span><span class="sxs-lookup"><span data-stu-id="be541-109">Description</span></span>|<span data-ttu-id="be541-110">正则表达式元素</span><span class="sxs-lookup"><span data-stu-id="be541-110">Regular expression element</span></span>|  
|---------------------|-----------------|--------------------------------|  
|<span data-ttu-id="be541-111">0</span><span class="sxs-lookup"><span data-stu-id="be541-111">0</span></span>|<span data-ttu-id="be541-112">0 到 9 之间的任何单个数字。</span><span class="sxs-lookup"><span data-stu-id="be541-112">Any single digit between 0 and 9.</span></span> <span data-ttu-id="be541-113">所需的项。</span><span class="sxs-lookup"><span data-stu-id="be541-113">Entry required.</span></span>|<span data-ttu-id="be541-114">\d</span><span class="sxs-lookup"><span data-stu-id="be541-114">\d</span></span>|  
|<span data-ttu-id="be541-115">9</span><span class="sxs-lookup"><span data-stu-id="be541-115">9</span></span>|<span data-ttu-id="be541-116">数字或空格。</span><span class="sxs-lookup"><span data-stu-id="be541-116">Digit or space.</span></span> <span data-ttu-id="be541-117">可选的输入。</span><span class="sxs-lookup"><span data-stu-id="be541-117">Entry optional.</span></span>|<span data-ttu-id="be541-118">[ \d]?</span><span class="sxs-lookup"><span data-stu-id="be541-118">[ \d]?</span></span>|  
|#|<span data-ttu-id="be541-119">数字或空格。</span><span class="sxs-lookup"><span data-stu-id="be541-119">Digit or space.</span></span> <span data-ttu-id="be541-120">可选的输入。</span><span class="sxs-lookup"><span data-stu-id="be541-120">Entry optional.</span></span> <span data-ttu-id="be541-121">如果此位置为空掩码中，它将呈现为一个空格。</span><span class="sxs-lookup"><span data-stu-id="be541-121">If this position is left blank in the mask, it will be rendered as a space.</span></span> <span data-ttu-id="be541-122">加号 （+） 和减号 （-） 允许符号。</span><span class="sxs-lookup"><span data-stu-id="be541-122">Plus (+) and minus (-) signs are allowed.</span></span>|<span data-ttu-id="be541-123">[ \d+-]?</span><span class="sxs-lookup"><span data-stu-id="be541-123">[ \d+-]?</span></span>|  
|<span data-ttu-id="be541-124">L</span><span class="sxs-lookup"><span data-stu-id="be541-124">L</span></span>|<span data-ttu-id="be541-125">ASCII 字母。</span><span class="sxs-lookup"><span data-stu-id="be541-125">ASCII letter.</span></span> <span data-ttu-id="be541-126">所需的项。</span><span class="sxs-lookup"><span data-stu-id="be541-126">Entry required.</span></span>|<span data-ttu-id="be541-127">[-zA-A-z]</span><span class="sxs-lookup"><span data-stu-id="be541-127">[a-zA-Z]</span></span>|  
|<span data-ttu-id="be541-128">?</span><span class="sxs-lookup"><span data-stu-id="be541-128">?</span></span>|<span data-ttu-id="be541-129">ASCII 字母。</span><span class="sxs-lookup"><span data-stu-id="be541-129">ASCII letter.</span></span> <span data-ttu-id="be541-130">可选的输入。</span><span class="sxs-lookup"><span data-stu-id="be541-130">Entry optional.</span></span>|<span data-ttu-id="be541-131">[-zA-A-z]？</span><span class="sxs-lookup"><span data-stu-id="be541-131">[a-zA-Z]?</span></span>|  
|&|<span data-ttu-id="be541-132">字符。</span><span class="sxs-lookup"><span data-stu-id="be541-132">Character.</span></span> <span data-ttu-id="be541-133">所需的项。</span><span class="sxs-lookup"><span data-stu-id="be541-133">Entry required.</span></span>|<span data-ttu-id="be541-134">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]</span><span class="sxs-lookup"><span data-stu-id="be541-134">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]</span></span>|  
|<span data-ttu-id="be541-135">C</span><span class="sxs-lookup"><span data-stu-id="be541-135">C</span></span>|<span data-ttu-id="be541-136">字符。</span><span class="sxs-lookup"><span data-stu-id="be541-136">Character.</span></span> <span data-ttu-id="be541-137">可选的输入。</span><span class="sxs-lookup"><span data-stu-id="be541-137">Entry optional.</span></span>|<span data-ttu-id="be541-138">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]？</span><span class="sxs-lookup"><span data-stu-id="be541-138">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?</span></span>|  
|<span data-ttu-id="be541-139">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="be541-139">A</span></span>|<span data-ttu-id="be541-140">字母数字。</span><span class="sxs-lookup"><span data-stu-id="be541-140">Alphanumeric.</span></span> <span data-ttu-id="be541-141">可选的输入。</span><span class="sxs-lookup"><span data-stu-id="be541-141">Entry optional.</span></span>|<span data-ttu-id="be541-142">\W</span><span class="sxs-lookup"><span data-stu-id="be541-142">\W</span></span>|  
|<span data-ttu-id="be541-143">。</span><span class="sxs-lookup"><span data-stu-id="be541-143">.</span></span>|<span data-ttu-id="be541-144">相应于区域性的小数点占位符。</span><span class="sxs-lookup"><span data-stu-id="be541-144">Culture-appropriate decimal placeholder.</span></span>|<span data-ttu-id="be541-145">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-145">Not available.</span></span>|  
|<span data-ttu-id="be541-146">,</span><span class="sxs-lookup"><span data-stu-id="be541-146">,</span></span>|<span data-ttu-id="be541-147">相应的区域性的千位占位符。</span><span class="sxs-lookup"><span data-stu-id="be541-147">Culture-appropriate thousands placeholder.</span></span>|<span data-ttu-id="be541-148">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-148">Not available.</span></span>|  
|<span data-ttu-id="be541-149">:</span><span class="sxs-lookup"><span data-stu-id="be541-149">:</span></span>|<span data-ttu-id="be541-150">相应于区域性的时间分隔符。</span><span class="sxs-lookup"><span data-stu-id="be541-150">Culture-appropriate time separator.</span></span>|<span data-ttu-id="be541-151">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-151">Not available.</span></span>|  
|/|<span data-ttu-id="be541-152">相应于区域性的日期分隔符。</span><span class="sxs-lookup"><span data-stu-id="be541-152">Culture-appropriate date separator.</span></span>|<span data-ttu-id="be541-153">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-153">Not available.</span></span>|  
|$|<span data-ttu-id="be541-154">相应于区域性的货币符号。</span><span class="sxs-lookup"><span data-stu-id="be541-154">Culture-appropriate currency symbol.</span></span>|<span data-ttu-id="be541-155">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-155">Not available.</span></span>|  
|\<|<span data-ttu-id="be541-156">将转换为小写后面的所有字符。</span><span class="sxs-lookup"><span data-stu-id="be541-156">Converts all characters that follow to lowercase.</span></span>|<span data-ttu-id="be541-157">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-157">Not available.</span></span>|  
|>|<span data-ttu-id="be541-158">将转换为大写后面的所有字符。</span><span class="sxs-lookup"><span data-stu-id="be541-158">Converts all characters that follow to uppercase.</span></span>|<span data-ttu-id="be541-159">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-159">Not available.</span></span>|  
|<span data-ttu-id="be541-160">&#124;</span><span class="sxs-lookup"><span data-stu-id="be541-160">&#124;</span></span>|<span data-ttu-id="be541-161">撤消上一个班次向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="be541-161">Undoes a previous shift up or shift down.</span></span>|<span data-ttu-id="be541-162">不可用。</span><span class="sxs-lookup"><span data-stu-id="be541-162">Not available.</span></span>|  
|\|<span data-ttu-id="be541-163">掩码字符，将其转变为文字进行转义。</span><span class="sxs-lookup"><span data-stu-id="be541-163">Escapes a mask character, turning it into a literal.</span></span> <span data-ttu-id="be541-164">"\\\\"是一个反斜杠的转义序列。</span><span class="sxs-lookup"><span data-stu-id="be541-164">"\\\\" is the escape sequence for a backslash.</span></span>|\|  
|<span data-ttu-id="be541-165">所有其他字符。</span><span class="sxs-lookup"><span data-stu-id="be541-165">All other characters.</span></span>|<span data-ttu-id="be541-166">原义字符。</span><span class="sxs-lookup"><span data-stu-id="be541-166">Literals.</span></span> <span data-ttu-id="be541-167">所有非掩码元素将显示为自身内<xref:System.Windows.Forms.MaskedTextBox>。</xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="be541-167">All non-mask elements will appear as themselves within <xref:System.Windows.Forms.MaskedTextBox>.</span></span>|<span data-ttu-id="be541-168">所有其他字符。</span><span class="sxs-lookup"><span data-stu-id="be541-168">All other characters.</span></span>|  
  
 <span data-ttu-id="be541-169">小数点 （.），千分位 （，）、 时间 （:）、 （/）、 日期和货币 （$） 符号默认为显示这些符号由应用程序的区域性。</span><span class="sxs-lookup"><span data-stu-id="be541-169">The decimal (.), thousandths (,), time (:), date (/), and currency ($) symbols default to displaying those symbols as defined by the application's culture.</span></span> <span data-ttu-id="be541-170">您可以强制其使用显示用于另一个区域性的符号<xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>属性。</xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A></span><span class="sxs-lookup"><span data-stu-id="be541-170">You can force them to display symbols for another culture by using the <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> property.</span></span>  
  
## <a name="regular-expressions-and-masks"></a><span data-ttu-id="be541-171">正则表达式和蒙板</span><span class="sxs-lookup"><span data-stu-id="be541-171">Regular Expressions and Masks</span></span>  
 <span data-ttu-id="be541-172">尽管可以使用正则表达式和蒙板来验证用户输入，但它们并不完全相同。</span><span class="sxs-lookup"><span data-stu-id="be541-172">Although you can use regular expressions and masks to validate user input, they are not completely equivalent.</span></span> <span data-ttu-id="be541-173">正则表达式可以表示掩码，相比更复杂的模式，但更简洁地采用与区域相关的格式掩码可以表达相同的信息。</span><span class="sxs-lookup"><span data-stu-id="be541-173">Regular expressions can express more complex patterns than masks, but masks can express the same information more succinctly and in a culturally relevant format.</span></span>  
  
 <span data-ttu-id="be541-174">下表比较了每个四个正则表达式和等效的掩码。</span><span class="sxs-lookup"><span data-stu-id="be541-174">The following table compares four regular expressions and the equivalent mask for each.</span></span>  
  
|<span data-ttu-id="be541-175">正则表达式</span><span class="sxs-lookup"><span data-stu-id="be541-175">Regular Expression</span></span>|<span data-ttu-id="be541-176">掩码</span><span class="sxs-lookup"><span data-stu-id="be541-176">Mask</span></span>|<span data-ttu-id="be541-177">备注</span><span class="sxs-lookup"><span data-stu-id="be541-177">Notes</span></span>|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|<span data-ttu-id="be541-178">`/`掩码中的字符是逻辑日期分隔符，并且它将向用户显示适合于应用程序的当前区域性的日期分隔符。</span><span class="sxs-lookup"><span data-stu-id="be541-178">The `/` character in the mask is a logical date separator, and it will appear to the user as the date separator appropriate to the application's current culture.</span></span>|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|<span data-ttu-id="be541-179">在其中三个字母月份的缩写显示为首字母大写、 两个小写字母后跟与美国格式的日期 （日、 月缩写和年）。</span><span class="sxs-lookup"><span data-stu-id="be541-179">A date (day, month abbreviation, and year) in United States format in which the three-letter month abbreviation is displayed with an initial uppercase letter followed by two lowercase letters.</span></span>|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|<span data-ttu-id="be541-180">美国电话号码，区号为可选项。</span><span class="sxs-lookup"><span data-stu-id="be541-180">United States phone number, area code optional.</span></span> <span data-ttu-id="be541-181">如果用户不希望输入的可选字符，她可以输入空格，或将鼠标指针放直接由第一个 0 表示掩码中的位置。</span><span class="sxs-lookup"><span data-stu-id="be541-181">If the user does not wish to enter the optional characters, she can either enter spaces or place the mouse pointer directly at the position in the mask represented by the first 0.</span></span>|  
|`$\d{6}.00`|`$999,999.00`|<span data-ttu-id="be541-182">0 到 999999 的范围中的货币值。</span><span class="sxs-lookup"><span data-stu-id="be541-182">A currency value in the range of 0 to 999999.</span></span> <span data-ttu-id="be541-183">货币、 千分位和十进制字符将替换在运行时它们特定于区域性的等效项。</span><span class="sxs-lookup"><span data-stu-id="be541-183">The currency, thousandth, and decimal characters will be replaced at run-time with their culture-specific equivalents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be541-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be541-184">See Also</span></span>  
 <span data-ttu-id="be541-185"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A></xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span><span class="sxs-lookup"><span data-stu-id="be541-185"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span></span>   
 <span data-ttu-id="be541-186"><xref:System.Windows.Forms.MaskedTextBox></xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="be541-186"><xref:System.Windows.Forms.MaskedTextBox></span></span>   
<span data-ttu-id="be541-187"> [验证在 Visual Basic 中的字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md) </span><span class="sxs-lookup"><span data-stu-id="be541-187"> [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md) </span></span>  
<span data-ttu-id="be541-188"> [MaskedTextBox 控件](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)</span><span class="sxs-lookup"><span data-stu-id="be541-188"> [MaskedTextBox Control](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)</span></span>
