---
title: 使用 Blazor 构建可重用的 UI 组件
description: 了解如何使用 Blazor 构建可重用的 UI 组件，以及它们与 ASP.NET Web 窗体控件的比较方式。
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228624"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="43568-103">使用 Blazor 构建可重用的 UI 组件</span><span class="sxs-lookup"><span data-stu-id="43568-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="43568-104">ASP.NET Web 窗体中一个美妙的事情是，它如何将可重用的用户界面 （UI） 代码封装到可重用的 UI 控件中。</span><span class="sxs-lookup"><span data-stu-id="43568-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="43568-105">可以使用 *.ascx*文件在标记中定义自定义用户控件。</span><span class="sxs-lookup"><span data-stu-id="43568-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="43568-106">您还可以在代码中构建详细的服务器控件，并支持完全设计人员。</span><span class="sxs-lookup"><span data-stu-id="43568-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="43568-107">Blazor 还支持通过*组件*进行 UI 封装。</span><span class="sxs-lookup"><span data-stu-id="43568-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="43568-108">组件：</span><span class="sxs-lookup"><span data-stu-id="43568-108">A component:</span></span>

- <span data-ttu-id="43568-109">是 UI 的自包含块。</span><span class="sxs-lookup"><span data-stu-id="43568-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="43568-110">维护自己的状态和呈现逻辑。</span><span class="sxs-lookup"><span data-stu-id="43568-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="43568-111">可以定义 UI 事件处理程序、绑定到输入数据以及管理其自己的生命周期。</span><span class="sxs-lookup"><span data-stu-id="43568-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="43568-112">通常在使用 Razor 语法的 *.razor*文件中定义。</span><span class="sxs-lookup"><span data-stu-id="43568-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="43568-113">剃刀简介</span><span class="sxs-lookup"><span data-stu-id="43568-113">An introduction to Razor</span></span>

<span data-ttu-id="43568-114">Razor 是基于 HTML 和 C# 的轻量级标记模板化语言。</span><span class="sxs-lookup"><span data-stu-id="43568-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="43568-115">使用 Razor，您可以在标记和 C# 代码之间无缝过渡，以定义组件呈现逻辑。</span><span class="sxs-lookup"><span data-stu-id="43568-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="43568-116">编译 *.razor*文件时，呈现逻辑以结构化方式在 .NET 类中捕获。</span><span class="sxs-lookup"><span data-stu-id="43568-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="43568-117">已编译类的名称取自 *.razor*文件名。</span><span class="sxs-lookup"><span data-stu-id="43568-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="43568-118">命名空间取自项目和文件夹路径的默认命名空间，或者您可以使用`@namespace`指令显式指定命名空间（下面有关 Razor 指令的更多）。</span><span class="sxs-lookup"><span data-stu-id="43568-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="43568-119">组件的呈现逻辑使用使用使用 C# 添加的动态逻辑使用普通 HTML 标记进行创作。</span><span class="sxs-lookup"><span data-stu-id="43568-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="43568-120">该`@`字符用于转换为 C#。</span><span class="sxs-lookup"><span data-stu-id="43568-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="43568-121">剃刀通常很聪明，可以找出您何时切换回 HTML。</span><span class="sxs-lookup"><span data-stu-id="43568-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="43568-122">例如，以下组件呈现当前`<p>`时间的标记：</span><span class="sxs-lookup"><span data-stu-id="43568-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="43568-123">要显式指定 C# 表达式的开始和结束，请使用括号：</span><span class="sxs-lookup"><span data-stu-id="43568-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="43568-124">Razor 还便于在渲染逻辑中使用 C# 控制流。</span><span class="sxs-lookup"><span data-stu-id="43568-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="43568-125">例如，您可以有条件地呈现一些 HTML，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43568-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="43568-126">或者，您可以使用正常的 C#`foreach`循环生成项列表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43568-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="43568-127">Razor 指令（如ASP.NET Web 窗体中的指令）控制 Razor 组件的编译方式的许多方面。</span><span class="sxs-lookup"><span data-stu-id="43568-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="43568-128">示例包括组件：</span><span class="sxs-lookup"><span data-stu-id="43568-128">Examples include the component's:</span></span>

