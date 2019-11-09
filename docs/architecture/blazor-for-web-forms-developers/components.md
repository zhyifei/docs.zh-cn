---
title: 使用 Blazor 生成可重复使用的 UI 组件
description: 了解如何使用 Blazor 生成可重复使用的 UI 组件，以及如何将其与 ASP.NET Web 窗体控件进行比较。
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 79919b183a4eb759f0b27c97500ee71c9378770b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841959"
---
# <a name="build-reusable-ui-components-with-blazor"></a>使用 Blazor 生成可重复使用的 UI 组件

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

有关 ASP.NET Web 窗体的一项精彩功能，就是它如何使可重用的用户界面（UI）代码块可用于可重复使用的 UI 控件。 可以使用 *.ascx*文件在标记中定义自定义用户控件。 你还可以在代码中生成具有完全设计器支持的精致服务器控件。

Blazor 还支持通过*组件*进行 UI 封装。 组件：

- 是一个独立的 UI 块区。
- 维护其自己的状态和呈现逻辑。
- 可以定义 UI 事件处理程序、绑定到输入数据，并管理其自己的生命周期。
- 通常使用 Razor 语法在*razor*文件中定义。

## <a name="an-introduction-to-razor"></a>Razor 简介

Razor 是基于 HTML 和C#的轻型标记模板化语言。 借助 Razor，你可以在标记和C#代码之间无缝转换，以定义你的组件呈现逻辑。 在编译*razor*文件时，呈现逻辑在 .net 类中以结构化的方式捕获。 已编译类的名称是从*razor*文件名获取的。 命名空间是从项目的默认命名空间和文件夹路径获取的，或者可以使用 `@namespace` 指令显式指定命名空间（更多以下 Razor 指令）。

组件的呈现逻辑使用普通的 HTML 标记编写，动态逻辑标记是使用C#添加的。 `@` 字符用于转换为C#。 Razor 通常会巧妙地了解何时切换回 HTML。 例如，以下组件将 `<p>` 标记呈现为当前时间：

```razor
<p>@DateTime.Now</p>
```

若要显式指定C#表达式的开头和结尾，请使用括号：

```razor
<p>@(DateTime.Now)</p>
```

使用 Razor 还可以轻松地在C#呈现逻辑中使用控制流。 例如，你可以有条件地呈现一些 HTML，如下所示：

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

或者，可以使用如下所示的普通C# `foreach` 循环生成项列表：

```razor
<ul>
@foreach (var item in items)
{
    <li>item.Text</li>
}
</ul>
```

Razor 指令（如 ASP.NET Web 窗体中的指令）控制如何编译 Razor 组件的许多方面。 示例包括组件的：

- Namespace
- 基类
- 实现的接口
- 泛型参数
- 导入的命名空间
- 路由

Razor 指令以 `@` 字符开始，通常在文件开头的新行的开头使用。 例如，`@namespace` 指令定义组件的命名空间：

```razor
@namespace MyComponentNamespace
```

下表汇总了 Blazor 中使用的各种 Razor 指令及其等效的 ASP.NET Web 窗体（如果存在）。

|指令    |描述|示例|Web 窗体等效项|
|-------------|-----------|-------|--------------------|
|`@attribute` |向组件添加类级别属性|`@attribute [Authorize]`|None|
|`@code`      |将类成员添加到组件|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|实现指定接口|`@implements IDisposable`|使用代码隐藏|
|`@inherits`  |继承自指定的基类|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |将服务注入组件|`@inject IJSRuntime JS`|None|
|`@layout`    |指定组件的布局组件|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |设置组件的命名空间|`@namespace MyNamespace`|None|
|`@page`      |指定组件的路由|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |指定组件的泛型类型参数|`@typeparam TItem`|使用代码隐藏|
|`@using`     |指定要引入作用域的命名空间|`@using MyComponentNamespace`|*在 web.config*中添加命名空间|

Razor 组件还广泛使用元素上的*指令属性*，以控制如何编译组件（事件处理、数据绑定、组件 & 元素引用等）的各个方面。 指令特性都遵循通用通用语法，其中括号中的值是可选的：

```razor
@directive(-suffix(:name))(="value")
```

下表总结了 Blazor 中使用的 Razor 指令的各种属性。

