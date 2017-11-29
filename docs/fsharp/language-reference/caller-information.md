---
title: "调用方信息 （F #）"
description: "描述如何使用调用方信息自变量特性来从方法获取调用方信息。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="f6840-104">调用方信息</span><span class="sxs-lookup"><span data-stu-id="f6840-104">Caller information</span></span>

<span data-ttu-id="f6840-105">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="f6840-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="f6840-106">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="f6840-107">此信息有助于跟踪、调试和创建诊断工具。</span><span class="sxs-lookup"><span data-stu-id="f6840-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="f6840-108">若要获取此信息，可以使用应用于可选参数的特性，每个特性都具有默认值。</span><span class="sxs-lookup"><span data-stu-id="f6840-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="f6840-109">下表列出了在中定义的调用方信息特性[System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices)命名空间：</span><span class="sxs-lookup"><span data-stu-id="f6840-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="f6840-110">特性</span><span class="sxs-lookup"><span data-stu-id="f6840-110">Attribute</span></span>|<span data-ttu-id="f6840-111">描述</span><span class="sxs-lookup"><span data-stu-id="f6840-111">Description</span></span>|<span data-ttu-id="f6840-112">类型</span><span class="sxs-lookup"><span data-stu-id="f6840-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="f6840-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="f6840-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="f6840-114">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f6840-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="f6840-115">这是编译时的文件路径。</span><span class="sxs-lookup"><span data-stu-id="f6840-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="f6840-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="f6840-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="f6840-117">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="f6840-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="f6840-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="f6840-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="f6840-119">调用方的方法或属性名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-119">Method or property name of the caller.</span></span> <span data-ttu-id="f6840-120">请参阅本主题后面的成员名称部分。</span><span class="sxs-lookup"><span data-stu-id="f6840-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="f6840-121">示例</span><span class="sxs-lookup"><span data-stu-id="f6840-121">Example</span></span>

<span data-ttu-id="f6840-122">下面的示例演示如何使用这些特性来跟踪调用方。</span><span class="sxs-lookup"><span data-stu-id="f6840-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="f6840-123">备注</span><span class="sxs-lookup"><span data-stu-id="f6840-123">Remarks</span></span>

<span data-ttu-id="f6840-124">调用方信息特性只能应用于可选参数。</span><span class="sxs-lookup"><span data-stu-id="f6840-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="f6840-125">必须提供每个可选参数的显式值。</span><span class="sxs-lookup"><span data-stu-id="f6840-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="f6840-126">调用方信息特性会导致编译器编写使用调用方信息特性修饰每个可选参数的正确值。</span><span class="sxs-lookup"><span data-stu-id="f6840-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="f6840-127">在编译时，调用方信息值将作为文本传入中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="f6840-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="f6840-128">与不同的结果[StackTrace](/dotnet/api/system.diagnostics.stacktrace)的异常，结果的属性不受模糊处理。</span><span class="sxs-lookup"><span data-stu-id="f6840-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="f6840-129">你可显式提供可选参数来控制调用方信息或隐藏调用方信息。</span><span class="sxs-lookup"><span data-stu-id="f6840-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="f6840-130">成员名称</span><span class="sxs-lookup"><span data-stu-id="f6840-130">Member names</span></span>

<span data-ttu-id="f6840-131">你可以使用[ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)特性来避免将成员名称指定`String`为调用的方法的自变量。</span><span class="sxs-lookup"><span data-stu-id="f6840-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="f6840-132">通过使用这种方法，你可以避免重命名重构不会更改的问题`String`值。</span><span class="sxs-lookup"><span data-stu-id="f6840-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="f6840-133">此好处对于以下任务特别有用：</span><span class="sxs-lookup"><span data-stu-id="f6840-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="f6840-134">使用跟踪和诊断例程。</span><span class="sxs-lookup"><span data-stu-id="f6840-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="f6840-135">实现[INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged)接口绑定数据时。</span><span class="sxs-lookup"><span data-stu-id="f6840-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="f6840-136">此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="f6840-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="f6840-137">而无需[ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)属性，则必须将属性名称指定为文本。</span><span class="sxs-lookup"><span data-stu-id="f6840-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="f6840-138">下图显示该成员时使用 CallerMemberName 属性返回的名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="f6840-139">调用发生中</span><span class="sxs-lookup"><span data-stu-id="f6840-139">Calls occurs within</span></span>|<span data-ttu-id="f6840-140">成员名称结果</span><span class="sxs-lookup"><span data-stu-id="f6840-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="f6840-141">方法、属性或事件</span><span class="sxs-lookup"><span data-stu-id="f6840-141">Method, property, or event</span></span>|<span data-ttu-id="f6840-142">从中发起调用的方法、属性或事件的名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="f6840-143">构造函数</span><span class="sxs-lookup"><span data-stu-id="f6840-143">Constructor</span></span>|<span data-ttu-id="f6840-144">字符串“.ctor”</span><span class="sxs-lookup"><span data-stu-id="f6840-144">The string ".ctor"</span></span>|
|<span data-ttu-id="f6840-145">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="f6840-145">Static constructor</span></span>|<span data-ttu-id="f6840-146">字符串“.cctor”</span><span class="sxs-lookup"><span data-stu-id="f6840-146">The string ".cctor"</span></span>|
|<span data-ttu-id="f6840-147">析构函数</span><span class="sxs-lookup"><span data-stu-id="f6840-147">Destructor</span></span>|<span data-ttu-id="f6840-148">字符串“Finalize”</span><span class="sxs-lookup"><span data-stu-id="f6840-148">The string "Finalize"</span></span>|
|<span data-ttu-id="f6840-149">用户定义的运算符或转换</span><span class="sxs-lookup"><span data-stu-id="f6840-149">User-defined operators or conversions</span></span>|<span data-ttu-id="f6840-150">为成员生成的名称，例如，“op_Addition”。</span><span class="sxs-lookup"><span data-stu-id="f6840-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="f6840-151">特性构造函数</span><span class="sxs-lookup"><span data-stu-id="f6840-151">Attribute constructor</span></span>|<span data-ttu-id="f6840-152">要应用特性的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="f6840-153">如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="f6840-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="f6840-154">无包含的成员（例如，程序集级别或应用于类型的特性）</span><span class="sxs-lookup"><span data-stu-id="f6840-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="f6840-155">可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="f6840-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f6840-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6840-156">See also</span></span>
 [<span data-ttu-id="f6840-157">特性</span><span class="sxs-lookup"><span data-stu-id="f6840-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="f6840-158">命名自变量</span><span class="sxs-lookup"><span data-stu-id="f6840-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="f6840-159">可选参数</span><span class="sxs-lookup"><span data-stu-id="f6840-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