- <span data-ttu-id="43568-129">命名空间</span><span class="sxs-lookup"><span data-stu-id="43568-129">Namespace</span></span>
- <span data-ttu-id="43568-130">基类</span><span class="sxs-lookup"><span data-stu-id="43568-130">Base class</span></span>
- <span data-ttu-id="43568-131">实现的接口</span><span class="sxs-lookup"><span data-stu-id="43568-131">Implemented interfaces</span></span>
- <span data-ttu-id="43568-132">泛型参数</span><span class="sxs-lookup"><span data-stu-id="43568-132">Generic parameters</span></span>
- <span data-ttu-id="43568-133">导入的命名空间</span><span class="sxs-lookup"><span data-stu-id="43568-133">Imported namespaces</span></span>
- <span data-ttu-id="43568-134">路由</span><span class="sxs-lookup"><span data-stu-id="43568-134">Routes</span></span>

<span data-ttu-id="43568-135">Razor 指令以`@`字符开头，通常在文件开头的新行开始时使用。</span><span class="sxs-lookup"><span data-stu-id="43568-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="43568-136">例如，`@namespace`指令定义组件的命名空间：</span><span class="sxs-lookup"><span data-stu-id="43568-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="43568-137">下表总结了 Blazor 中使用的各种 Razor 指令及其ASP.NET Web 窗体等效项（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="43568-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="43568-138">指令</span><span class="sxs-lookup"><span data-stu-id="43568-138">Directive</span></span>    |<span data-ttu-id="43568-139">说明</span><span class="sxs-lookup"><span data-stu-id="43568-139">Description</span></span>|<span data-ttu-id="43568-140">示例</span><span class="sxs-lookup"><span data-stu-id="43568-140">Example</span></span>|<span data-ttu-id="43568-141">与 Web 窗体等效</span><span class="sxs-lookup"><span data-stu-id="43568-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="43568-142">向组件添加类级属性</span><span class="sxs-lookup"><span data-stu-id="43568-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="43568-143">无</span><span class="sxs-lookup"><span data-stu-id="43568-143">None</span></span>|
|`@code`      |<span data-ttu-id="43568-144">将类成员添加到组件</span><span class="sxs-lookup"><span data-stu-id="43568-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="43568-145">实现指定的接口</span><span class="sxs-lookup"><span data-stu-id="43568-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="43568-146">使用代码隐藏</span><span class="sxs-lookup"><span data-stu-id="43568-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="43568-147">从指定的基类继承</span><span class="sxs-lookup"><span data-stu-id="43568-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="43568-148">将服务注入组件</span><span class="sxs-lookup"><span data-stu-id="43568-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="43568-149">无</span><span class="sxs-lookup"><span data-stu-id="43568-149">None</span></span>|
|`@layout`    |<span data-ttu-id="43568-150">指定组件的布局组件</span><span class="sxs-lookup"><span data-stu-id="43568-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="43568-151">设置组件的命名空间</span><span class="sxs-lookup"><span data-stu-id="43568-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="43568-152">无</span><span class="sxs-lookup"><span data-stu-id="43568-152">None</span></span>|
|`@page`      |<span data-ttu-id="43568-153">指定组件的路由</span><span class="sxs-lookup"><span data-stu-id="43568-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="43568-154">为组件指定泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="43568-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="43568-155">使用代码隐藏</span><span class="sxs-lookup"><span data-stu-id="43568-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="43568-156">指定要引入作用域的命名空间</span><span class="sxs-lookup"><span data-stu-id="43568-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="43568-157">在*Web.config 中*添加命名空间</span><span class="sxs-lookup"><span data-stu-id="43568-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="43568-158">Razor 组件还广泛使用元素上的*指令属性*来控制组件的编译方式的各个方面（事件处理、数据绑定、组件&元素引用等）。</span><span class="sxs-lookup"><span data-stu-id="43568-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="43568-159">指令属性都遵循一个通用通用语法，其中括号中的值是可选的：</span><span class="sxs-lookup"><span data-stu-id="43568-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="43568-160">下表总结了 Blazor 中使用的 Razor 指令的各种属性。</span><span class="sxs-lookup"><span data-stu-id="43568-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="43568-161">特性</span><span class="sxs-lookup"><span data-stu-id="43568-161">Attribute</span></span>    |<span data-ttu-id="43568-162">说明</span><span class="sxs-lookup"><span data-stu-id="43568-162">Description</span></span>|<span data-ttu-id="43568-163">示例</span><span class="sxs-lookup"><span data-stu-id="43568-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="43568-164">渲染属性字典</span><span class="sxs-lookup"><span data-stu-id="43568-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="43568-165">创建双向数据绑定</span><span class="sxs-lookup"><span data-stu-id="43568-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="43568-166">为指定事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="43568-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="43568-167">指定扩散算法用于保留集合中元素的键</span><span class="sxs-lookup"><span data-stu-id="43568-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="43568-168">捕获对组件或 HTML 元素的引用</span><span class="sxs-lookup"><span data-stu-id="43568-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="43568-169">Blazor （、、、`@onclick``@bind``@ref`等） 使用的各种指令属性在以下各章和后面的章节中介绍。</span><span class="sxs-lookup"><span data-stu-id="43568-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="43568-170">*.aspx*和 *.ascx*文件中使用的许多语法在 Razor 中具有并行语法。</span><span class="sxs-lookup"><span data-stu-id="43568-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="43568-171">下面是ASP.NET Web 窗体和 Razor 的语法的简单比较。</span><span class="sxs-lookup"><span data-stu-id="43568-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="43568-172">Feature</span><span class="sxs-lookup"><span data-stu-id="43568-172">Feature</span></span>                      |<span data-ttu-id="43568-173">Web 窗体</span><span class="sxs-lookup"><span data-stu-id="43568-173">Web Forms</span></span>           |<span data-ttu-id="43568-174">语法</span><span class="sxs-lookup"><span data-stu-id="43568-174">Syntax</span></span>               |<span data-ttu-id="43568-175">Razor</span><span class="sxs-lookup"><span data-stu-id="43568-175">Razor</span></span>         |<span data-ttu-id="43568-176">语法</span><span class="sxs-lookup"><span data-stu-id="43568-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="43568-177">指令</span><span class="sxs-lookup"><span data-stu-id="43568-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="43568-178">代码块</span><span class="sxs-lookup"><span data-stu-id="43568-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="43568-179">表达式</span><span class="sxs-lookup"><span data-stu-id="43568-179">Expressions</span></span><br><span data-ttu-id="43568-180">（HTML 编码）</span><span class="sxs-lookup"><span data-stu-id="43568-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="43568-181">隐 式：`@`</span><span class="sxs-lookup"><span data-stu-id="43568-181">Implicit: `@`</span></span><br><span data-ttu-id="43568-182">明确：`@()`</span><span class="sxs-lookup"><span data-stu-id="43568-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="43568-183">注释</span><span class="sxs-lookup"><span data-stu-id="43568-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="43568-184">数据绑定</span><span class="sxs-lookup"><span data-stu-id="43568-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="43568-185">要将成员添加到 Razor 组件类，请使用`@code`该指令。</span><span class="sxs-lookup"><span data-stu-id="43568-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="43568-186">此技术类似于在ASP.NET Web`<script runat="server">...</script>`窗体用户控件或页面中使用块。</span><span class="sxs-lookup"><span data-stu-id="43568-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="43568-187">由于 Razor 基于 C#，因此必须从 C# 项目中编译它 （*.csproj*）。</span><span class="sxs-lookup"><span data-stu-id="43568-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="43568-188">无法从可视化基础项目 *（.vbproj*） 编译 *.razor*文件。</span><span class="sxs-lookup"><span data-stu-id="43568-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="43568-189">您仍然可以从 Blazor 项目中引用可视化基本项目。</span><span class="sxs-lookup"><span data-stu-id="43568-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="43568-190">事实正好相反。</span><span class="sxs-lookup"><span data-stu-id="43568-190">The opposite is true too.</span></span>