|特性    |描述|示例|
|-------------|-----------|-------|
|`@attributes`|呈现特性字典|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |创建双向数据绑定    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |为指定的事件添加事件处理程序|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |指定由比较算法用来保留集合中元素的键|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |捕获对组件或 HTML 元素的引用|`<MyDialog @ref="myDialog" />`|

Blazor （`@onclick`、`@bind`、`@ref`等）使用的各种指令属性将在以下章节和更后面章节中介绍。

*.Aspx*和 *.ascx*文件中使用的很多语法在 Razor 中具有并行语法。 下面是 ASP.NET Web 窗体和 Razor 语法的简单比较。

|功能                      |Web Forms — Web 窗体           |语法               |Razor         |语法 |
|-----------------------------|--------------------|---------------------|--------------|-------|
|指令                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|代码块                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|表达式<br>（HTML 编码）|`<%: %>`            |`<%:DateTime.Now %>` |隐式： `@`<br>显式： `@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|注释                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|数据绑定                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

若要将成员添加到 Razor 组件类，请使用 `@code` 指令。 此方法类似于在 ASP.NET Web 窗体用户控件或页面中使用 `<script runat="server">...</script>` 块。

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

由于 Razor 基于C#，因此它必须从C#项目（ *.csproj*）中进行编译。 不能从 VB 项目（ *. .vbproj*）编译*razor*文件。 你仍可以从 Blazor 项目引用 VB 项目。 相反的情况也是如此。

有关完整 Razor 语法引用，请参阅[ASP.NET Core 的 Razor 语法参考](/aspnet/core/mvc/views/razor)。

## <a name="use-components"></a>使用组件

除了正常 HTML，组件还可以使用其他组件作为其呈现逻辑的一部分。 在 Razor 中使用组件的语法类似于在 ASP.NET Web 窗体应用程序中使用用户控件。 使用与组件的类型名称匹配的元素标记指定组件。 例如，可以添加如下所示的 `Counter` 组件：

```razor
<Counter />
```

与 ASP.NET Web 窗体不同，Blazor 中的组件：

- 不要使用元素前缀（例如 `asp:`）。
- 不需要在页面上或在*web.config*中注册。

像您的 .NET 类型一样，可以像您这样做，因为这正是它们的作用。 如果引用包含组件的程序集，则可以使用该组件。 若要将组件的命名空间引入作用域，请应用 `@using` 指令：

```razor
@using MyComponentLib

<Counter />
```

如默认 Blazor 项目中所示，通常将 `@using` 指令放入 *_Imports*文件中，以便将它们导入到同一目录和子目录中的所有*razor*文件中。

如果某个组件的命名空间不在范围内，则可以使用它的完整类型名称指定组件，如下所示C#：

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>组件参数

在 ASP.NET Web 窗体中，你可以使用公共属性将参数和数据流式传输到控件。 可以使用特性在标记中设置这些属性，也可以在代码中直接设置这些属性。 Blazor 组件的工作方式类似，不过，组件属性还必须标记为要被视为组件参数 `[Parameter]` 特性。

以下 `Counter` 组件定义了一个名为 `IncrementAmount` 的组件参数，该参数可用于指定每次单击按钮时 `Counter` 应增加的量。

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

若要在 Blazor 中指定组件参数，请使用 ASP.NET Web 窗体中的属性：

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>事件处理程序

ASP.NET Web 窗体和 Blazor 都提供用于处理 UI 事件的基于事件的编程模型。 此类事件的示例包括按钮单击和文本输入。 在 ASP.NET Web 窗体中，您可以使用 HTML 服务器控件处理 DOM 公开的 UI 事件，也可以处理 Web 服务器控件公开的事件。 这些事件通过窗体回发请求出现在服务器上。 请考虑以下 Web 窗体按钮单击示例：

*Counter*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

在 Blazor 中，可以使用窗体 `@on{event}`的指令特性直接注册 DOM UI 事件的处理程序。 `{event}` 占位符表示事件的名称。 例如，您可以按如下所示侦听按钮单击操作：

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

事件处理程序可接受可选的特定于事件的自变量来提供有关事件的详细信息。 例如，鼠标事件可以采用 `MouseEventArgs` 参数，但这不是必需的。

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

您可以使用 lambda 表达式，而不是引用事件处理程序的方法组。 Lambda 表达式允许您关闭其他范围内的值。

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

事件处理程序可以同步执行，也可以异步执行。 例如，以下 `OnClick` 事件处理程序以异步方式执行：

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

处理事件后，将呈现组件以考虑任何组件状态更改。 对于异步事件处理程序，该组件将在处理程序执行完成后立即呈现。 异步 `Task` 完成后，会*再次*呈现该组件。 此异步执行模式提供了在异步 `Task` 仍在进行时呈现一些适当 UI 的机会。

```razor
<button @onclick="Get message">Get message</button>

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

