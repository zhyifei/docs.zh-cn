---
title: 为 WCF 开发人员创建新的 ASP.NET Core gRPC 项目-gRPC
description: 了解如何使用 Visual Studio 或从命令行创建 gRPC 项目。
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967896"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>创建新的 ASP.NET Core gRPC 项目

.NET Core 附带了强大的 CLI 工具 `dotnet`，它使你能够从命令行创建和管理项目和解决方案。 该工具与 Visual Studio 紧密集成，因此，所有内容也可通过熟悉的 GUI 界面获得。 本章介绍了两种创建新 ASP.NET Core gRPC 项目的方法：首先使用 Visual Studio，然后使用 .NET Core CLI。

## <a name="create-the-project-using-visual-studio"></a>使用 Visual Studio 创建项目

> [!IMPORTANT]
> 若要开发任何 ASP.NET Core 3.0 应用，需要安装了**ASP.NET 和 web 开发**工作负荷的 Visual Studio 2019.3 或更高版本。

从*空白解决方案*模板创建名为**TraderSys**的空解决方案。 添加一个名为 `src`的解决方案文件夹，然后右键单击该文件夹，然后从上下文菜单中选择 "**添加** > "**新建项目**"。 在模板搜索框中输入 `grpc`，应会看到名为 `gRPC Service`的项目模板。

!["添加新项目" 对话框显示 gRPC 服务项目模板](media/create-project/new-grpc-project.png)

单击 "**下一步**" 以继续转到 "**配置项目**" 对话框并将项目命名为 "`TraderSys.Portfolios`"，并将 `src` 子目录添加到该**位置**。

!["配置项目" 对话框](media/create-project/configure-project.png)

单击 "**下一步**" 以继续转到 "**新建 gRPC 项目**" 对话框。

!["新建 gRPC 项目" 对话框](media/create-project/create-new-grpc-service.png)

目前，创建服务的选项是有限的。 此时将在本书中引入 Docker，因此请将该复选框保留为未选中状态，然后单击 "**创建**"。 将生成第一个 ASP.NET Core 3.0 gRPC 项目，并将其添加到解决方案中。 如果你不想了解如何使用 `dotnet CLI`，请跳到[清除示例代码](#clean-up-the-example-code)部分。

## <a name="create-the-project-using-the-net-core-cli"></a>使用 .NET Core CLI 创建项目

本部分介绍如何从命令行创建解决方案和项目。

创建解决方案，如下所示。 `-o` （或 `--output`）标志指定将在当前目录中创建的输出目录（如果不存在）。 该解决方案将提供与该目录相同的名称，即 `TraderSys.sln`。您可以使用 `-n` （或 `--name`）标志来提供不同的名称。

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 3.0 附带了 gRPC services 的 CLI 模板。 使用此模板创建新项目，并将其放入 `src` 子目录，就像 ASP.NET Core 项目的约定。 除非使用 `-n` 标志指定其他名称，否则将在目录（即 `TraderSys.Portfolios.csproj`）后面命名项目。

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

最后，使用 `dotnet sln` 命令将项目添加到解决方案。

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> 由于给定的目录只包含单个 `.csproj` 文件，因此，您可以只指定用于保存键入内容的目录。

你现在可以在 Visual Studio 2019、Visual Studio Code 或你喜欢的任何编辑器中打开此解决方案。

## <a name="clean-up-the-example-code"></a>清理示例代码

现在，你已使用 gRPC 模板创建了一个示例服务，该模板已在本书前面回顾过。 这在我们的股票交易环境中并不有用，因此我们将为第一个项目编辑一些内容。

### <a name="rename-and-edit-the-proto-file"></a>重命名和编辑协议文件

继续将 `Protos/greet.proto` 文件重命名为 `Protos/portfolios.proto` 并在编辑器中将其打开。 删除 `package` 行后面的所有内容，然后更改 `option csharp_namespace`、`package` 和 `service` 名称，并删除默认 `SayHello` 服务，使代码如下所示。

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> 默认情况下，此模板不会添加 `Protos` 命名空间部分，但是添加它可以更轻松地将 gRPC 生成的类和自己的类在代码中明确分隔。

如果重命名集成开发环境（IDE）中的 `greet.proto` 文件（如 Visual Studio），则会在 `.csproj` 文件中自动更新对此文件的引用。 但在某些其他编辑器中，如 Visual Studio Code，此引用不会自动更新，因此需要手动编辑项目文件。

在 gRPC 生成目标中，有一个 `Protobuf` item 元素，它允许您指定应编译哪些 `.proto` 文件以及需要哪种类型的代码生成（即，"服务器" 或 "客户端"）。

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>重命名 GreeterService 类

`GreeterService` 类位于 `Services` 文件夹中，并从 `Greeter.GreeterBase`继承。 将其重命名为 `PortfolioService`，并将基类更改为 `Portfolios.PortfoliosBase`。 删除 `override` 方法。

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

`Startup` 类的 `Configure` 方法中存在对 `GreeterService` 类的引用。 如果使用了重构来重命名类，则应自动更新此引用。 但是，如果没有，则需要手动编辑。

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

在下一部分中，我们将向此新服务添加功能。

>[!div class="step-by-step"]
>[上一页](migrate-wcf-to-grpc.md)
>[下一页](migrate-request-reply.md)