<span data-ttu-id="43568-191">有关完整的 Razor 语法引用，请参阅[ASP.NET 酷睿的 Razor 语法引用](/aspnet/core/mvc/views/razor)。</span><span class="sxs-lookup"><span data-stu-id="43568-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="43568-192">使用组件</span><span class="sxs-lookup"><span data-stu-id="43568-192">Use components</span></span>

<span data-ttu-id="43568-193">除了普通 HTML 之外，组件还可以使用其他组件作为其呈现逻辑的一部分。</span><span class="sxs-lookup"><span data-stu-id="43568-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="43568-194">在 Razor 中使用组件的语法类似于在 ASP.NET Web 窗体应用中使用用户控件。</span><span class="sxs-lookup"><span data-stu-id="43568-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="43568-195">使用与组件的类型名称匹配的元素标记指定组件。</span><span class="sxs-lookup"><span data-stu-id="43568-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="43568-196">例如，您可以添加如下所示的`Counter`组件：</span><span class="sxs-lookup"><span data-stu-id="43568-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="43568-197">与ASP.NET Web 窗体不同，Blazor 中的组件：</span><span class="sxs-lookup"><span data-stu-id="43568-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="43568-198">不要使用元素前缀（例如， `asp:`。</span><span class="sxs-lookup"><span data-stu-id="43568-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="43568-199">不需要在页面或*Web*上注册。</span><span class="sxs-lookup"><span data-stu-id="43568-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="43568-200">像想象一下 Razor 组件，就像您那样，可以.NET 类型，因为这正是它们。</span><span class="sxs-lookup"><span data-stu-id="43568-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="43568-201">如果引用了包含组件的程序集，则该组件可供使用。</span><span class="sxs-lookup"><span data-stu-id="43568-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="43568-202">要将组件的命名空间引入范围，请应用该`@using`指令：</span><span class="sxs-lookup"><span data-stu-id="43568-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="43568-203">如默认 Blazor 项目中所示，通常将指令放入`@using` *_Imports.razor*文件中，以便它们导入到同一目录中的所有 *.razor*文件中以及子目录中。</span><span class="sxs-lookup"><span data-stu-id="43568-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="43568-204">如果组件的命名空间不在作用域中，则可以使用组件的完整类型名称指定组件，如在 C# 中：</span><span class="sxs-lookup"><span data-stu-id="43568-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="43568-205">组件参数</span><span class="sxs-lookup"><span data-stu-id="43568-205">Component parameters</span></span>

