---
title: 页面、路由和布局
description: 了解如何在 Blazor 中创建页面，使用客户端路由和管理页面布局。
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841233"
---
# <a name="pages-routing-and-layouts"></a>页面、路由和布局

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web 窗体应用由 *.aspx*文件中定义的页面组成。 每个页面的地址基于其在项目中的物理文件路径。 当浏览器向页面发出请求时，将在服务器上动态呈现该页的内容。 页的 HTML 标记及其服务器控件的呈现帐户。

在 Blazor 中，应用中的每个页面都是一个组件，通常在*razor*文件中定义，具有一个或多个指定路由。 路由大多数发生在客户端，而不涉及特定的服务器请求。 浏览器首先发出对应用程序根地址的请求。 然后，Blazor 应用中的根 `Router` 组件会处理截获导航请求，并将它们处理到正确的组件。

Blazor 还支持*深层链接*。 当浏览器向特定路由发出请求而不是应用的根时，将发生深层链接。 发送到服务器的深层链接请求路由到 Blazor 应用，后者随后将请求客户端路由到正确的组件。

ASP.NET Web 窗体中的简单页面可能包含以下标记：

*名称 .aspx*

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

Blazor 应用中的等效页面如下所示：

*名称 razor*

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a>创建页面

若要在 Blazor 中创建页面，请创建一个组件并添加 `@page` Razor 指令，以便为该组件指定路由。 `@page` 指令使用单个参数，该参数是要添加到该组件的路由模板。

```razor
@page "/counter"
```

路由模板参数是必需的。 与 ASP.NET Web 窗体不同，指向 Blazor 组件的路由*不*会从其文件位置推断出来（尽管这可能是将来添加的功能）。

路由模板语法是用于在 ASP.NET Web 窗体中进行路由的基本语法。 使用大括号在模板中指定路由参数。 Blazor 会将路由值绑定到具有相同名称的组件参数（不区分大小写）。

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

您还可以对路由参数的值指定约束。 例如，要将产品 ID 限制为 `int`：

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

有关 Blazor 支持的路由约束的完整列表，请参阅[路由约束](/aspnet/core/blazor/routing#route-constraints)。

## <a name="router-component"></a>路由器组件

Blazor 中的路由由 `Router` 组件处理。 `Router` 组件通常在应用程序的根组件（*app.config*）中使用。

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

`Router` 组件将发现指定 `AppAssembly` 中和指定 `AdditionalAssemblies`中的可路由组件。 当浏览器导航时，`Router` 会截获导航，并使用提取的 `RouteData` 呈现其 `Found` 参数的内容（如果路由与地址匹配），否则 `Router` 将呈现其 `NotFound` 参数。

`RouteView` 组件会处理 `RouteData` 指定的匹配组件（如果有）。 如果匹配的组件没有布局，则使用可选的指定 `DefaultLayout`。

`LayoutView` 组件在指定布局中呈现其子内容。 本章稍后将详细介绍布局。

## <a name="navigation"></a>导航

在 ASP.NET Web 窗体中，通过将重定向响应返回到浏览器来触发到其他页面的导航。 例如:

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

在 Blazor 中通常不能返回重定向响应。 Blazor 不使用请求-答复模式。 不过，您可以与 JavaScript 一起直接触发浏览器导航。

Blazor 提供了一个 `NavigationManager` 服务，可用于：

- 获取当前浏览器地址
- 获取基址
- 触发器导航
- 当地址更改时收到通知

若要导航到其他地址，请使用 `NavigateTo` 方法：

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

有关所有 `NavigationManager` 成员的说明，请参阅[URI 和导航状态帮助](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers)程序。

## <a name="base-urls"></a>基 Url

如果你的 Blazor 应用部署在基路径下，则需要使用 "路由到工作" 属性的 "`<base>`" 标记在页元数据中指定基 URL。 如果应用的 "主机" 页使用 Razor 进行服务器呈现，则可以使用 `~/` 语法来指定应用程序的基址。 如果主机页为静态 HTML，则需要显式指定基 URL。

```html
<base href="~/" />
```

## <a name="page-layout"></a>页面布局

ASP.NET Web 窗体中的页面布局由母版页处理。 母版页定义一个模板，其中包含一个或多个内容占位符，然后可以由各个页面提供。 母版页在 *.master*文件中定义，并以 `<%@ Master %>` 指令开头。 *.Master*文件的内容会被编码为 *.aspx*页面，但添加了 `<asp:ContentPlaceHolder>` 控件来标记页面可以提供内容的位置。

*站点主*

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

在 Blazor 中，可以使用布局组件来处理页面布局。 布局组件继承自 `LayoutComponentBase`，后者定义类型 `RenderFragment`的单个 `Body` 属性，该属性可用于呈现页面的内容。

*MainLayout*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

呈现包含布局的页面时，页面将在指定布局的内容中呈现在布局呈现其 `Body` 属性的位置。

若要将布局应用于页面，请使用 `@layout` 指令：

```razor
@layout MainLayout
```

你可以使用 *_Imports razor*文件指定文件夹和子文件夹中的所有组件的布局。 你还可以使用[路由器组件](#router-component)指定所有页面的默认布局。

母版页可定义多个内容占位符，但 Blazor 中的布局只有单个 `Body` 属性。 在未来的版本中，Blazor 布局组件的这一限制将会得到解决。

ASP.NET Web 窗体中的母版页可以嵌套。 也就是说，母版页也可能使用母版页。 Blazor 中的布局组件也可能嵌套。 您可以将布局组件应用于布局组件。 内部布局的内容将在外部布局中呈现。

*ChildLayout*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*索引 razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

页面呈现的输出将为：

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

Blazor 中的布局通常不会定义页面的根 HTML 元素（`<html>`、`<body>`、`<head>`，等等）。 根 HTML 元素是在 Blazor 应用程序的主机页中定义的，该页用于呈现应用程序的初始 HTML 内容（请参阅[启动 Blazor](project-structure.md#bootstrap-blazor)）。 宿主页可以为应用程序提供多个包含周围标记的根组件。

Blazor 中的组件（包括页面）不能 `<script>` 标记中呈现。 存在此呈现限制的原因是 `<script>` 标记只加载一次，因此无法更改。 如果尝试使用 Razor 语法动态呈现标记，可能会发生意外行为。 相反，应将所有 `<script>` 标记添加到应用的 "主机" 页。

>[!div class="step-by-step"]
>[上一页](components.md)
>[下一页](state-management.md)
