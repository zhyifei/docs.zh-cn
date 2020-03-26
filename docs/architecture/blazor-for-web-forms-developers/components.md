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
# <a name="build-reusable-ui-components-with-blazor"></a>使用 Blazor 构建可重用的 UI 组件

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web 窗体中一个美妙的事情是，它如何将可重用的用户界面 （UI） 代码封装到可重用的 UI 控件中。 可以使用 *.ascx*文件在标记中定义自定义用户控件。 您还可以在代码中构建详细的服务器控件，并支持完全设计人员。

Blazor 还支持通过*组件*进行 UI 封装。 组件：

- 是 UI 的自包含块。
- 维护自己的状态和呈现逻辑。
- 可以定义 UI 事件处理程序、绑定到输入数据以及管理其自己的生命周期。
- 通常在使用 Razor 语法的 *.razor*文件中定义。

## <a name="an-introduction-to-razor"></a>剃刀简介

Razor 是基于 HTML 和 C# 的轻量级标记模板化语言。 使用 Razor，您可以在标记和 C# 代码之间无缝过渡，以定义组件呈现逻辑。 编译 *.razor*文件时，呈现逻辑以结构化方式在 .NET 类中捕获。 已编译类的名称取自 *.razor*文件名。 命名空间取自项目和文件夹路径的默认命名空间，或者您可以使用`@namespace`指令显式指定命名空间（下面有关 Razor 指令的更多）。

组件的呈现逻辑使用使用使用 C# 添加的动态逻辑使用普通 HTML 标记进行创作。 该`@`字符用于转换为 C#。 剃刀通常很聪明，可以找出您何时切换回 HTML。 例如，以下组件呈现当前`<p>`时间的标记：

```razor
<p>@DateTime.Now</p>
```

要显式指定 C# 表达式的开始和结束，请使用括号：

```razor
<p>@(DateTime.Now)</p>
```

Razor 还便于在渲染逻辑中使用 C# 控制流。 例如，您可以有条件地呈现一些 HTML，如下所示：

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

或者，您可以使用正常的 C#`foreach`循环生成项列表，如下所示：

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Razor 指令（如ASP.NET Web 窗体中的指令）控制 Razor 组件的编译方式的许多方面。 示例包括组件：

- 命名空间
- 基类
- 实现的接口
- 泛型参数
- 导入的命名空间
- 路由

Razor 指令以`@`字符开头，通常在文件开头的新行开始时使用。 例如，`@namespace`指令定义组件的命名空间：

```razor
@namespace MyComponentNamespace
```

下表总结了 Blazor 中使用的各种 Razor 指令及其ASP.NET Web 窗体等效项（如果存在）。

|指令    |说明|示例|与 Web 窗体等效|
|-------------|-----------|-------|--------------------|
|`@attribute` |向组件添加类级属性|`@attribute [Authorize]`|无|
|`@code`      |将类成员添加到组件|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|实现指定的接口|`@implements IDisposable`|使用代码隐藏|
|`@inherits`  |从指定的基类继承|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |将服务注入组件|`@inject IJSRuntime JS`|无|
|`@layout`    |指定组件的布局组件|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |设置组件的命名空间|`@namespace MyNamespace`|无|
|`@page`      |指定组件的路由|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |为组件指定泛型类型参数|`@typeparam TItem`|使用代码隐藏|
|`@using`     |指定要引入作用域的命名空间|`@using MyComponentNamespace`|在*Web.config 中*添加命名空间|

Razor 组件还广泛使用元素上的*指令属性*来控制组件的编译方式的各个方面（事件处理、数据绑定、组件&元素引用等）。 指令属性都遵循一个通用通用语法，其中括号中的值是可选的：

```razor
@directive(-suffix(:name))(="value")
```

下表总结了 Blazor 中使用的 Razor 指令的各种属性。

|特性    |说明|示例|
|-------------|-----------|-------|
|`@attributes`|渲染属性字典|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |创建双向数据绑定    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |为指定事件添加事件处理程序|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |指定扩散算法用于保留集合中元素的键|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |捕获对组件或 HTML 元素的引用|`<MyDialog @ref="myDialog" />`|