<span data-ttu-id="43568-206">在ASP.NET Web 窗体中，可以使用公共属性将参数和数据流向控件。</span><span class="sxs-lookup"><span data-stu-id="43568-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="43568-207">这些属性可以使用属性在标记中设置，也可以直接在代码中设置。</span><span class="sxs-lookup"><span data-stu-id="43568-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="43568-208">Blazor 组件的工作方式类似，尽管组件属性还必须使用要被视为组件参数`[Parameter]`的属性进行标记。</span><span class="sxs-lookup"><span data-stu-id="43568-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="43568-209">以下`Counter`组件定义一个组件参数，该`IncrementAmount`参数可用于指定每次单击按钮时`Counter`应递增的金额。</span><span class="sxs-lookup"><span data-stu-id="43568-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="43568-210">要在 Blazor 中指定组件参数，请使用ASP.NET Web 窗体中的属性：</span><span class="sxs-lookup"><span data-stu-id="43568-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="43568-211">事件处理程序</span><span class="sxs-lookup"><span data-stu-id="43568-211">Event handlers</span></span>

<span data-ttu-id="43568-212">ASP.NET Web 窗体和 Blazor 都提供了一个基于事件的编程模型来处理 UI 事件。</span><span class="sxs-lookup"><span data-stu-id="43568-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="43568-213">此类事件的示例包括按钮单击和文本输入。</span><span class="sxs-lookup"><span data-stu-id="43568-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="43568-214">在ASP.NET Web 窗体中，您可以使用 HTML 服务器控件来处理 DOM 公开的 UI 事件，也可以处理 Web 服务器控件公开的事件。</span><span class="sxs-lookup"><span data-stu-id="43568-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="43568-215">事件通过回后表单请求在服务器上显示。</span><span class="sxs-lookup"><span data-stu-id="43568-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="43568-216">请考虑以下 Web 窗体按钮单击示例：</span><span class="sxs-lookup"><span data-stu-id="43568-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="43568-217">*计数器.ascx*</span><span class="sxs-lookup"><span data-stu-id="43568-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="43568-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="43568-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="43568-219">在 Blazor 中，可以直接使用窗体`@on{event}`的指令属性注册 DOM UI 事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="43568-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="43568-220">占`{event}`位符表示事件的名称。</span><span class="sxs-lookup"><span data-stu-id="43568-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="43568-221">例如，您可以侦听按钮单击，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43568-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="43568-222">事件处理程序可以接受可选的特定于事件的参数来提供有关该事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="43568-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="43568-223">例如，鼠标事件可以采用`MouseEventArgs`参数，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="43568-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="43568-224">可以使用 lambda 表达式，而不是引用事件处理程序的方法组。</span><span class="sxs-lookup"><span data-stu-id="43568-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="43568-225">lambda 表达式允许您关闭其他范围内值。</span><span class="sxs-lookup"><span data-stu-id="43568-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="43568-226">事件处理程序可以同步或异步执行。</span><span class="sxs-lookup"><span data-stu-id="43568-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="43568-227">例如，以下`OnClick`事件处理程序异步执行：</span><span class="sxs-lookup"><span data-stu-id="43568-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="43568-228">处理事件后，组件将呈现为考虑任何组件状态更改。</span><span class="sxs-lookup"><span data-stu-id="43568-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="43568-229">使用异步事件处理程序，在处理程序执行完成后立即呈现组件。</span><span class="sxs-lookup"><span data-stu-id="43568-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="43568-230">异步`Task`完成后 *，将再次*呈现组件。</span><span class="sxs-lookup"><span data-stu-id="43568-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="43568-231">此异步执行模式提供了在异步`Task`仍在进行时呈现一些适当 UI 的机会。</span><span class="sxs-lookup"><span data-stu-id="43568-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="43568-232">组件还可以通过定义类型的`EventCallback<TValue>`组件参数来定义自己的事件。</span><span class="sxs-lookup"><span data-stu-id="43568-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="43568-233">事件回调支持 DOM UI 事件处理程序的所有变体：可选参数、同步或异步、方法组或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="43568-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="43568-234">数据绑定</span><span class="sxs-lookup"><span data-stu-id="43568-234">Data binding</span></span>

