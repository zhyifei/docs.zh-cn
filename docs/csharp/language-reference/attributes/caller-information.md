---
title: C# 保留的特性：跟踪调用方信息
ms.date: 04/09/2020
description: 这些特性指示编译器生成有关调用成员的代码的信息。 可使用 CallerFilePath、CallerLineNumber 和 CallerMemberName 提供详细的跟踪信息
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389822"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="24249-104">保留的特性：确定调用方信息</span><span class="sxs-lookup"><span data-stu-id="24249-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="24249-105">使用信息属性，可以获取有关方法调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="24249-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="24249-106">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="24249-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="24249-107">若要获取成员调用方信息，可以使用应用于可选参数的特性。</span><span class="sxs-lookup"><span data-stu-id="24249-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="24249-108">每个可选参数指定一个默认值。</span><span class="sxs-lookup"><span data-stu-id="24249-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="24249-109">下表列出在 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 命名空间中定义的调用方信息特性：</span><span class="sxs-lookup"><span data-stu-id="24249-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="24249-110">特性</span><span class="sxs-lookup"><span data-stu-id="24249-110">Attribute</span></span>|<span data-ttu-id="24249-111">描述</span><span class="sxs-lookup"><span data-stu-id="24249-111">Description</span></span>|<span data-ttu-id="24249-112">类型</span><span class="sxs-lookup"><span data-stu-id="24249-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="24249-113">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="24249-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="24249-114">完整路径是编译时的路径。</span><span class="sxs-lookup"><span data-stu-id="24249-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="24249-115">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="24249-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="24249-116">调用方的方法名称或属性名称。</span><span class="sxs-lookup"><span data-stu-id="24249-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="24249-117">此信息有助于你编写跟踪、调试和创建诊断工具。</span><span class="sxs-lookup"><span data-stu-id="24249-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="24249-118">下面的示例演示如何使用调用方信息特性。</span><span class="sxs-lookup"><span data-stu-id="24249-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="24249-119">每次调用 `TraceMessage` 方法时，调用方信息将替换为可选参数的变量。</span><span class="sxs-lookup"><span data-stu-id="24249-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="24249-120">为每个可选参数指定显式默认值。</span><span class="sxs-lookup"><span data-stu-id="24249-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="24249-121">不能将调用方信息特性应用于未指定为可选的参数。</span><span class="sxs-lookup"><span data-stu-id="24249-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="24249-122">调用方信息特性不会使参数成为可选参数。</span><span class="sxs-lookup"><span data-stu-id="24249-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="24249-123">相反，它们会在忽略此参数时影响传入的默认值。</span><span class="sxs-lookup"><span data-stu-id="24249-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="24249-124">在编译时，调用方信息值将作为文本传入中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="24249-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="24249-125">与异常的 <xref:System.Exception.StackTrace%2A> 属性的结果不同，这些结果不受模糊处理的影响。</span><span class="sxs-lookup"><span data-stu-id="24249-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="24249-126">你可显式提供可选参数来控制调用方信息或隐藏调用方信息。</span><span class="sxs-lookup"><span data-stu-id="24249-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="24249-127">成员名称</span><span class="sxs-lookup"><span data-stu-id="24249-127">Member names</span></span>

<span data-ttu-id="24249-128">可以使用 `CallerMemberName` 特性来避免将成员名称指定为所调用的方法的 `String` 参数。</span><span class="sxs-lookup"><span data-stu-id="24249-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="24249-129">通过使用这种技术，可以避免“重命名重构”  不更改 `String` 值的问题。</span><span class="sxs-lookup"><span data-stu-id="24249-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="24249-130">此好处对于以下任务特别有用：</span><span class="sxs-lookup"><span data-stu-id="24249-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="24249-131">使用跟踪和诊断例程。</span><span class="sxs-lookup"><span data-stu-id="24249-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="24249-132">在绑定数据时实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口。</span><span class="sxs-lookup"><span data-stu-id="24249-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="24249-133">此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="24249-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="24249-134">如果没有 `CallerMemberName` 特性，则必须将属性名称指定为文本。</span><span class="sxs-lookup"><span data-stu-id="24249-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="24249-135">以下图表显示在使用 `CallerMemberName` 特性时返回的成员名称。</span><span class="sxs-lookup"><span data-stu-id="24249-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="24249-136">调用发生中</span><span class="sxs-lookup"><span data-stu-id="24249-136">Calls occur within</span></span>|<span data-ttu-id="24249-137">成员名称结果</span><span class="sxs-lookup"><span data-stu-id="24249-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="24249-138">方法、属性或事件</span><span class="sxs-lookup"><span data-stu-id="24249-138">Method, property, or event</span></span>|<span data-ttu-id="24249-139">从中发起调用的方法、属性或事件的名称。</span><span class="sxs-lookup"><span data-stu-id="24249-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="24249-140">构造函数</span><span class="sxs-lookup"><span data-stu-id="24249-140">Constructor</span></span>|<span data-ttu-id="24249-141">字符串“.ctor”</span><span class="sxs-lookup"><span data-stu-id="24249-141">The string ".ctor"</span></span>|
|<span data-ttu-id="24249-142">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="24249-142">Static constructor</span></span>|<span data-ttu-id="24249-143">字符串“.cctor”</span><span class="sxs-lookup"><span data-stu-id="24249-143">The string ".cctor"</span></span>|
|<span data-ttu-id="24249-144">析构函数</span><span class="sxs-lookup"><span data-stu-id="24249-144">Destructor</span></span>|<span data-ttu-id="24249-145">字符串“Finalize”</span><span class="sxs-lookup"><span data-stu-id="24249-145">The string "Finalize"</span></span>|
|<span data-ttu-id="24249-146">用户定义的运算符或转换</span><span class="sxs-lookup"><span data-stu-id="24249-146">User-defined operators or conversions</span></span>|<span data-ttu-id="24249-147">为成员生成的名称，例如，“op_Addition”。</span><span class="sxs-lookup"><span data-stu-id="24249-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="24249-148">特性构造函数</span><span class="sxs-lookup"><span data-stu-id="24249-148">Attribute constructor</span></span>|<span data-ttu-id="24249-149">要应用特性的方法或属性的名称。</span><span class="sxs-lookup"><span data-stu-id="24249-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="24249-150">如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="24249-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="24249-151">无包含的成员（例如，程序集级别或应用于类型的特性）</span><span class="sxs-lookup"><span data-stu-id="24249-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="24249-152">可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="24249-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="24249-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="24249-153">See also</span></span>

- [<span data-ttu-id="24249-154">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="24249-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="24249-155">特性</span><span class="sxs-lookup"><span data-stu-id="24249-155">Attributes</span></span>](../../../standard/attributes/index.md)