Blazor （、、、`@onclick``@bind``@ref`等） 使用的各种指令属性在以下各章和后面的章节中介绍。

*.aspx*和 *.ascx*文件中使用的许多语法在 Razor 中具有并行语法。 下面是ASP.NET Web 窗体和 Razor 的语法的简单比较。

|Feature                      |Web 窗体           |语法               |Razor         |语法 |
|-----------------------------|--------------------|---------------------|--------------|-------|
|指令                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|代码块                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|表达式<br>（HTML 编码）|`<%: %>`            |`<%:DateTime.Now %>` |隐 式：`@`<br>明确：`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|注释                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|数据绑定                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

要将成员添加到 Razor 组件类，请使用`@code`该指令。 此技术类似于在ASP.NET Web`<script runat="server">...</script>`窗体用户控件或页面中使用块。

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

由于 Razor 基于 C#，因此必须从 C# 项目中编译它 （*.csproj*）。 无法从可视化基础项目 *（.vbproj*） 编译 *.razor*文件。 您仍然可以从 Blazor 项目中引用可视化基本项目。 事实正好相反。

有关完整的 Razor 语法引用，请参阅[ASP.NET 酷睿的 Razor 语法引用](/aspnet/core/mvc/views/razor)。

## <a name="use-components"></a>使用组件

除了普通 HTML 之外，组件还可以使用其他组件作为其呈现逻辑的一部分。 在 Razor 中使用组件的语法类似于在 ASP.NET Web 窗体应用中使用用户控件。 使用与组件的类型名称匹配的元素标记指定组件。 例如，您可以添加如下所示的`Counter`组件：

```razor
<Counter />
```

与ASP.NET Web 窗体不同，Blazor 中的组件：

- 不要使用元素前缀（例如， `asp:`。
- 不需要在页面或*Web*上注册。

像想象一下 Razor 组件，就像您那样，可以.NET 类型，因为这正是它们。 如果引用了包含组件的程序集，则该组件可供使用。 要将组件的命名空间引入范围，请应用该`@using`指令：

```razor
@using MyComponentLib