<span data-ttu-id="43568-235">Blazor 提供了一种将数据从 UI 组件绑定到组件状态的简单机制。</span><span class="sxs-lookup"><span data-stu-id="43568-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="43568-236">此方法不同于 ASP.NET Web 窗体中用于将数据从数据源绑定到 UI 控件的功能。</span><span class="sxs-lookup"><span data-stu-id="43568-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="43568-237">我们将在["处理数据"](data.md)部分中介绍处理来自不同数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="43568-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="43568-238">要创建从 UI 组件到组件状态的双向数据绑定，请使用`@bind`指令属性。</span><span class="sxs-lookup"><span data-stu-id="43568-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="43568-239">在下面的示例中，复选框的值绑定到该`isChecked`字段。</span><span class="sxs-lookup"><span data-stu-id="43568-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="43568-240">呈现组件时，复选框的值将设置为`isChecked`字段的值。</span><span class="sxs-lookup"><span data-stu-id="43568-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="43568-241">当用户切换复选框时，将`onchange`触发事件并将`isChecked`该字段设置为新值。</span><span class="sxs-lookup"><span data-stu-id="43568-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="43568-242">在这种情况下`@bind`，语法等效于以下标记：</span><span class="sxs-lookup"><span data-stu-id="43568-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="43568-243">要更改用于绑定的事件，请使用 属性`@bind:event`。</span><span class="sxs-lookup"><span data-stu-id="43568-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="43568-244">组件还可以支持绑定到其参数的数据。</span><span class="sxs-lookup"><span data-stu-id="43568-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="43568-245">要绑定数据，请定义与可绑定参数同名的事件回调参数。</span><span class="sxs-lookup"><span data-stu-id="43568-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="43568-246">"已更改"后缀将添加到名称中。</span><span class="sxs-lookup"><span data-stu-id="43568-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="43568-247">*密码盒.剃须刀*</span><span class="sxs-lookup"><span data-stu-id="43568-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="43568-248">要将数据绑定链接到基础 UI 元素，请使用 该值设置值并直接在 UI 元素上处理事件`@bind`，而不是使用 属性。</span><span class="sxs-lookup"><span data-stu-id="43568-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="43568-249">要绑定到组件参数，请使用属性`@bind-{Parameter}`指定要绑定到的参数。</span><span class="sxs-lookup"><span data-stu-id="43568-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="43568-250">状态更改</span><span class="sxs-lookup"><span data-stu-id="43568-250">State changes</span></span>

