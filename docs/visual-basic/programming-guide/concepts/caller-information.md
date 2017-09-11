---
title: "调用方信息 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d9a028474a3bb7ae020f466d4dfe51608c43ab07
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="ebac6-102">调用方信息 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebac6-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="ebac6-103">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="ebac6-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="ebac6-104">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="ebac6-105">此信息有助于跟踪、调试和创建诊断工具。</span><span class="sxs-lookup"><span data-stu-id="ebac6-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="ebac6-106">若要获取此信息，可以使用应用于可选参数的特性，每个特性都具有默认值。</span><span class="sxs-lookup"><span data-stu-id="ebac6-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="ebac6-107">下表列出了在中定义的调用方信息特性<xref:System.Runtime.CompilerServices?displayProperty=fullName>命名空间︰</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ebac6-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="ebac6-108">特性</span><span class="sxs-lookup"><span data-stu-id="ebac6-108">Attribute</span></span>|<span data-ttu-id="ebac6-109">描述</span><span class="sxs-lookup"><span data-stu-id="ebac6-109">Description</span></span>|<span data-ttu-id="ebac6-110">类型</span><span class="sxs-lookup"><span data-stu-id="ebac6-110">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="ebac6-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="ebac6-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="ebac6-112">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="ebac6-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="ebac6-113">这是编译时的文件路径。</span><span class="sxs-lookup"><span data-stu-id="ebac6-113">This is the file path at compile time.</span></span>|`String`|  
|<span data-ttu-id="ebac6-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="ebac6-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="ebac6-115">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="ebac6-115">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="ebac6-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="ebac6-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="ebac6-117">调用方的方法或属性名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-117">Method or property name of the caller.</span></span> <span data-ttu-id="ebac6-118">请参阅[成员名称](#MEMBERNAMES)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="ebac6-118">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="ebac6-119">示例</span><span class="sxs-lookup"><span data-stu-id="ebac6-119">Example</span></span>  
 <span data-ttu-id="ebac6-120">下面的示例演示如何使用调用方信息特性。</span><span class="sxs-lookup"><span data-stu-id="ebac6-120">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="ebac6-121">每次调用 `TraceMessage` 方法时，调用方信息将替换为可选参数的变量。</span><span class="sxs-lookup"><span data-stu-id="ebac6-121">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="ebac6-122">备注</span><span class="sxs-lookup"><span data-stu-id="ebac6-122">Remarks</span></span>  
 <span data-ttu-id="ebac6-123">你必须为每个可选参数指定显式默认值。</span><span class="sxs-lookup"><span data-stu-id="ebac6-123">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="ebac6-124">不能将调用方信息特性应用于未指定为可选的参数。</span><span class="sxs-lookup"><span data-stu-id="ebac6-124">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="ebac6-125">调用方信息特性不会使参数成为可选参数。</span><span class="sxs-lookup"><span data-stu-id="ebac6-125">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="ebac6-126">相反，它们会在忽略此参数时影响传入的默认值。</span><span class="sxs-lookup"><span data-stu-id="ebac6-126">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="ebac6-127">在编译时，调用方信息值将作为文本传入中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="ebac6-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="ebac6-128">与不同的结果<xref:System.Exception.StackTrace%2A>例外情况之外，结果的属性不受模糊处理。</xref:System.Exception.StackTrace%2A></span><span class="sxs-lookup"><span data-stu-id="ebac6-128">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="ebac6-129">你可显式提供可选参数来控制调用方信息或隐藏调用方信息。</span><span class="sxs-lookup"><span data-stu-id="ebac6-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="ebac6-130"><a name="MEMBERNAMES"></a>成员名称</span><span class="sxs-lookup"><span data-stu-id="ebac6-130"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="ebac6-131">可以使用 `CallerMemberName` 特性来避免将成员名称指定为所调用的方法的 `String` 参数。</span><span class="sxs-lookup"><span data-stu-id="ebac6-131">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="ebac6-132">通过使用此方法，可以避免此问题，**重命名重构**不会更改`String`值。</span><span class="sxs-lookup"><span data-stu-id="ebac6-132">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="ebac6-133">此好处对于以下任务特别有用：</span><span class="sxs-lookup"><span data-stu-id="ebac6-133">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="ebac6-134">使用跟踪和诊断例程。</span><span class="sxs-lookup"><span data-stu-id="ebac6-134">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="ebac6-135">实现<xref:System.ComponentModel.INotifyPropertyChanged>接口绑定数据时。</xref:System.ComponentModel.INotifyPropertyChanged></span><span class="sxs-lookup"><span data-stu-id="ebac6-135">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="ebac6-136">此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="ebac6-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="ebac6-137">如果没有 `CallerMemberName` 特性，则必须将属性名称指定为文本。</span><span class="sxs-lookup"><span data-stu-id="ebac6-137">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="ebac6-138">以下图表显示在使用 `CallerMemberName` 特性时返回的成员名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-138">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="ebac6-139">调用发生中</span><span class="sxs-lookup"><span data-stu-id="ebac6-139">Calls occurs within</span></span>|<span data-ttu-id="ebac6-140">成员名称结果</span><span class="sxs-lookup"><span data-stu-id="ebac6-140">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="ebac6-141">方法、属性或事件</span><span class="sxs-lookup"><span data-stu-id="ebac6-141">Method, property, or event</span></span>|<span data-ttu-id="ebac6-142">从中发起调用的方法、属性或事件的名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-142">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="ebac6-143">构造函数</span><span class="sxs-lookup"><span data-stu-id="ebac6-143">Constructor</span></span>|<span data-ttu-id="ebac6-144">字符串“.ctor”</span><span class="sxs-lookup"><span data-stu-id="ebac6-144">The string ".ctor"</span></span>|  
|<span data-ttu-id="ebac6-145">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="ebac6-145">Static constructor</span></span>|<span data-ttu-id="ebac6-146">字符串“.cctor”</span><span class="sxs-lookup"><span data-stu-id="ebac6-146">The string ".cctor"</span></span>|  
|<span data-ttu-id="ebac6-147">析构函数</span><span class="sxs-lookup"><span data-stu-id="ebac6-147">Destructor</span></span>|<span data-ttu-id="ebac6-148">字符串“Finalize”</span><span class="sxs-lookup"><span data-stu-id="ebac6-148">The string "Finalize"</span></span>|  
|<span data-ttu-id="ebac6-149">用户定义的运算符或转换</span><span class="sxs-lookup"><span data-stu-id="ebac6-149">User-defined operators or conversions</span></span>|<span data-ttu-id="ebac6-150">为成员生成的名称，例如，“op_Addition”。</span><span class="sxs-lookup"><span data-stu-id="ebac6-150">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="ebac6-151">特性构造函数</span><span class="sxs-lookup"><span data-stu-id="ebac6-151">Attribute constructor</span></span>|<span data-ttu-id="ebac6-152">要应用特性的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="ebac6-153">如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="ebac6-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="ebac6-154">无包含的成员（例如，程序集级别或应用于类型的特性）</span><span class="sxs-lookup"><span data-stu-id="ebac6-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="ebac6-155">可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="ebac6-155">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebac6-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebac6-156">See Also</span></span>  
 <span data-ttu-id="ebac6-157">[特性 (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ebac6-157">[Attributes (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="ebac6-158"> [公共特性 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ebac6-158"> [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span></span>  
<span data-ttu-id="ebac6-159"> [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="ebac6-159"> [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span></span>  
<span data-ttu-id="ebac6-160"> [编程概念 (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="ebac6-160"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