组件还可以通过定义 `EventCallback<TValue>`类型的组件参数来定义自己的事件。 事件回调支持 DOM UI 事件处理程序的所有变体：可选参数、同步或异步、方法组或 lambda 表达式。

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>数据绑定

Blazor 提供了一种简单的机制，用于将数据从 UI 组件绑定到组件的状态。 此方法不同于 ASP.NET Web 窗体中的功能，可用于将数据从数据源绑定到 UI 控件。 在处理[数据](data.md)部分，我们将介绍如何处理来自不同数据源的数据。

若要创建从 UI 组件到组件状态的双向数据绑定，请使用 `@bind` 指令特性。 在下面的示例中，复选框的值绑定到 `isChecked` 字段。

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

呈现组件时，复选框的值将设置为 "`isChecked`" 字段的值。 当用户切换复选框时，将激发 `onchange` 事件，并将 `isChecked` 字段设置为新值。 在此示例中，`@bind` 语法等效于以下标记：

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

若要更改用于绑定的事件，请使用 `@bind:event` 特性。

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

组件还可以支持数据绑定到其参数。 若要进行数据绑定，请使用与可绑定参数相同的名称定义事件回调参数。 "更改的" 后缀将添加到名称中。

*PasswordBox*

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

若要将数据绑定链接到基础 UI 元素，请设置值并直接在 UI 元素上处理事件，而不是使用 `@bind` 特性。

若要绑定到组件参数，请使用 `@bind-{Parameter}` 特性来指定要绑定到的参数。

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>状态更改

如果组件的状态在正常的 UI 事件或事件回调之外发生了更改，则组件必须手动通知其需要再次呈现。 若要指示组件状态已更改，请对组件调用 `StateHasChanged` 方法。

在下面的示例中，组件显示来自 `AppState` 服务的消息，该消息可以由应用程序的其他部分更新。 组件向 `AppState.OnChange` 事件注册其 `StateHasChanged` 方法，以便每当消息被更新时呈现该组件。

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

## <a name="component-lifecycle"></a>组件生命周期

ASP.NET Web 窗体框架为模块、页和控件提供了定义完善的生命周期方法。 例如，下面的控件为 `Init`、`Load`和 `UnLoad` 生命周期事件实现事件处理程序：

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor 组件还具有定义完善的生命周期。 组件的生命周期可用于初始化组件状态和实现高级组件行为。

所有 Blazor 的组件生命周期方法都有同步和异步版本。 组件呈现是同步的。 无法在呈现组件的过程中运行异步逻辑。 所有异步逻辑都必须作为 `async` 生命周期方法的一部分执行。

### <a name="oninitialized"></a>OnInitialized

`OnInitialized` 和 `OnInitializedAsync` 方法用于初始化组件。 通常在第一次呈现组件后对其进行初始化。 组件初始化后，它可能会在最终被释放之前呈现多次。 `OnInitialized` 方法类似于 ASP.NET Web 窗体页和控件中的 `Page_Load` 事件。

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

当组件已从其父级接收参数并且为属性分配了值时，将调用 `OnParametersSet` 和 `OnParametersSetAsync` 方法。 这些方法在组件初始化之后以及*每次呈现组件*时执行。

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

`OnAfterRender` 和 `OnAfterRenderAsync` 方法在组件完成呈现后调用。 此时将填充元素和组件引用（有关这些概念的详细信息，请参阅下文）。 此时启用了与浏览器的交互。 可以安全地进行与 DOM 和 JavaScript 执行的交互。

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

在*服务器上预呈现时不会调用*`OnAfterRender` 和 `OnAfterRenderAsync`。

第一次呈现组件时 `true` `firstRender` 参数;否则，将 `false`其值。

### <a name="idisposable"></a>IDisposable

当从 UI 中删除组件时，Blazor 组件可以实现 `IDisposable` 来释放资源。 Razor 组件可以通过使用 `@implements` 指令来实现 `IDispose`：

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