<span data-ttu-id="43568-251">如果组件的状态在正常 UI 事件或事件回调之外已更改，则组件必须手动发出信号，表示需要再次呈现该组件。</span><span class="sxs-lookup"><span data-stu-id="43568-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="43568-252">要发出组件状态已更改的信号，请调用组件上`StateHasChanged`的方法。</span><span class="sxs-lookup"><span data-stu-id="43568-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="43568-253">在下面的示例中，组件显示`AppState`来自服务的消息，该消息可以由应用的其他部分更新。</span><span class="sxs-lookup"><span data-stu-id="43568-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="43568-254">组件将其`StateHasChanged`方法注册到事件中`AppState.OnChange`，以便每当消息更新时都会呈现该组件。</span><span class="sxs-lookup"><span data-stu-id="43568-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="43568-255">组件生命周期</span><span class="sxs-lookup"><span data-stu-id="43568-255">Component lifecycle</span></span>

<span data-ttu-id="43568-256">ASP.NET Web 窗体框架为模块、页面和控制定义了明确的生命周期方法。</span><span class="sxs-lookup"><span data-stu-id="43568-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="43568-257">例如，以下控件为`Init`和`Load`和`UnLoad`生命周期事件实现事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="43568-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="43568-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="43568-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="43568-259">Blazor 组件也有定义明确的生命周期。</span><span class="sxs-lookup"><span data-stu-id="43568-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="43568-260">组件的生命周期可用于初始化组件状态并实现高级组件行为。</span><span class="sxs-lookup"><span data-stu-id="43568-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="43568-261">Blazor 的所有组件生命周期方法都具有同步和异步版本。</span><span class="sxs-lookup"><span data-stu-id="43568-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="43568-262">组件呈现是同步的。</span><span class="sxs-lookup"><span data-stu-id="43568-262">Component rendering is synchronous.</span></span> <span data-ttu-id="43568-263">不能作为组件呈现的一部分运行异步逻辑。</span><span class="sxs-lookup"><span data-stu-id="43568-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="43568-264">所有异步逻辑都必须作为生命周期方法的一`async`部分执行。</span><span class="sxs-lookup"><span data-stu-id="43568-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="43568-265">初始化时</span><span class="sxs-lookup"><span data-stu-id="43568-265">OnInitialized</span></span>

<span data-ttu-id="43568-266">和`OnInitialized``OnInitializedAsync`方法用于初始化组件。</span><span class="sxs-lookup"><span data-stu-id="43568-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="43568-267">组件通常在首次呈现后初始化。</span><span class="sxs-lookup"><span data-stu-id="43568-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="43568-268">初始化组件后，在最终释放组件之前，可能会多次呈现该组件。</span><span class="sxs-lookup"><span data-stu-id="43568-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="43568-269">该方法`OnInitialized`类似于ASP.NET Web`Page_Load`窗体页和控件中的事件。</span><span class="sxs-lookup"><span data-stu-id="43568-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="43568-270">在参数设置上</span><span class="sxs-lookup"><span data-stu-id="43568-270">OnParametersSet</span></span>

<span data-ttu-id="43568-271">当`OnParametersSet`组件`OnParametersSetAsync`从其父组件接收参数并将值分配给属性时，将调用 和 方法。</span><span class="sxs-lookup"><span data-stu-id="43568-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="43568-272">这些方法在组件初始化后以及*每次呈现组件时*执行。</span><span class="sxs-lookup"><span data-stu-id="43568-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="43568-273">在渲染后打开</span><span class="sxs-lookup"><span data-stu-id="43568-273">OnAfterRender</span></span>

<span data-ttu-id="43568-274">和`OnAfterRender``OnAfterRenderAsync`方法在组件完成呈现后调用。</span><span class="sxs-lookup"><span data-stu-id="43568-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="43568-275">此时将填充元素和组件引用（下面将介绍这些概念的更多内容）。</span><span class="sxs-lookup"><span data-stu-id="43568-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="43568-276">此时启用了与浏览器的交互性。</span><span class="sxs-lookup"><span data-stu-id="43568-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="43568-277">与 DOM 和 JavaScript 执行的交互可以安全地发生。</span><span class="sxs-lookup"><span data-stu-id="43568-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="43568-278">`OnAfterRender`并在`OnAfterRenderAsync`*服务器上预渲染时不调用*。</span><span class="sxs-lookup"><span data-stu-id="43568-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="43568-279">参数`firstRender`是`true`首次呈现组件;否则，其值为`false`。</span><span class="sxs-lookup"><span data-stu-id="43568-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="43568-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="43568-280">IDisposable</span></span>