<Counter />
```

如默认 Blazor 项目中所示，通常将指令放入`@using` *_Imports.razor*文件中，以便它们导入到同一目录中的所有 *.razor*文件中以及子目录中。

如果组件的命名空间不在作用域中，则可以使用组件的完整类型名称指定组件，如在 C# 中：

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>组件参数

在ASP.NET Web 窗体中，可以使用公共属性将参数和数据流向控件。 这些属性可以使用属性在标记中设置，也可以直接在代码中设置。 Blazor 组件的工作方式类似，尽管组件属性还必须使用要被视为组件参数`[Parameter]`的属性进行标记。

以下`Counter`组件定义一个组件参数，该`IncrementAmount`参数可用于指定每次单击按钮时`Counter`应递增的金额。

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

要在 Blazor 中指定组件参数，请使用ASP.NET Web 窗体中的属性：

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>事件处理程序

ASP.NET Web 窗体和 Blazor 都提供了一个基于事件的编程模型来处理 UI 事件。 此类事件的示例包括按钮单击和文本输入。 在ASP.NET Web 窗体中，您可以使用 HTML 服务器控件来处理 DOM 公开的 UI 事件，也可以处理 Web 服务器控件公开的事件。 事件通过回后表单请求在服务器上显示。 请考虑以下 Web 窗体按钮单击示例：

*计数器.ascx*

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

在 Blazor 中，可以直接使用窗体`@on{event}`的指令属性注册 DOM UI 事件的处理程序。 占`{event}`位符表示事件的名称。 例如，您可以侦听按钮单击，如下所示：

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

事件处理程序可以接受可选的特定于事件的参数来提供有关该事件的详细信息。 例如，鼠标事件可以采用`MouseEventArgs`参数，但不是必需的。

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

可以使用 lambda 表达式，而不是引用事件处理程序的方法组。 lambda 表达式允许您关闭其他范围内值。

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

事件处理程序可以同步或异步执行。 例如，以下`OnClick`事件处理程序异步执行：

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

处理事件后，组件将呈现为考虑任何组件状态更改。 使用异步事件处理程序，在处理程序执行完成后立即呈现组件。 异步`Task`完成后 *，将再次*呈现组件。 此异步执行模式提供了在异步`Task`仍在进行时呈现一些适当 UI 的机会。

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

组件还可以通过定义类型的`EventCallback<TValue>`组件参数来定义自己的事件。 事件回调支持 DOM UI 事件处理程序的所有变体：可选参数、同步或异步、方法组或 lambda 表达式。

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>数据绑定

Blazor 提供了一种将数据从 UI 组件绑定到组件状态的简单机制。 此方法不同于 ASP.NET Web 窗体中用于将数据从数据源绑定到 UI 控件的功能。 我们将在["处理数据"](data.md)部分中介绍处理来自不同数据源的数据。

要创建从 UI 组件到组件状态的双向数据绑定，请使用`@bind`指令属性。 在下面的示例中，复选框的值绑定到该`isChecked`字段。

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

呈现组件时，复选框的值将设置为`isChecked`字段的值。 当用户切换复选框时，将`onchange`触发事件并将`isChecked`该字段设置为新值。 在这种情况下`@bind`，语法等效于以下标记：

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

要更改用于绑定的事件，请使用 属性`@bind:event`。

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

组件还可以支持绑定到其参数的数据。 要绑定数据，请定义与可绑定参数同名的事件回调参数。 "已更改"后缀将添加到名称中。

*密码盒.剃须刀*

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

要将数据绑定链接到基础 UI 元素，请使用 该值设置值并直接在 UI 元素上处理事件`@bind`，而不是使用 属性。

要绑定到组件参数，请使用属性`@bind-{Parameter}`指定要绑定到的参数。

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>状态更改

如果组件的状态在正常 UI 事件或事件回调之外已更改，则组件必须手动发出信号，表示需要再次呈现该组件。 要发出组件状态已更改的信号，请调用组件上`StateHasChanged`的方法。

在下面的示例中，组件显示`AppState`来自服务的消息，该消息可以由应用的其他部分更新。 组件将其`StateHasChanged`方法注册到事件中`AppState.OnChange`，以便每当消息更新时都会呈现该组件。

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

ASP.NET Web 窗体框架为模块、页面和控制定义了明确的生命周期方法。 例如，以下控件为`Init`和`Load`和`UnLoad`生命周期事件实现事件处理程序：

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor 组件也有定义明确的生命周期。 组件的生命周期可用于初始化组件状态并实现高级组件行为。

Blazor 的所有组件生命周期方法都具有同步和异步版本。 组件呈现是同步的。 不能作为组件呈现的一部分运行异步逻辑。 所有异步逻辑都必须作为生命周期方法的一`async`部分执行。

### <a name="oninitialized"></a>初始化时

和`OnInitialized``OnInitializedAsync`方法用于初始化组件。 组件通常在首次呈现后初始化。 初始化组件后，在最终释放组件之前，可能会多次呈现该组件。 该方法`OnInitialized`类似于ASP.NET Web`Page_Load`窗体页和控件中的事件。

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>在参数设置上

当`OnParametersSet`组件`OnParametersSetAsync`从其父组件接收参数并将值分配给属性时，将调用 和 方法。 这些方法在组件初始化后以及*每次呈现组件时*执行。

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>在渲染后打开

和`OnAfterRender``OnAfterRenderAsync`方法在组件完成呈现后调用。 此时将填充元素和组件引用（下面将介绍这些概念的更多内容）。 此时启用了与浏览器的交互性。 与 DOM 和 JavaScript 执行的交互可以安全地发生。

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

`OnAfterRender`并在`OnAfterRenderAsync`*服务器上预渲染时不调用*。

参数`firstRender`是`true`首次呈现组件;否则，其值为`false`。

### <a name="idisposable"></a>IDisposable

Blazor 组件可以`IDisposable`实现在从 UI 中删除组件时释放资源。 Razor 组件可以使用`IDispose``@implements`该指令实现：

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

在ASP.NET Web 窗体中，通常通过引用控件实例的 ID 来直接在代码中操作控件实例。 在 Blazor 中，还可以捕获和操作对组件的引用，尽管它不太常见。

要在 Blazor 中捕获组件引用，`@ref`请使用指令属性。 属性的值应与与引用的组件类型相同的可设置字段的名称匹配。

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

呈现父组件时，该字段将填充子组件实例。 然后，您可以调用组件实例上的方法或以其他方式操作组件实例。

不建议直接使用组件引用操作组件状态。 这样做可防止组件在正确的时间自动呈现。

## <a name="capture-element-references"></a>捕获元素引用

Blazor 组件可以捕获对元素的引用。 与ASP.NET Web 窗体中的 HTML 服务器控件不同，不能直接使用 Blazor 中的元素引用操作 DOM。 Blazor 使用 DOM 扩散算法为您处理大多数 DOM 交互。 Blazor 中捕获的元素引用不透明。 但是，它们用于传递 JavaScript 互操作调用中的特定元素引用。 有关 JavaScript 互通的详细信息，请参阅[ASP.NET核心 Blazor JavaScript 互通](/aspnet/core/blazor/javascript-interop)。

## <a name="templated-components"></a>模板化组件

在ASP.NET Web 窗体中，您可以创建*模板化控件*。 模板化控件使开发人员能够指定用于呈现容器控件的 HTML 的一部分。 构建模板化服务器控件的机制非常复杂，但它们支持以用户自定义的方式呈现数据的强大方案。 模板化控件的示例包括`Repeater`和`DataList`。

Blazor 组件也可以通过定义类型`RenderFragment`或`RenderFragment<T>`的组件参数进行模板化。 表示`RenderFragment`Razor 标记块，然后由组件呈现。 A`RenderFragment<T>`是 Razor 标记的块，它采用在渲染渲染片段时可以指定的参数。

### <a name="child-content"></a>子内容

Blazor 组件可以捕获其子内容作为`RenderFragment`，并将该内容呈现为组件呈现的一部分。 要捕获子内容，请定义类型的`RenderFragment`组件参数并将其`ChildContent`命名为 。

*子内容组件.razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

然后，父组件可以使用正常的 Razor 语法提供子内容。

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>模板参数

模板化的 Blazor 组件还可以定义类型`RenderFragment`或`RenderFragment<T>`的多个组件参数。 调用 时可以`RenderFragment<T>`指定 的 参数。 要为组件指定泛型类型参数，请使用`@typeparam`Razor 指令。

*简单列表查看.剃须刀*

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

使用模板化组件时，可以使用与参数名称匹配的子元素指定模板参数。 `RenderFragment<T>`作为元素传递的类型组件参数具有名为 的`context`隐式参数。 您可以使用子元素上`Context`的属性更改此实现参数的名称。 可以使用与类型参数名称匹配的属性指定任何泛型类型参数。 如果可能，将推断类型参数：

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

Blazor 组件通常创作在单个 *.razor*文件中。 但是，也可以使用代码背后的文件分隔代码和标记。 要使用组件文件，添加与组件文件的文件名匹配但添加了 *.cs*扩展名 *（Counter.razor.cs*） 的 C# 文件。 使用 C# 文件为组件定义基类。 您可以命名基类的任何内容，但通常将类命名为与组件类相同，但添加了`Base`扩展项 （）。`CounterBase` 基于组件的类也必须派生自`ComponentBase`。 然后，在 Razor 组件文件中，添加`@inherits`指令以指定组件的基类 （。`@inherits CounterBase`

*计数器.剃须刀*

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

基类中组件成员的可见性必须`protected`为或`public`对组件类可见。

## <a name="additional-resources"></a>其他资源

前面不是对Blazor组件所有方面的详尽处理。 有关如何[创建和使用核心剃须刀组件ASP.NET](/aspnet/core/blazor/components)的详细信息，请参阅 Blazor 文档。

>[!div class="step-by-step"]
>[上一个](app-startup.md)
>[下一个](pages-routing-layouts.md)
