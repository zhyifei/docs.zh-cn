---
title: '调用方信息 （F #）'
description: 介绍如何使用调用方信息参数特性从一种方法获取调用方信息。
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537275"
---
# <a name="caller-information"></a><span data-ttu-id="20138-103">调用方信息</span><span class="sxs-lookup"><span data-stu-id="20138-103">Caller information</span></span>

<span data-ttu-id="20138-104">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="20138-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="20138-105">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="20138-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="20138-106">此信息有助于跟踪、调试和创建诊断工具。</span><span class="sxs-lookup"><span data-stu-id="20138-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="20138-107">若要获取此信息，可以使用应用于可选参数的特性，每个特性都具有默认值。</span><span class="sxs-lookup"><span data-stu-id="20138-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="20138-108">下表列出了在中定义的调用方信息特性[System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices)命名空间：</span><span class="sxs-lookup"><span data-stu-id="20138-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="20138-109">特性</span><span class="sxs-lookup"><span data-stu-id="20138-109">Attribute</span></span>|<span data-ttu-id="20138-110">描述</span><span class="sxs-lookup"><span data-stu-id="20138-110">Description</span></span>|<span data-ttu-id="20138-111">类型</span><span class="sxs-lookup"><span data-stu-id="20138-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="20138-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="20138-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="20138-113">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="20138-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="20138-114">这是编译时的文件路径。</span><span class="sxs-lookup"><span data-stu-id="20138-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="20138-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="20138-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="20138-116">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="20138-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="20138-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="20138-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="20138-118">调用方的方法或属性名称。</span><span class="sxs-lookup"><span data-stu-id="20138-118">Method or property name of the caller.</span></span> <span data-ttu-id="20138-119">请参阅本主题后面的成员名称部分。</span><span class="sxs-lookup"><span data-stu-id="20138-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="20138-120">示例</span><span class="sxs-lookup"><span data-stu-id="20138-120">Example</span></span>

<span data-ttu-id="20138-121">下面的示例演示如何使用这些属性来跟踪调用方。</span><span class="sxs-lookup"><span data-stu-id="20138-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="20138-122">备注</span><span class="sxs-lookup"><span data-stu-id="20138-122">Remarks</span></span>

<span data-ttu-id="20138-123">调用方信息特性只能应用于可选参数。</span><span class="sxs-lookup"><span data-stu-id="20138-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="20138-124">必须提供每个可选参数的显式值。</span><span class="sxs-lookup"><span data-stu-id="20138-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="20138-125">调用方信息特性会导致编译器编写使用调用方信息特性修饰每个可选参数的正确值。</span><span class="sxs-lookup"><span data-stu-id="20138-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="20138-126">在编译时，调用方信息值将作为文本传入中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="20138-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="20138-127">与不同的结果[StackTrace](/dotnet/api/system.diagnostics.stacktrace)模糊处理，不会影响有关例外情况，结果的属性。</span><span class="sxs-lookup"><span data-stu-id="20138-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="20138-128">你可显式提供可选参数来控制调用方信息或隐藏调用方信息。</span><span class="sxs-lookup"><span data-stu-id="20138-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="20138-129">成员名称</span><span class="sxs-lookup"><span data-stu-id="20138-129">Member names</span></span>

<span data-ttu-id="20138-130">可以使用[ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)属性，若要避免指定将成员名称`String`到被调用方法的参数。</span><span class="sxs-lookup"><span data-stu-id="20138-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="20138-131">通过使用此方法，避免重命名重构不会更改的问题`String`值。</span><span class="sxs-lookup"><span data-stu-id="20138-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="20138-132">此好处对于以下任务特别有用：</span><span class="sxs-lookup"><span data-stu-id="20138-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="20138-133">使用跟踪和诊断例程。</span><span class="sxs-lookup"><span data-stu-id="20138-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="20138-134">实现[INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged)接口时将数据绑定。</span><span class="sxs-lookup"><span data-stu-id="20138-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="20138-135">此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="20138-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="20138-136">无需[ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)属性，您必须指定属性名称的文本。</span><span class="sxs-lookup"><span data-stu-id="20138-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="20138-137">下图显示了成员时使用 CallerMemberName 属性返回的名称。</span><span class="sxs-lookup"><span data-stu-id="20138-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="20138-138">调用发生中</span><span class="sxs-lookup"><span data-stu-id="20138-138">Calls occurs within</span></span>|<span data-ttu-id="20138-139">成员名称结果</span><span class="sxs-lookup"><span data-stu-id="20138-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="20138-140">方法、属性或事件</span><span class="sxs-lookup"><span data-stu-id="20138-140">Method, property, or event</span></span>|<span data-ttu-id="20138-141">从中发起调用的方法、属性或事件的名称。</span><span class="sxs-lookup"><span data-stu-id="20138-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="20138-142">构造函数</span><span class="sxs-lookup"><span data-stu-id="20138-142">Constructor</span></span>|<span data-ttu-id="20138-143">字符串“.ctor”</span><span class="sxs-lookup"><span data-stu-id="20138-143">The string ".ctor"</span></span>|
|<span data-ttu-id="20138-144">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="20138-144">Static constructor</span></span>|<span data-ttu-id="20138-145">字符串“.cctor”</span><span class="sxs-lookup"><span data-stu-id="20138-145">The string ".cctor"</span></span>|
|<span data-ttu-id="20138-146">析构函数</span><span class="sxs-lookup"><span data-stu-id="20138-146">Destructor</span></span>|<span data-ttu-id="20138-147">字符串“Finalize”</span><span class="sxs-lookup"><span data-stu-id="20138-147">The string "Finalize"</span></span>|
|<span data-ttu-id="20138-148">用户定义的运算符或转换</span><span class="sxs-lookup"><span data-stu-id="20138-148">User-defined operators or conversions</span></span>|<span data-ttu-id="20138-149">为成员生成的名称，例如，“op_Addition”。</span><span class="sxs-lookup"><span data-stu-id="20138-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="20138-150">特性构造函数</span><span class="sxs-lookup"><span data-stu-id="20138-150">Attribute constructor</span></span>|<span data-ttu-id="20138-151">要应用特性的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="20138-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="20138-152">如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="20138-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="20138-153">无包含的成员（例如，程序集级别或应用于类型的特性）</span><span class="sxs-lookup"><span data-stu-id="20138-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="20138-154">可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="20138-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="20138-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="20138-155">See also</span></span>

- [<span data-ttu-id="20138-156">特性</span><span class="sxs-lookup"><span data-stu-id="20138-156">Attributes</span></span>](attributes.md)  
- [<span data-ttu-id="20138-157">命名的参数</span><span class="sxs-lookup"><span data-stu-id="20138-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
- [<span data-ttu-id="20138-158">可选参数</span><span class="sxs-lookup"><span data-stu-id="20138-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