<span data-ttu-id="43568-281">Blazor 组件可以`IDisposable`实现在从 UI 中删除组件时释放资源。</span><span class="sxs-lookup"><span data-stu-id="43568-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="43568-282">Razor 组件可以使用`IDispose``@implements`该指令实现：</span><span class="sxs-lookup"><span data-stu-id="43568-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="43568-283">捕获组件引用</span><span class="sxs-lookup"><span data-stu-id="43568-283">Capture component references</span></span>

<span data-ttu-id="43568-284">在ASP.NET Web 窗体中，通常通过引用控件实例的 ID 来直接在代码中操作控件实例。</span><span class="sxs-lookup"><span data-stu-id="43568-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="43568-285">在 Blazor 中，还可以捕获和操作对组件的引用，尽管它不太常见。</span><span class="sxs-lookup"><span data-stu-id="43568-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="43568-286">要在 Blazor 中捕获组件引用，`@ref`请使用指令属性。</span><span class="sxs-lookup"><span data-stu-id="43568-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="43568-287">属性的值应与与引用的组件类型相同的可设置字段的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="43568-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="43568-288">呈现父组件时，该字段将填充子组件实例。</span><span class="sxs-lookup"><span data-stu-id="43568-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="43568-289">然后，您可以调用组件实例上的方法或以其他方式操作组件实例。</span><span class="sxs-lookup"><span data-stu-id="43568-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="43568-290">不建议直接使用组件引用操作组件状态。</span><span class="sxs-lookup"><span data-stu-id="43568-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="43568-291">这样做可防止组件在正确的时间自动呈现。</span><span class="sxs-lookup"><span data-stu-id="43568-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="43568-292">捕获元素引用</span><span class="sxs-lookup"><span data-stu-id="43568-292">Capture element references</span></span>

<span data-ttu-id="43568-293">Blazor 组件可以捕获对元素的引用。</span><span class="sxs-lookup"><span data-stu-id="43568-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="43568-294">与ASP.NET Web 窗体中的 HTML 服务器控件不同，不能直接使用 Blazor 中的元素引用操作 DOM。</span><span class="sxs-lookup"><span data-stu-id="43568-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="43568-295">Blazor 使用 DOM 扩散算法为您处理大多数 DOM 交互。</span><span class="sxs-lookup"><span data-stu-id="43568-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="43568-296">Blazor 中捕获的元素引用不透明。</span><span class="sxs-lookup"><span data-stu-id="43568-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="43568-297">但是，它们用于传递 JavaScript 互操作调用中的特定元素引用。</span><span class="sxs-lookup"><span data-stu-id="43568-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="43568-298">有关 JavaScript 互通的详细信息，请参阅[ASP.NET核心 Blazor JavaScript 互通](/aspnet/core/blazor/javascript-interop)。</span><span class="sxs-lookup"><span data-stu-id="43568-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="43568-299">模板化组件</span><span class="sxs-lookup"><span data-stu-id="43568-299">Templated components</span></span>

<span data-ttu-id="43568-300">在ASP.NET Web 窗体中，您可以创建*模板化控件*。</span><span class="sxs-lookup"><span data-stu-id="43568-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="43568-301">模板化控件使开发人员能够指定用于呈现容器控件的 HTML 的一部分。</span><span class="sxs-lookup"><span data-stu-id="43568-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="43568-302">构建模板化服务器控件的机制非常复杂，但它们支持以用户自定义的方式呈现数据的强大方案。</span><span class="sxs-lookup"><span data-stu-id="43568-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="43568-303">模板化控件的示例包括`Repeater`和`DataList`。</span><span class="sxs-lookup"><span data-stu-id="43568-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="43568-304">Blazor 组件也可以通过定义类型`RenderFragment`或`RenderFragment<T>`的组件参数进行模板化。</span><span class="sxs-lookup"><span data-stu-id="43568-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="43568-305">表示`RenderFragment`Razor 标记块，然后由组件呈现。</span><span class="sxs-lookup"><span data-stu-id="43568-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="43568-306">A`RenderFragment<T>`是 Razor 标记的块，它采用在渲染渲染片段时可以指定的参数。</span><span class="sxs-lookup"><span data-stu-id="43568-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="43568-307">子内容</span><span class="sxs-lookup"><span data-stu-id="43568-307">Child content</span></span>

