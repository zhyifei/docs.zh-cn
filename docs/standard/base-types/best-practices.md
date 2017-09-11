---
title: "正则表达式最佳实践"
description: "正则表达式最佳实践"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cf9c83de791fa4990a991689a26d4bbdd84cfe7d
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="best-practices-for-regular-expressions"></a><span data-ttu-id="9a0d3-104">正则表达式最佳实践</span><span class="sxs-lookup"><span data-stu-id="9a0d3-104">Best practices for regular expressions</span></span>

<span data-ttu-id="9a0d3-105">.NET 中的正则表达式引擎是一种功能强大而齐全的工具，它基于模式匹配（而不是比较和匹配文本）来处理文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-105">The regular expression engine in .NET is a powerful, full-featured tool that processes text based on pattern matches rather than on comparing and matching literal text.</span></span> <span data-ttu-id="9a0d3-106">在大多数情况下，它可以快速、高效地执行模式匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-106">In most cases, it performs pattern matching rapidly and efficiently.</span></span> <span data-ttu-id="9a0d3-107">但在某些情况下，正则表达式引擎的速度似乎很慢。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-107">However, in some cases, the regular expression engine can appear to be very slow.</span></span> <span data-ttu-id="9a0d3-108">在极端情况下，它甚至看似停止响应，因为它会用若干个小时甚至若干天处理相对小的输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-108">In extreme cases, it can even appear to stop responding as it processes a relatively small input over the course of hours or even days.</span></span> 

<span data-ttu-id="9a0d3-109">本主题概述开发人员为了确保其正则表达式实现最佳性能可以采纳的一些最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-109">This topic outlines some of the best practices that developers can adopt to ensure that their regular expressions achieve optimal performance.</span></span> <span data-ttu-id="9a0d3-110">它包含下列部分：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-110">It contains the following sections:</span></span>