## <a name="capture-component-references"></a>捕获组件引用

在 ASP.NET Web 窗体中，通常通过引用控件的 ID 来直接在代码中处理控件实例。 在 Blazor 中，还可以捕获和操作对组件的引用，尽管它不太常见。

若要在 Blazor 中捕获组件引用，请使用 `@ref` 指令特性。 属性的值应与所引用组件的类型相同的可设置字段的名称匹配。

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

呈现父组件时，将用子组件实例填充字段。 然后，你可以对组件实例调用方法或其他操作。

不建议直接使用组件引用操控组件状态。 这样做可以防止在正确的时间自动呈现组件。

## <a name="capture-element-references"></a>捕获元素引用

Blazor 组件可以捕获对元素的引用。 与 ASP.NET Web 窗体中的 HTML 服务器控件不同，您不能直接使用 Blazor 中的元素引用来操作 DOM。 Blazor 使用其 DOM 比较算法处理大多数 DOM 交互。 Blazor 中捕获的元素引用不透明。 但是，它们用于在 JavaScript 互操作调用中传递特定的元素引用。 有关 JavaScript 互操作的详细信息，请参阅[ASP.NET Core Blazor JavaScript 互操作](/aspnet/core/blazor/javascript-interop)。

## <a name="templated-components"></a>模板化组件

在 ASP.NET Web 窗体中，您可以创建*模板化控件*。 模板化控件使开发人员可以指定用于呈现容器控件的 HTML 部分。 构建模板化服务器控件的机制非常复杂，但它们可让用户以用户可自定义的方式呈现数据。 模板化控件的示例包括 `Repeater` 和 `DataList`。

还可以通过定义 `RenderFragment` 或 `RenderFragment<T>`类型的组件参数，模板化 Blazor 组件。 一个 `RenderFragment` 表示 Razor 标记的块区，该标记随后可由组件呈现。 `RenderFragment<T>` 是 Razor 标记的块区，它采用可在呈现呈现片段时指定的参数。

### <a name="child-content"></a>子内容

Blazor 组件可以将其子内容捕获为 `RenderFragment`，并在呈现组件时呈现该内容。 若要捕获子内容，请定义类型 `RenderFragment` 的组件参数，并将其命名为 `ChildContent`。

*ChildContentComponent*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

然后，父组件可以使用普通 Razor 语法提供子内容。

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>模板参数

模板化 Blazor 组件还可以定义 `RenderFragment` 或 `RenderFragment<T>`类型的多个组件参数。 调用时可以指定 `RenderFragment<T>` 的参数。 若要为组件指定泛型类型参数，请使用 `@typeparam` Razor 指令。

*SimpleListView*

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

使用模板化组件时，可以使用与参数名称匹配的子元素指定模板参数。 作为元素传递的类型 `RenderFragment<T>` 的组件参数具有一个名为 `context`的隐式参数。 您可以使用子元素上的 `Context` 特性更改此实现参数的名称。 可以使用与类型参数的名称匹配的特性指定任何泛型类型参数。 如果可能，将推断类型参数：

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

此组件的输出如下所示：

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>代码隐藏

Blazor 组件通常是在单个*razor*文件中创作的。 不过，也可以使用代码隐藏文件来分隔代码和标记。 若要使用组件文件，请添加C#一个与组件文件的文件名相匹配的文件，但添加了 *.cs*扩展名（*Counter.razor.cs*）。 使用C#文件定义组件的基类。 您可以将基类命名为任何所需的名称，但通常会将类命名为与 component 类相同，但添加了 `Base` 扩展（`CounterBase`）。 基于组件的类还必须派生自 `ComponentBase`。 然后，在 Razor 组件文件中添加 `@inherits` 指令以指定组件的基类（`@inherits CounterBase`）。

*Counter*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

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

基类中组件成员的可见性必须是 `protected` 或 `public` 才能对组件类可见。

## <a name="additional-resources"></a>其他资源

前面不是 Blazor 组件的所有方面的全面处理。 有关如何[创建和使用 ASP.NET Core Razor 组件](/aspnet/core/blazor/components)的详细信息，请参阅 Blazor 文档。

>[!div class="step-by-step"]
>[上一页](app-startup.md)
>[下一页](pages-routing-layouts.md)