<span data-ttu-id="43568-308">Blazor 组件可以捕获其子内容作为`RenderFragment`，并将该内容呈现为组件呈现的一部分。</span><span class="sxs-lookup"><span data-stu-id="43568-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="43568-309">要捕获子内容，请定义类型的`RenderFragment`组件参数并将其`ChildContent`命名为 。</span><span class="sxs-lookup"><span data-stu-id="43568-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="43568-310">*子内容组件.razor*</span><span class="sxs-lookup"><span data-stu-id="43568-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="43568-311">然后，父组件可以使用正常的 Razor 语法提供子内容。</span><span class="sxs-lookup"><span data-stu-id="43568-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="43568-312">模板参数</span><span class="sxs-lookup"><span data-stu-id="43568-312">Template parameters</span></span>

<span data-ttu-id="43568-313">模板化的 Blazor 组件还可以定义类型`RenderFragment`或`RenderFragment<T>`的多个组件参数。</span><span class="sxs-lookup"><span data-stu-id="43568-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="43568-314">调用 时可以`RenderFragment<T>`指定 的 参数。</span><span class="sxs-lookup"><span data-stu-id="43568-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="43568-315">要为组件指定泛型类型参数，请使用`@typeparam`Razor 指令。</span><span class="sxs-lookup"><span data-stu-id="43568-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="43568-316">*简单列表查看.剃须刀*</span><span class="sxs-lookup"><span data-stu-id="43568-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="43568-317">使用模板化组件时，可以使用与参数名称匹配的子元素指定模板参数。</span><span class="sxs-lookup"><span data-stu-id="43568-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="43568-318">`RenderFragment<T>`作为元素传递的类型组件参数具有名为 的`context`隐式参数。</span><span class="sxs-lookup"><span data-stu-id="43568-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="43568-319">您可以使用子元素上`Context`的属性更改此实现参数的名称。</span><span class="sxs-lookup"><span data-stu-id="43568-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="43568-320">可以使用与类型参数名称匹配的属性指定任何泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="43568-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="43568-321">如果可能，将推断类型参数：</span><span class="sxs-lookup"><span data-stu-id="43568-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="43568-322">此组件的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="43568-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="43568-323">代码隐藏</span><span class="sxs-lookup"><span data-stu-id="43568-323">Code-behind</span></span>

<span data-ttu-id="43568-324">Blazor 组件通常创作在单个 *.razor*文件中。</span><span class="sxs-lookup"><span data-stu-id="43568-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="43568-325">但是，也可以使用代码背后的文件分隔代码和标记。</span><span class="sxs-lookup"><span data-stu-id="43568-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="43568-326">要使用组件文件，添加与组件文件的文件名匹配但添加了 *.cs*扩展名 *（Counter.razor.cs*） 的 C# 文件。</span><span class="sxs-lookup"><span data-stu-id="43568-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="43568-327">使用 C# 文件为组件定义基类。</span><span class="sxs-lookup"><span data-stu-id="43568-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="43568-328">您可以命名基类的任何内容，但通常将类命名为与组件类相同，但添加了`Base`扩展项 （）。`CounterBase`</span><span class="sxs-lookup"><span data-stu-id="43568-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="43568-329">基于组件的类也必须派生自`ComponentBase`。</span><span class="sxs-lookup"><span data-stu-id="43568-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="43568-330">然后，在 Razor 组件文件中，添加`@inherits`指令以指定组件的基类 （。`@inherits CounterBase`</span><span class="sxs-lookup"><span data-stu-id="43568-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="43568-331">*计数器.剃须刀*</span><span class="sxs-lookup"><span data-stu-id="43568-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="43568-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="43568-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="43568-333">基类中组件成员的可见性必须`protected`为或`public`对组件类可见。</span><span class="sxs-lookup"><span data-stu-id="43568-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43568-334">其他资源</span><span class="sxs-lookup"><span data-stu-id="43568-334">Additional resources</span></span>

<span data-ttu-id="43568-335">前面不是对Blazor组件所有方面的详尽处理。</span><span class="sxs-lookup"><span data-stu-id="43568-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="43568-336">有关如何[创建和使用核心剃须刀组件ASP.NET](/aspnet/core/blazor/components)的详细信息，请参阅 Blazor 文档。</span><span class="sxs-lookup"><span data-stu-id="43568-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="43568-337">[上一个](app-startup.md)
>[下一个](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="43568-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