* [<span data-ttu-id="9a0d3-111">考虑输入源</span><span class="sxs-lookup"><span data-stu-id="9a0d3-111">Consider the input source</span></span>](#consider-the-input-source)

* [<span data-ttu-id="9a0d3-112">适当处理对象实例化</span><span class="sxs-lookup"><span data-stu-id="9a0d3-112">Handle object instantiation appropriately</span></span>](#handle-object-instantiation-appropriately)

* [<span data-ttu-id="9a0d3-113">控制回溯</span><span class="sxs-lookup"><span data-stu-id="9a0d3-113">Take charge of backtracking</span></span>](#take-charge-of-backtracking)

* [<span data-ttu-id="9a0d3-114">使用超时值</span><span class="sxs-lookup"><span data-stu-id="9a0d3-114">Use time-out values</span></span>](#use-time-out-values)

* [<span data-ttu-id="9a0d3-115">只在必要时捕获</span><span class="sxs-lookup"><span data-stu-id="9a0d3-115">Capture only when necessary</span></span>](#capture-only-when-necessary)

* [<span data-ttu-id="9a0d3-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a0d3-116">Related topics</span></span>](#related-topics)

## <a name="consider-the-input-source"></a><span data-ttu-id="9a0d3-117">考虑输入源</span><span class="sxs-lookup"><span data-stu-id="9a0d3-117">Consider the input source</span></span>

<span data-ttu-id="9a0d3-118">通常，正则表达式可接受两种类型的输入：受约束的输入或不受约束的输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-118">In general, regular expressions can accept two types of input: constrained or unconstrained.</span></span> <span data-ttu-id="9a0d3-119">受约束的输入是源自已知或可靠的源并遵循预定义格式的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-119">Constrained input is text that originates from a known or reliable source and follows a predefined format.</span></span> <span data-ttu-id="9a0d3-120">不受约束的输入是源自不可靠的源（如 Web 用户）并且可能不遵循预定义或预期格式的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-120">Unconstrained input is text that originates from an unreliable source, such as a web user, and may not follow a predefined or expected format.</span></span>

<span data-ttu-id="9a0d3-121">编写的正则表达式模式的目的通常是匹配有效输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-121">Regular expression patterns are typically written to match valid input.</span></span> <span data-ttu-id="9a0d3-122">也就是说，开发人员检查他们要匹配的文本，然后编写与其匹配的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-122">That is, developers examine the text that they want to match and then write a regular expression pattern that matches it.</span></span> <span data-ttu-id="9a0d3-123">然后，开发人员使用多个有效输入项进行测试，以确定此模式是否需要更正或进一步细化。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-123">Developers then determine whether this pattern requires correction or further elaboration by testing it with multiple valid input items.</span></span> <span data-ttu-id="9a0d3-124">当模式可匹配所有假定的有效输入时，则将其声明为生产就绪并且可包括在发布的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-124">When the pattern matches all presumed valid inputs, it is declared to be production-ready and can be included in a released application.</span></span> <span data-ttu-id="9a0d3-125">这使得正则表达式模式适合匹配受约束的输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-125">This makes a regular expression pattern suitable for matching constrained input.</span></span> <span data-ttu-id="9a0d3-126">但它不适合匹配不受约束的输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-126">However, it does not make it suitable for matching unconstrained input.</span></span>

<span data-ttu-id="9a0d3-127">若要匹配不受约束的输入，正则表达式必须能够高效处理以下三种文本：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-127">To match unconstrained input, a regular expression must be able to efficiently handle three kinds of text:</span></span>

<span data-ttu-id="9a0d3-128">• 与正则表达式模式匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-128">• Text that matches the regular expression pattern.</span></span>

<span data-ttu-id="9a0d3-129">• 与正则表达式模式不匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-129">• Text that does not match the regular expression pattern.</span></span>

<span data-ttu-id="9a0d3-130">• 与正则表达式模式大致匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-130">• Text that nearly matches the regular expression pattern.</span></span>

<span data-ttu-id="9a0d3-131">对于为了处理受约束的输入而编写的正则表达式，最后一种文本类型尤其存在问题。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-131">The last text type is especially problematic for a regular expression that has been written to handle constrained input.</span></span> <span data-ttu-id="9a0d3-132">如果该正则表达式还依赖大量[回溯](backtracking.md)，则正则表达式引擎可能会花费大量时间（在有些情况下，需要许多个小时或许多天）来处理看似无害的文本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-132">If that regular expression also relies on extensive [backtracking](backtracking.md), the regular expression engine can spend an inordinate amount of time (in some cases, many hours or days) processing seemingly innocuous text.</span></span> 

> [!WARNING]
> <span data-ttu-id="9a0d3-133">下面的示例使用容易过度回溯并可能拒绝有效电子邮件地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-133">The following example uses a regular expression that is prone to excessive backtracking and that is likely to reject valid email addresses.</span></span> <span data-ttu-id="9a0d3-134">不应在电子邮件验证例程中使用。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-134">You should not use it in an email validation routine.</span></span> <span data-ttu-id="9a0d3-135">如果需要用于验证电子邮件地址的正则表达式，请参阅[如何：确认字符串是有效的电子邮件格式](verify-format.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-135">If you would like a regular expression that validates email addresses, see [How to: Verify that strings are in valid email format](verify-format.md).</span></span> 


<span data-ttu-id="9a0d3-136">例如，考虑一种很常用但很有问题的用于验证电子邮件地址别名的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-136">For example, consider a very commonly used but extremely problematic regular expression for validating the alias of an email address.</span></span> <span data-ttu-id="9a0d3-137">编写正则表达式 `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` 的目的是处理被视为有效的电子邮件地址，该地址包含一个字母数字字符，后跟零个或多个可为字母数字、句点或连字符的字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-137">The regular expression `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` is written to process what is considered to be a valid email address, which consists of an alphanumeric character, followed by zero or more characters that can be alphanumeric, periods, or hyphens.</span></span> <span data-ttu-id="9a0d3-138">该正则表达式必须以字母数字字符结束。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-138">The regular expression must end with an alphanumeric character.</span></span> <span data-ttu-id="9a0d3-139">但正如下面的示例所示，尽管此正则表达式可以轻松处理有效输入，但在处理接近有效的输入时性能非常低效。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-139">However, as the following example shows, although this regular expression handles valid input easily, its performance is very inefficient when it is processing nearly valid input.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

<span data-ttu-id="9a0d3-140">如该示例输出所示，正则表达式引擎处理有效电子邮件别名的时间间隔大致相同，与其长度无关。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-140">As the output from the example shows, the regular expression engine processes the valid email alias in about the same time interval regardless of its length.</span></span> <span data-ttu-id="9a0d3-141">另一方面，当接近有效的电子邮件地址包含五个以上字符时，字符串中每增加一个字符，处理时间会大约增加一倍。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-141">On the other hand, when the nearly valid email address has more than five characters, processing time approximately doubles for each additional character in the string.</span></span> <span data-ttu-id="9a0d3-142">这意味着，处理接近有效的 28 个字符构成的字符串将需要一个小时，处理接近有效的 33 个字符构成的字符串将需要接近一天的时间。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-142">This means that a nearly valid 28-character string would take over an hour to process, and a nearly valid 33-character string would take nearly a day to process.</span></span> 

<span data-ttu-id="9a0d3-143">由于开发此正则表达式时只考虑了要匹配的输入的格式，因此未能考虑与模式不匹配的输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-143">Because this regular expression was developed solely by considering the format of input to be matched, it fails to take account of input that does not match the pattern.</span></span> <span data-ttu-id="9a0d3-144">这反过来会使与正则表达式模式近似匹配的不受约束输入的性能显著降低。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-144">This, in turn, can allow unconstrained input that nearly matches the regular expression pattern to significantly degrade performance.</span></span>

<span data-ttu-id="9a0d3-145">若要解决此问题，可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-145">To solve this problem, you can do the following:</span></span>

* <span data-ttu-id="9a0d3-146">开发模式时，应考虑回溯对正则表达式引擎的性能的影响程度，特别是当正则表达式设计用于处理不受约束的输入时。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-146">When developing a pattern, you should consider how backtracking might affect the performance of the regular expression engine, particularly if your regular expression is designed to process unconstrained input.</span></span> <span data-ttu-id="9a0d3-147">有关详细信息，请参阅[控制回溯](#take-charge-of-backtracking)部分。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-147">For more information, see the [Take charge of backtracking](#take-charge-of-backtracking) section.</span></span>

* <span data-ttu-id="9a0d3-148">使用无效输入、接近有效的输入以及有效输入对正则表达式进行完全测试。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-148">Thoroughly test your regular expression using invalid and near-valid input as well as valid input.</span></span> <span data-ttu-id="9a0d3-149">若要为特定正则表达式随机生成输入，可以使用 [Rex](http://research.microsoft.com/en-us/projects/rex/)，这是 Microsoft Research 提供的正则表达式探索工具。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-149">To generate input for a particular regular expression randomly, you can use [Rex](http://research.microsoft.com/en-us/projects/rex/), which is a regular expression exploration tool from Microsoft Research.</span></span>

## <a name="handle-object-instantiation-appropriately"></a><span data-ttu-id="9a0d3-150">适当处理对象实例化</span><span class="sxs-lookup"><span data-stu-id="9a0d3-150">Handle object instantiation appropriately</span></span>

<span data-ttu-id="9a0d3-151">.NET 的正则表达式对象模型的核心是 [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) 类，它表示正则表达式引擎。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-151">At the heart of .NET’s regular expression object model is the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) class, which represents the regular expression engine.</span></span> <span data-ttu-id="9a0d3-152">通常，影响正则表达式性能的单个最大因素是 [Regex](xref:System.Text.RegularExpressions.Regex) 引擎的使用方式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-152">Often, the single greatest factor that affects regular expression performance is the way in which the [Regex](xref:System.Text.RegularExpressions.Regex) engine is used.</span></span> <span data-ttu-id="9a0d3-153">定义正则表达式需要将正则表达式引擎与正则表达式模式紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-153">Defining a regular expression involves tightly coupling the regular expression engine with a regular expression pattern.</span></span> <span data-ttu-id="9a0d3-154">无论该耦合过程是需要通过向其构造函数传递正则表达式模式来实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象还是通过向其传递正则表达式模式和要分析的字符串来调用静态方法，都必然会消耗大量资源。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-154">That coupling process, whether it involves instantiating a [Regex](xref:System.Text.RegularExpressions.Regex) object by passing its constructor a regular expression pattern or calling a static method by passing it the regular expression pattern along with the string to be analyzed, is by necessity an expensive one.</span></span>

<span data-ttu-id="9a0d3-155">可将正则表达式引擎与特定正则表达式模式耦合，然后使用该引擎以若干种方式匹配文本：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-155">You can couple the regular expression engine with a particular regular expression pattern and then use the engine to match text in several ways:</span></span>

* <span data-ttu-id="9a0d3-156">可以调用静态模式匹配方法，如 [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String))。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-156">You can call a static pattern-matching method, such as [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span></span> <span data-ttu-id="9a0d3-157">这不需要实例化正则表达式对象。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-157">This does not require instantiation of a regular expression object.</span></span>

* <span data-ttu-id="9a0d3-158">可以实例化一个 [Regex](xref:System.Text.RegularExpressions.Regex) 对象并调用已解释的正则表达式的实例模式匹配方法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-158">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of an interpreted regular expression.</span></span> <span data-ttu-id="9a0d3-159">这是将正则表达式引擎绑定到正则表达式模式的默认方法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-159">This is the default method for binding the regular expression engine to a regular expression pattern.</span></span> <span data-ttu-id="9a0d3-160">如果实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象时未使用包含 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 标志的 options 自变量，则会生成此方法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-160">It results when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated without an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

* <span data-ttu-id="9a0d3-161">可以实例化一个 [Regex](xref:System.Text.RegularExpressions.Regex) 对象并调用已编译的正则表达式的实例模式匹配方法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-161">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of a compiled regular expression.</span></span> <span data-ttu-id="9a0d3-162">当使用包括 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 标志的 options 自变量实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象时，正则表达式对象表示已编译的模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-162">Regular expression objects represent compiled patterns when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated with an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a0d3-163">如果方法调用中重复使用同一正则表达式或者应用程序大量使用正则表达式对象，则方法调用的形式（静态、已解释、已编译）会影响性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-163">The form of the method call (static, interpreted, compiled) affects performance if the same regular expression is used repeatedly in method calls, or if an application makes extensive use of regular expression objects.</span></span>
 
### <a name="static-regular-expressions"></a><span data-ttu-id="9a0d3-164">静态正则表达式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-164">Static regular expressions</span></span>

<span data-ttu-id="9a0d3-165">建议将静态正则表达式方法用作使用同一正则表达式重复实例化正则表达式对象的替代方法。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-165">Static regular expression methods are recommended as an alternative to repeatedly instantiating a regular expression object with the same regular expression.</span></span> <span data-ttu-id="9a0d3-166">与正则表达式对象使用的正则表达式模式不同，实例方法调用所使用的模式中的操作代码或已编译的 Microsoft 中间语言 (MSIL) 由正则表达式引擎缓存在内部。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-166">Unlike regular expression patterns used by regular expression objects, either the operation codes or the compiled Microsoft intermediate language (MSIL) from patterns used in instance method calls is cached internally by the regular expression engine.</span></span> 

<span data-ttu-id="9a0d3-167">例如，你可能会调用某个方法来验证用户输入。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-167">For example, you might call a method to validate user input.</span></span> <span data-ttu-id="9a0d3-168">在此示例中，名为 `IsValidCurrency` 的方法将检查用户是否输入了后跟至少一个十进制数的货币符号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-168">In this example, a method named `IsValidCurrency` checks whether the user has entered a currency symbol followed by at least one decimal digit.</span></span> <span data-ttu-id="9a0d3-169">下面的示例显示 `IsValidCurrency` 方法的一个非常低效的实现。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-169">A very inefficient implementation of the `IsValidCurrency` method is shown in the following example.</span></span> <span data-ttu-id="9a0d3-170">请注意，每个方法调用使用相同模式重新实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-170">Note that each method call reinstantiates a [Regex](xref:System.Text.RegularExpressions.Regex) object with the same pattern.</span></span> <span data-ttu-id="9a0d3-171">这反过来意味着，每次调用该方法时，都必须重新编译正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-171">This, in turn, means that the regular expression pattern must be recompiled each time the method is called.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

<span data-ttu-id="9a0d3-172">应将此低效代码替换为对静态 [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-172">You should replace this inefficient code with a call to the static [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) method.</span></span> <span data-ttu-id="9a0d3-173">这样便不必在每次要调用模式匹配方法时都实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象，还允许正则表达式引擎从其缓存中检索正则表达式的已编译版本。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-173">This eliminates the need to instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object each time you want to call a pattern-matching method, and enables the regular expression engine to retrieve a compiled version of the regular expression from its cache.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

<span data-ttu-id="9a0d3-174">默认情况下，将缓存最后 15 个最近使用的静态正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-174">By default, the last 15 most recently used static regular expression patterns are cached.</span></span> <span data-ttu-id="9a0d3-175">对于需要大量已缓存的静态正则表达式的应用程序，可通过设置 [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) 属性来调整缓存大小。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-175">For applications that require a larger number of cached static regular expressions, the size of the cache can be adjusted by setting the [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) property.</span></span>

<span data-ttu-id="9a0d3-176">此示例中使用的正则表达式 `\p{Sc}+\s*\d+` 可验证输入字符串是否包含一个货币符号和至少一个十进制数。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-176">The regular expression `\p{Sc}+\s*\d+` that is used in this example verifies that the input string consists of a currency symbol and at least one decimal digit.</span></span> <span data-ttu-id="9a0d3-177">模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-177">The pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="9a0d3-178">模式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-178">Pattern</span></span> | <span data-ttu-id="9a0d3-179">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-179">Description</span></span>
------- | -----------
`\p{Sc}+` | <span data-ttu-id="9a0d3-180">与 Unicode 符号、货币类别中的一个或多个字符匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-180">Match one or more characters in the Unicode Symbol, Currency category.</span></span>
`\s*` | <span data-ttu-id="9a0d3-181">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-181">Match zero or more white-space characters.</span></span>
`\d+` | <span data-ttu-id="9a0d3-182">匹配一个或多个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-182">Match one or more decimal digits.</span></span>
 
### <a name="interpreted-vs-compiled-regular-expressions"></a><span data-ttu-id="9a0d3-183">已解释与已编译的正则表达式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-183">Interpreted vs. compiled regular expressions</span></span>

<span data-ttu-id="9a0d3-184">将解释未通过 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 选项的规范绑定到正则表达式引擎的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-184">Regular expression patterns that are not bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are interpreted.</span></span> <span data-ttu-id="9a0d3-185">在实例化正则表达式对象时，正则表达式引擎会将正则表达式转换为一组操作代码。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-185">When a regular expression object is instantiated, the regular expression engine converts the regular expression to a set of operation codes.</span></span> <span data-ttu-id="9a0d3-186">调用实例方法时，操作代码会转换为 MSIL 并由 JIT 编译器执行。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-186">When an instance method is called, the operation codes are converted to MSIL and executed by the JIT compiler.</span></span> <span data-ttu-id="9a0d3-187">同样，当调用一种静态正则表达式方法并且在缓存中找不到该正则表达式时，正则表达式引擎会将该正则表达式转换为一组操作代码并将其存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-187">Similarly, when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to a set of operation codes and stores them in the cache.</span></span> <span data-ttu-id="9a0d3-188">然后，它将这些操作代码转换为 MSIL，以便于 JIT 编译器执行。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-188">It then converts these operation codes to MSIL so that the JIT compiler can execute them.</span></span> <span data-ttu-id="9a0d3-189">已解释的正则表达式会减少启动时间，但会使执行速度变慢。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-189">Interpreted regular expressions reduce startup time at the cost of slower execution time.</span></span> <span data-ttu-id="9a0d3-190">因此，在少数方法调用中使用正则表达式时或调用正则表达式方法的确切数量未知但预期很小时，使用已解释的正则表达式的效果最佳。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-190">Because of this, they are best used when the regular expression is used in a small number of method calls, or if the exact number of calls to regular expression methods is unknown but is expected to be small.</span></span> <span data-ttu-id="9a0d3-191">随着方法调用数量的增加，执行速度变慢对性能的影响会超过减少启动时间带来的性能改进。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-191">As the number of method calls increases, the performance gain from reduced startup time is outstripped by the slower execution speed.</span></span>

<span data-ttu-id="9a0d3-192">将编译未通过 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 选项的规范绑定到正则表达式引擎的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-192">Regular expression patterns that are bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are compiled.</span></span> <span data-ttu-id="9a0d3-193">这意味着，当实例化正则表达式对象时或当调用一种静态正则表达式方法并且在缓存中找不到该正则表达式时，正则表达式引擎会将该正则表达式转换为一组中间操作代码，这些代码之后会转换为 MSIL。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-193">This means that, when a regular expression object is instantiated, or when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to an intermediary set of operation codes, which it then converts to MSIL.</span></span> <span data-ttu-id="9a0d3-194">调用方法时，JIT 编译器将执行该 MSIL。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-194">When a method is called, the JIT compiler executes the MSIL.</span></span> <span data-ttu-id="9a0d3-195">与已解释的正则表达式相比，已编译的正则表达式增加了启动时间，但执行各种模式匹配方法的速度更快。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-195">In contrast to interpreted regular expressions, compiled regular expressions increase startup time but execute individual pattern-matching methods faster.</span></span> <span data-ttu-id="9a0d3-196">因此，相对于调用的正则表达式方法的数量，因编译正则表达式而产生的性能产生了改进。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-196">As a result, the performance benefit that results from compiling the regular expression increases in proportion to the number of regular expression methods called.</span></span>

<span data-ttu-id="9a0d3-197">简言之，当你使用特定正则表达式调用正则表达式方法相对不频繁时，建议使用已解释的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-197">To summarize, we recommend that you use interpreted regular expressions when you call regular expression methods with a specific regular expression relatively infrequently.</span></span> <span data-ttu-id="9a0d3-198">当你使用特定正则表达式调用正则表达式方法相对频繁时，应使用已编译的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-198">You should use compiled regular expressions when you call regular expression methods with a specific regular expression relatively frequently.</span></span> <span data-ttu-id="9a0d3-199">很难确定已解释的正则表达式执行速度减慢超出启动时间减少带来的性能增益的确切阈值，或已编译的正则表达式启动速度减慢超出执行速度加快带来的性能增益的阈值。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-199">The exact threshold at which the slower execution speeds of interpreted regular expressions outweigh gains from their reduced startup time, or the threshold at which the slower startup times of compiled regular expressions outweigh gains from their faster execution speeds, is difficult to determine.</span></span> <span data-ttu-id="9a0d3-200">这依赖于各种因素，包括正则表达式的复杂程度和它处理的特定数据。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-200">It depends on a variety of factors, including the complexity of the regular expression and the specific data that it processes.</span></span> <span data-ttu-id="9a0d3-201">若要确定已解释或已编译的正则表达式是否可为特定应用程序方案提供最佳性能，可以使用 [Stopwatch](xref:System.Diagnostics.Stopwatch) 类来比较其执行时间。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-201">To determine whether interpreted or compiled regular expressions offer the best performance for your particular application scenario, you can use the [Stopwatch](xref:System.Diagnostics.Stopwatch) class to compare their execution times.</span></span>

<span data-ttu-id="9a0d3-202">下面的示例在阅读 Theodore Dreiser 的《金融家》中的前十个句子和阅读所有句子时比较已编译和已解释的正则表达式的性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-202">The following example compares the performance of compiled and interpreted regular expressions when reading the first ten sentences and when reading all the sentences in the text of Theodore Dreiser's The Financier.</span></span> <span data-ttu-id="9a0d3-203">如示例输出所示，当只对匹配方法的正则表达式进行十次调用时，已解释的正则表达式与已编译的正则表达式相比，可提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-203">As the output from the example shows, when only ten calls are made to regular expression matching methods, an interpreted regular expression offers better performance than a compiled regular expression.</span></span> <span data-ttu-id="9a0d3-204">但是，当进行大量调用（在此示例中，超过 13,000 次调用）时，已编译的正则表达式可提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-204">However, a compiled regular expression offers better performance when a large number of calls (in this case, over 13,000) are made.</span></span> 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

<span data-ttu-id="9a0d3-205">该示例中使用的正则表达式模式 `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-205">The regular expression pattern used in the example, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, is defined as shown in the following table.</span></span>

<span data-ttu-id="9a0d3-206">模式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-206">Pattern</span></span> | <span data-ttu-id="9a0d3-207">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-207">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="9a0d3-208">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-208">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="9a0d3-209">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-209">Match one or more word characters.</span></span>
<span data-ttu-id="9a0d3-210">\`(\r?\n)</span><span class="sxs-lookup"><span data-stu-id="9a0d3-210">\`(\r?\n)</span></span>|<span data-ttu-id="9a0d3-211">,?\s)\`</span><span class="sxs-lookup"><span data-stu-id="9a0d3-211">,?\s)\`</span></span> | <span data-ttu-id="9a0d3-212">匹配零个或一个回车符后跟一个换行符，或零个或一个逗号后跟一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-212">Match either zero or one carriage return followed by a newline character, or zero or one comma followed by a white-space character.</span></span>
<span data-ttu-id="9a0d3-213">\`(\w+((\r?\n)</span><span class="sxs-lookup"><span data-stu-id="9a0d3-213">\`(\w+((\r?\n)</span></span>|<span data-ttu-id="9a0d3-214">,?\s))*\`</span><span class="sxs-lookup"><span data-stu-id="9a0d3-214">,?\s))*\`</span></span> | <span data-ttu-id="9a0d3-215">匹配一个或多个单词字符的零个或多个事例，后跟零个或一个回车符和换行符，或后跟零个或一个逗号、一个空格字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-215">Match zero or more occurrences of one or more word characters that are followed either by zero or one carriage return and a newline character, or by zero or one comma followed by a white-space character.</span></span>
`\w+` | <span data-ttu-id="9a0d3-216">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-216">Match one or more word characters.</span></span>
`[.?:;!]` | <span data-ttu-id="9a0d3-217">匹配句号、问号、冒号、分号或感叹号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-217">Match a period, question mark, colon, semicolon, or exclamation point.</span></span>
 
## <a name="take-charge-of-backtracking"></a><span data-ttu-id="9a0d3-218">控制回溯</span><span class="sxs-lookup"><span data-stu-id="9a0d3-218">Take charge of backtracking</span></span>

<span data-ttu-id="9a0d3-219">通常，正则表达式引擎使用线性进度在输入字符串中移动并将其编译为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-219">Ordinarily, the regular expression engine uses linear progression to move through an input string and compare it to a regular expression pattern.</span></span> <span data-ttu-id="9a0d3-220">但是，当在正则表达式模式中使用不确定限定符（如 __*__、**+** 和 **?**）时，</span><span class="sxs-lookup"><span data-stu-id="9a0d3-220">However, when indeterminate quantifiers such as __*__, **+**, and **?**</span></span> <span data-ttu-id="9a0d3-221">正则表达式引擎可能会放弃一部分成功的分部匹配，并返回以前保存的状态，以便为整个模式搜索成功匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-221">are used in a regular expression pattern, the regular expression engine may give up a portion of successful partial matches and return to a previously saved state in order to search for a successful match for the entire pattern.</span></span> <span data-ttu-id="9a0d3-222">此过程称为回溯。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-222">This process is known as backtracking.</span></span>

> [!NOTE]
> <span data-ttu-id="9a0d3-223">有关回溯的详细信息，请参阅[正则表达式行为的详细信息](regex-behavior.md)和[正则表达式中的回溯](backtracking.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-223">For more information on backtracking, see [Details of regular expression behavior](regex-behavior.md) and [Backtracking in regular expressions](backtracking.md).</span></span>
 
<span data-ttu-id="9a0d3-224">支持回溯可为正则表达式提供强大的功能和灵活性。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-224">Support for backtracking gives regular expressions power and flexibility.</span></span> <span data-ttu-id="9a0d3-225">还可将控制正则表达式引擎操作的职责交给正则表达式开发人员来处理。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-225">It also places the responsibility for controlling the operation of the regular expression engine in the hands of regular expression developers.</span></span> <span data-ttu-id="9a0d3-226">由于开发人员通常不了解此职责，因此其误用回溯或依赖过多回溯通常会显著降低正则表达式的性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-226">Because developers are often not aware of this responsibility, their misuse of backtracking or reliance on excessive backtracking often plays the most significant role in degrading regular expression performance.</span></span> <span data-ttu-id="9a0d3-227">在最糟糕的情况下，输入字符串中每增加一个字符，执行时间会加倍。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-227">In a worst-case scenario, execution time can double for each additional character in the input string.</span></span> <span data-ttu-id="9a0d3-228">实际上，如果过多使用回溯，则在输入与正则表达式模式近似匹配时很容易创建无限循环的编程等效形式；正则表达式引擎可能需要几小时甚至几天来处理相对短的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-228">In fact, by using backtracking excessively, it is easy to create the programmatic equivalent of an endless loop if input nearly matches the regular expression pattern; the regular expression engine may take hours or even days to process a relatively short input string.</span></span>

<span data-ttu-id="9a0d3-229">通常，尽管回溯不是匹配所必需的，但应用程序会因使用回溯而对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-229">Often, applications pay a performance penalty for using backtracking despite the fact that backtracking is not essential for a match.</span></span> <span data-ttu-id="9a0d3-230">例如，正则表达式 `\b\p{Lu}\w*\b` 将匹配以大写字符开头的所有单词，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-230">For example, the regular expression `\b\p{Lu}\w*\b` matches all words that begin with an uppercase character, as the following table shows.</span></span>

<span data-ttu-id="9a0d3-231">模式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-231">Pattern</span></span> | <span data-ttu-id="9a0d3-232">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-232">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="9a0d3-233">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-233">Begin the match at a word boundary.</span></span>
`\p{Lu}` | <span data-ttu-id="9a0d3-234">匹配大写字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-234">Match an uppercase character.</span></span>
`\w*` | <span data-ttu-id="9a0d3-235">匹配零个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-235">Match zero or more word characters.</span></span>
`\b` | <span data-ttu-id="9a0d3-236">在单词边界处结束匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-236">End the match at a word boundary.</span></span>
 
<span data-ttu-id="9a0d3-237">由于单词边界与单词字符不同也不是其子集，因此正则表达式引擎在匹配单词字符时无法跨越单词边界。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-237">Because a word boundary is not the same as, or a subset of, a word character, there is no possibility that the regular expression engine will cross a word boundary when matching word characters.</span></span> <span data-ttu-id="9a0d3-238">这意味着，对于此正则表达式而言，回溯对任何匹配的总体成功不会有任何贡献 -- 由于正则表达式引擎被强制为单词字符的每个成功的初步匹配保存其状态，因此它只会降低性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-238">This means that for this regular expression, backtracking can never contribute to the overall success of any match -- it can only degrade performance, because the regular expression engine is forced to save its state for each successful preliminary match of a word character.</span></span>

<span data-ttu-id="9a0d3-239">如果确定不需要回溯，可以使用 **(?>**_subexpression_**)** 语言元素将其禁用。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-239">If you determine that backtracking is not necessary, you can disable it by using the **(?>**_subexpression_**)** language element.</span></span> <span data-ttu-id="9a0d3-240">下面的示例通过使用两个正则表达式来分析输入字符串。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-240">The following example parses an input string by using two regular expressions.</span></span> <span data-ttu-id="9a0d3-241">第一个正则表达式 `\b\p{Lu}\w*\b` 依赖于回溯。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-241">The first, `\b\p{Lu}\w*\b`, relies on backtracking.</span></span> <span data-ttu-id="9a0d3-242">第二个正则表达式 `\b\p{Lu}(?>\w*)\b` 禁用回溯。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-242">The second, `\b\p{Lu}(?>\w*)\b`, disables backtracking.</span></span> <span data-ttu-id="9a0d3-243">如示例输出所示，这两个正则表达式产生的结果相同。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-243">As the output from the example shows, they both produce the same result.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

<span data-ttu-id="9a0d3-244">在许多情况下，在将正则表达式模式与输入文本匹配时，回溯很重要。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-244">In many cases, backtracking is essential for matching a regular expression pattern to input text.</span></span> <span data-ttu-id="9a0d3-245">但是，过度回溯会严重降低性能，并且会产生应用程序已停止响应的感觉。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-245">However, excessive backtracking can severely degrade performance and create the impression that an application has stopped responding.</span></span> <span data-ttu-id="9a0d3-246">特别需要指出的是，当嵌套限定符并且与外部子表达式匹配的文本为与内部子表达式匹配的文本的子集时，尤其会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-246">In particular, this happens when quantifiers are nested and the text that matches the outer subexpression is a subset of the text that matches the inner subexpression.</span></span> 

> [!WARNING]
> <span data-ttu-id="9a0d3-247">除避免过度回溯之外，还应使用超时功能以确保过度回溯不会严重降低正则表达式性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-247">In addition to avoiding excessive backtracking, you should use the timeout feature to ensure that excessive backtracking does not severely degrade regular expression performance.</span></span> <span data-ttu-id="9a0d3-248">有关详细信息，请参阅[使用超时值](#use-time-out-values)部分。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-248">For more information, see the [Use time-out values](#use-time-out-values) section.</span></span>
 
<span data-ttu-id="9a0d3-249">例如，正则表达式模式 `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` 用于匹配至少包括一个字母数字字符的部件号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-249">For example, the regular expression pattern `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` is intended to match a part number that consists of at least one alphanumeric character.</span></span> <span data-ttu-id="9a0d3-250">任何附加字符可以包含字母数字字符、连字符、下划线或句号，但最后一个字符必须为字母数字。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-250">Any additional characters can consist of an alphanumeric character, a hyphen, an underscore, or a period, though the last character must be alphanumeric.</span></span> <span data-ttu-id="9a0d3-251">美元符号用于终止部件号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-251">A dollar sign terminates the part number.</span></span> <span data-ttu-id="9a0d3-252">在某些情况下，由于限定符嵌套并且子表达式 `[0-9A-Z]` 是子表达式 `[-.\w]*` 的子集，因此此正则表达式模式会表现出极差的性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-252">In some cases, this regular expression pattern can exhibit extremely poor performance because quantifiers are nested, and because the subexpression `[0-9A-Z]` is a subset of the subexpression `[-.\w]*`.</span></span>

<span data-ttu-id="9a0d3-253">在这些情况下，可通过移除嵌套限定符并将外部子表达式替换为零宽度预测先行和回顾断言来优化正则表达式性能。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-253">In these cases, you can optimize regular expression performance by removing the nested quantifiers and replacing the outer subexpression with a zero-width lookahead or lookbehind assertion.</span></span> <span data-ttu-id="9a0d3-254">预测先行和回顾断言是定位点；它们不在输入字符串中移动指针，而是通过预测先行或回顾来检查是否满足指定条件。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-254">Lookahead and lookbehind assertions are anchors; they do not move the pointer in the input string, but instead look ahead or behind to check whether a specified condition is met.</span></span> <span data-ttu-id="9a0d3-255">例如，可将部件号正则表达式重写为 `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-255">For example, the part number regular expression can be rewritten as `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span></span> <span data-ttu-id="9a0d3-256">此正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-256">This regular expression pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="9a0d3-257">模式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-257">Pattern</span></span> | <span data-ttu-id="9a0d3-258">说明</span><span class="sxs-lookup"><span data-stu-id="9a0d3-258">Description</span></span>
------- | -----------
`^` | <span data-ttu-id="9a0d3-259">从输入字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-259">Begin the match at the beginning of the input string.</span></span>
`[0-9A-Z]` | <span data-ttu-id="9a0d3-260">匹配字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-260">Match an alphanumeric character.</span></span> <span data-ttu-id="9a0d3-261">部件号至少要包含此字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-261">The part number must consist of at least this character.</span></span>
`[-.\w]*` | <span data-ttu-id="9a0d3-262">匹配零个或多个任意单词字符、连字符或句号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-262">Match zero or more occurrences of any word character, hyphen, or period.</span></span>
<span data-ttu-id="9a0d3-263">\`\$]</span><span class="sxs-lookup"><span data-stu-id="9a0d3-263">\`\$]</span></span> | <span data-ttu-id="9a0d3-264">匹配美元符号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-264">Match a dollar sign.</span></span>
`(?<=[0-9A-Z])` | <span data-ttu-id="9a0d3-265">查看作为结束的美元符号，以确保前一个字符是字母数字。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-265">Look ahead of the ending dollar sign to ensure that the previous character is alphanumeric.</span></span>
<span data-ttu-id="9a0d3-266">`$` 在输入字符串末尾结束匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-266">`$` End the match at the end of the input string.</span></span>
 
<span data-ttu-id="9a0d3-267">下面的示例演示了如何使用此正则表达式来匹配包含可能部件号的数组。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-267">The following example illustrates the use of this regular expression to match an array containing possible part numbers.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

<span data-ttu-id="9a0d3-268">.NET 中的正则表达式语言包括以下可用于消除嵌套限定符的语言元素。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-268">The regular expression language in .NET includes the following language elements that you can use to eliminate nested quantifiers.</span></span> <span data-ttu-id="9a0d3-269">有关更多信息，请参见[正则表达式中的分组构造](grouping.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-269">For more information, see [Grouping constructs in regular expressions](grouping.md).</span></span>

<span data-ttu-id="9a0d3-270">语言元素</span><span class="sxs-lookup"><span data-stu-id="9a0d3-270">Language element</span></span> | <span data-ttu-id="9a0d3-271">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-271">Description</span></span>
---------------- | ----------- 
<span data-ttu-id="9a0d3-272">**(?**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="9a0d3-272">**(?**=_subexpression_**)**</span></span> | <span data-ttu-id="9a0d3-273">零宽度正预测先行。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-273">Zero-width positive lookahead.</span></span> <span data-ttu-id="9a0d3-274">查看当前位置的前面，确定 *subexpression* 是否与输入字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-274">Look ahead of the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="9a0d3-275">**(?!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="9a0d3-275">**(?!**_subexpression_**)**</span></span> | <span data-ttu-id="9a0d3-276">零宽度负预测先行。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-276">Zero-width negative lookahead.</span></span> <span data-ttu-id="9a0d3-277">查看当前位置的前面，确定 *subexpression* 是否不与输入字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-277">Look ahead of the current position to determine whether *subexpression* does not match the input string.</span></span>
<span data-ttu-id="9a0d3-278">**(?<**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="9a0d3-278">**(?<**=_subexpression_**)**</span></span> | <span data-ttu-id="9a0d3-279">零宽度正回顾。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-279">Zero-width positive lookbehind.</span></span> <span data-ttu-id="9a0d3-280">查看当前位置的后面，确定 *subexpression* 是否与输入字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-280">Look behind the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="9a0d3-281">**(?<!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="9a0d3-281">**(?<!**_subexpression_**)**</span></span> | <span data-ttu-id="9a0d3-282">零宽度负回顾。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-282">Zero-width negative lookbehind.</span></span> <span data-ttu-id="9a0d3-283">查看当前位置的后面，确定 *subexpression* 是否不与输入字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-283">Look behind the current position to determine whether *subexpression* does not match the input string.</span></span>
 
## <a name="use-time-out-values"></a><span data-ttu-id="9a0d3-284">使用超时值</span><span class="sxs-lookup"><span data-stu-id="9a0d3-284">Use time-out values</span></span>

<span data-ttu-id="9a0d3-285">如果正则表达式处理与正则表达式模式大致匹配的输入，则通常依赖于会严重影响其性能的过度回溯。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-285">If your regular expressions processes input that nearly matches the regular expression pattern, it can often rely on excessive backtracking, which impacts its performance significantly.</span></span> <span data-ttu-id="9a0d3-286">除认真考虑对回溯的使用以及针对大致匹配输入对正则表达式进行测试之外，还应始终设置一个超时值以确保最大程度地降低过度回溯的影响（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-286">In addition to carefully considering your use of backtracking and testing the regular expression against near-matching input, you should always set a time-out value to ensure that the impact of excessive backtracking, if it occurs, is minimized.</span></span>

<span data-ttu-id="9a0d3-287">正则表达式超时间隔定义了在超时前正则表达式引擎用于查找单个匹配项的时间长度。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-287">The regular expression time-out interval defines the period of time that the regular expression engine will look for a single match before it times out.</span></span> <span data-ttu-id="9a0d3-288">默认超时间隔为 [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout)，这意味着正则表达式不会超时。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-288">The default time-out interval is [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), which means that the regular expression will not time out.</span></span> <span data-ttu-id="9a0d3-289">可以按如下所示重写此值并定义超时间隔：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-289">You can override this value and define a time-out interval as follows:</span></span> 

* <span data-ttu-id="9a0d3-290">在实例化一个 [Regex](xref:System.Text.RegularExpressions.Regex) 对象（通过调用 [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) 构造函数）时，提供一个超时值。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-290">By providing a time-out value when you instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object by calling the [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) constructor.</span></span>

* <span data-ttu-id="9a0d3-291">调用静态模式匹配方法，如 [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) 或 [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan))，其中包含 *matchTimeout* 参数。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-291">By calling a static pattern matching method, such as [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) or [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), that includes a *matchTimeout* parameter.</span></span>

<span data-ttu-id="9a0d3-292">如果定义了超时间隔并且在此间隔结束时未找到匹配项，正则表达式方法将引发 [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) 异常。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-292">If you have defined a time-out interval and a match is not found at the end of that interval, the regular expression method throws a [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) exception.</span></span> <span data-ttu-id="9a0d3-293">在异常处理程序中，可以选择使用一个更长的超时间隔来重试匹配、放弃匹配尝试并假定没有匹配项，或者放弃匹配尝试并记录异常信息以供未来分析。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-293">In your exception handler, you can choose to retry the match with a longer time-out interval, abandon the match attempt and assume that there is no match, or abandon the match attempt and log the exception information for future analysis.</span></span>

<span data-ttu-id="9a0d3-294">下面的示例定义了一种 `GetWordData` 方法，此方法实例化了一个正则表达式，使其具有 350 毫秒的超时间隔，用于计算文本文件中的词语数和一个词语中的平均字符数。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-294">The following example defines a `GetWordData` method that instantiates a regular expression with a time-out interval of 350 milliseconds to calculate the number of words and average number of characters in a word in a text document.</span></span> <span data-ttu-id="9a0d3-295">如果匹配操作超时，超时间隔将延长 350 毫秒并重新实例化 [Regex](xref:System.Text.RegularExpressions.Regex) 对象。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-295">If the matching operation times out, the time-out interval is increased by 350 milliseconds and the [Regex](xref:System.Text.RegularExpressions.Regex) object is re-instantiated.</span></span> <span data-ttu-id="9a0d3-296">如果新的超时间隔超过 1 秒，则此方法将再次向调用方引发异常。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-296">If the new time-out interval exceeds 1 second, the method re-throws the exception to the caller.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a><span data-ttu-id="9a0d3-297">只在必要时捕获</span><span class="sxs-lookup"><span data-stu-id="9a0d3-297">Capture only when necessary</span></span>

<span data-ttu-id="9a0d3-298">.NET 中的正则表达式支持许多分组构造，这样，便可以将正则表达式模式分组为一个或多个子表达式。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-298">Regular expressions in .NET support a number of grouping constructs, which let you group a regular expression pattern into one or more subexpressions.</span></span> <span data-ttu-id="9a0d3-299">.NET 正则表达式语言中最常用的分组构造为 **(**_subexpression_**)**（用于定义编号的捕获组）和 **(?<*_name_**>**_subexpression_**)**（用于定义命名的捕获组）。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-299">The most commonly used grouping constructs in .NET regular expression language are **(**_subexpression_**)**, which defines a numbered capturing group, and **(?<*_name_**>**_subexpression_**)**, which defines a named capturing group.</span></span> <span data-ttu-id="9a0d3-300">分组构造是创建反向引用和定义要应用限定符的子表达式时所必需的。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-300">Grouping constructs are essential for creating backreferences and for defining a subexpression to which a quantifier is applied.</span></span> 

<span data-ttu-id="9a0d3-301">但是，使用这些语言元素会产生一定的开销。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-301">However, the use of these language elements has a cost.</span></span> <span data-ttu-id="9a0d3-302">它们会导致用最近的未命名或已命名捕获来填充 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 属性返回的 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 对象，如果单个分组构造已捕获输入字符串中的多个子字符串，则还会填充包含多个 [Capture](xref:System.Text.RegularExpressions.Capture) 对象的特定捕获组的 [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) 属性返回的 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 对象。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-302">They cause the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property to be populated with the most recent unnamed or named captures, and if a single grouping construct has captured multiple substrings in the input string, they also populate the [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) object returned by the [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) property of a particular capturing group with multiple [Capture](xref:System.Text.RegularExpressions.Capture) objects.</span></span>

<span data-ttu-id="9a0d3-303">通常，只在正则表达式中使用分组构造，这样可对其应用限定符，而且以后不会使用这些子表达式捕获的组。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-303">Often, grouping constructs are used in a regular expression only so that quantifiers can be applied to them, and the groups captured by these subexpressions are not subsequently used.</span></span> <span data-ttu-id="9a0d3-304">例如，正则表达式 `\b(\w+[;,]?\s?)+[.?!]` 用于捕获整个句子。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-304">For example, the regular expression `\b(\w+[;,]?\s?)+[.?!]` is designed to capture an entire sentence.</span></span> <span data-ttu-id="9a0d3-305">下表描述了此正则表达式模式中的语言元素及其对 [Match](xref:System.Text.RegularExpressions.Match) 对象的 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 和 [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) 集合的影响。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-305">The following table describes the language elements in this regular expression pattern and their effect on the [Match](xref:System.Text.RegularExpressions.Match) object's [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) and [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) collections.</span></span>

<span data-ttu-id="9a0d3-306">模式</span><span class="sxs-lookup"><span data-stu-id="9a0d3-306">Pattern</span></span> | <span data-ttu-id="9a0d3-307">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-307">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="9a0d3-308">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-308">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="9a0d3-309">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-309">Match one or more word characters.</span></span>
`[;,]?` | <span data-ttu-id="9a0d3-310">匹配零个或一个逗号或分号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-310">Match zero or one comma or semicolon.</span></span>
`\s?` | <span data-ttu-id="9a0d3-311">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-311">Match zero or one white-space character.</span></span>
`(\w+[;,]?\s?)+` | <span data-ttu-id="9a0d3-312">匹配以下一个或多个事例：一个或多个单词字符，后跟一个可选逗号或分号，一个可选的空白字符。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-312">Match one or more occurrences of one or more word characters followed by an optional comma or semicolon followed by an optional white-space character.</span></span> <span data-ttu-id="9a0d3-313">用于定义第一个捕获组，它是必需的，以便将重复多个单词字符的组合（即单词）后跟可选标点符号，直至正则表达式引擎到达句子末尾。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-313">This defines the first capturing group, which is necessary so that the combination of multiple word characters (that is, a word) followed by an optional punctuation symbol will be repeated until the regular expression engine reaches the end of a sentence.</span></span>
`[.?!]` | <span data-ttu-id="9a0d3-314">匹配句号、问号或感叹号。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-314">Match a period, question mark, or exclamation point.</span></span>
 
<span data-ttu-id="9a0d3-315">如下面的示例所示，当找到匹配时，[GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 和 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 对象都将用匹配中的捕获内容来填充。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-315">As the following example shows, when a match is found, both the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) objects are populated with captures from the match.</span></span> <span data-ttu-id="9a0d3-316">在此情况下，存在捕获组 `(\w+[;,]?\s?)`，因此可对其应用 **+** 限定符，从而使得正则表达式模式可与句子中的每个单词匹配。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-316">In this case, the capturing group `(\w+[;,]?\s?)` exists so that the **+** quantifier can be applied to it, which enables the regular expression pattern to match each word in a sentence.</span></span> <span data-ttu-id="9a0d3-317">否则，它将匹配句子中的最后一个单词。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-317">Otherwise, it would match the last word in a sentence.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

<span data-ttu-id="9a0d3-318">当你只使用子表达式来对其应用限定符并且你对捕获的文本不感兴趣时，应禁用组捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-318">When you use subexpressions only to apply quantifiers to them, and you are not interested in the captured text, you should disable group captures.</span></span> <span data-ttu-id="9a0d3-319">例如，**(?:**_subexpression_**)** 语言元素可防止应用该元素的组捕获匹配的子字符串。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-319">For example, the **(?:**_subexpression_**)** language element prevents the group to which it applies from capturing matched substrings.</span></span> <span data-ttu-id="9a0d3-320">在下面的示例中，上一示例中的正则表达式模式更改为 `\b(?:\w+[;,]?\s?)+[.?!]`。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-320">In the following example, the regular expression pattern from the previous example is changed to `\b(?:\w+[;,]?\s?)+[.?!]`.</span></span> <span data-ttu-id="9a0d3-321">正如输出所示，它禁止正则表达式引擎填充 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 和 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 集合。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-321">As the output shows, it prevents the regular expression engine from populating the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) collections.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

<span data-ttu-id="9a0d3-322">可以通过以下方式之一来禁用捕获：</span><span class="sxs-lookup"><span data-stu-id="9a0d3-322">You can disable captures in one of the following ways:</span></span>

* <span data-ttu-id="9a0d3-323">使用 **(?:**_subexpression_**)** 语言元素。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-323">Use the **(?:**_subexpression_**)** language element.</span></span> <span data-ttu-id="9a0d3-324">此元素可防止在它应用的组中捕获匹配的子字符串。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-324">This element prevents the capture of matched substrings in the group to which it applies.</span></span> <span data-ttu-id="9a0d3-325">它不在任何嵌套的组中禁用子字符串捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-325">It does not disable substring captures in any nested groups.</span></span>

* <span data-ttu-id="9a0d3-326">使用 [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) 选项。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-326">Use the [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) option.</span></span> <span data-ttu-id="9a0d3-327">在正则表达式模式中禁用所有未命名或隐式捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-327">It disables all unnamed or implicit captures in the regular expression pattern.</span></span> <span data-ttu-id="9a0d3-328">使用此选项时，只能捕获与使用 **(?<**_name_**>**_subexpression_**)** 语言元素定义的命名组匹配的子字符串。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-328">When you use this option, only substrings that match named groups defined with the **(?<**_name_**>**_subexpression_**)** language element can be captured.</span></span> <span data-ttu-id="9a0d3-329">可将 [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) 标志传递给 [Regex](xref:System.Text.RegularExpressions.Regex) 类构造函数的 options 参数或 [Regex](xref:System.Text.RegularExpressions.Regex) 静态匹配方法的 options 参数。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-329">The [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) flag can be passed to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) class constructor or to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) static matching method.</span></span>

* <span data-ttu-id="9a0d3-330">在 **(?imnsx)** 语言元素中使用 **n** 选项。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-330">Use the **n** option in the **(?imnsx)** language element.</span></span> <span data-ttu-id="9a0d3-331">此选项将在元素出现的正则表达式模式中的点处禁用所有未命名或隐式捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-331">This option disables all unnamed or implicit captures from the point in the regular expression pattern at which the element appears.</span></span> <span data-ttu-id="9a0d3-332">捕获将一直禁用到模式结束或 **(-n)** 选项启用未命名或隐式捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-332">Captures are disabled either until the end of the pattern or until the **(-n)** option enables unnamed or implicit captures.</span></span> <span data-ttu-id="9a0d3-333">有关更多信息，请参见[正则表达式中的其他构造](miscellaneous.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-333">For more information, see [Miscellaneous constructs in regular expressions](miscellaneous.md).</span></span>

* <span data-ttu-id="9a0d3-334">在 **(?imnsx:**_subexpression_**)** 语言元素中使用 **n** 选项。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-334">Use the **n** option in the **(?imnsx:**_subexpression_**)** language element.</span></span> <span data-ttu-id="9a0d3-335">此选项可在 *subexpression* 中禁用所有未命名或隐式捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-335">This option disables all unnamed or implicit captures in *subexpression*.</span></span> <span data-ttu-id="9a0d3-336">同时禁用任何未命名或隐式的嵌套捕获组进行的任何捕获。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-336">Captures by any unnamed or implicit nested capturing groups are disabled as well.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a0d3-337">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a0d3-337">Related topics</span></span>

<span data-ttu-id="9a0d3-338">标题</span><span class="sxs-lookup"><span data-stu-id="9a0d3-338">Title</span></span> | <span data-ttu-id="9a0d3-339">描述</span><span class="sxs-lookup"><span data-stu-id="9a0d3-339">Description</span></span>
----- | ----------- 
[<span data-ttu-id="9a0d3-340">正则表达式行为的详细信息</span><span class="sxs-lookup"><span data-stu-id="9a0d3-340">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="9a0d3-341">在 .NET 中检查正则表达式引擎的实现。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-341">Examines the implementation of the regular expression engine in .NET.</span></span> <span data-ttu-id="9a0d3-342">该主题重点介绍正则表达式的灵活性，并说明开发人员确保正则表达式引擎高效、强健运行的职责。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-342">The topic focuses on the flexibility of regular expressions and explains the developer's responsibility for ensuring the efficient and robust operation of the regular expression engine.</span></span>
[<span data-ttu-id="9a0d3-343">正则表达式中的回溯</span><span class="sxs-lookup"><span data-stu-id="9a0d3-343">Backtracking in regular expressions</span></span>](backtracking.md) | <span data-ttu-id="9a0d3-344">说明何为回溯及其对正则表达式性能有何影响，并检查为回溯提供替代项的语言元素。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-344">Explains what backtracking is and how it affects regular expression performance, and examines language elements that provide alternatives to backtracking.</span></span>
[<span data-ttu-id="9a0d3-345">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="9a0d3-345">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="9a0d3-346">介绍 .NET 中的正则表达式语言的元素，并提供每个语言元素的详细文档链接。</span><span class="sxs-lookup"><span data-stu-id="9a0d3-346">Describes the elements of the regular expression language in .NET and provides links to detailed documentation for each language element.</span></span>
 


