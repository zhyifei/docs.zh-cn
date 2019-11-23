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
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="870d4-103">创建新的 ASP.NET Core gRPC 项目</span><span class="sxs-lookup"><span data-stu-id="870d4-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="870d4-104">.NET Core 附带了强大的 CLI 工具 `dotnet`，它使你能够从命令行创建和管理项目和解决方案。</span><span class="sxs-lookup"><span data-stu-id="870d4-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="870d4-105">该工具与 Visual Studio 紧密集成，因此，所有内容也可通过熟悉的 GUI 界面获得。</span><span class="sxs-lookup"><span data-stu-id="870d4-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="870d4-106">本章介绍了两种创建新 ASP.NET Core gRPC 项目的方法：首先使用 Visual Studio，然后使用 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="870d4-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="870d4-107">使用 Visual Studio 创建项目</span><span class="sxs-lookup"><span data-stu-id="870d4-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="870d4-108">若要开发任何 ASP.NET Core 3.0 应用，需要安装了**ASP.NET 和 web 开发**工作负荷的 Visual Studio 2019.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="870d4-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="870d4-109">从*空白解决方案*模板创建名为**TraderSys**的空解决方案。</span><span class="sxs-lookup"><span data-stu-id="870d4-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="870d4-110">添加一个名为 `src`的解决方案文件夹，然后右键单击该文件夹，然后从上下文菜单中选择 "**添加** > "**新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="870d4-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="870d4-111">在模板搜索框中输入 `grpc`，应会看到名为 `gRPC Service`的项目模板。</span><span class="sxs-lookup"><span data-stu-id="870d4-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

!["添加新项目" 对话框显示 gRPC 服务项目模板](media/create-project/new-grpc-project.png)

<span data-ttu-id="870d4-113">单击 "**下一步**" 以继续转到 "**配置项目**" 对话框并将项目命名为 "`TraderSys.Portfolios`"，并将 `src` 子目录添加到该**位置**。</span><span class="sxs-lookup"><span data-stu-id="870d4-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

!["配置项目" 对话框](media/create-project/configure-project.png)

<span data-ttu-id="870d4-115">单击 "**下一步**" 以继续转到 "**新建 gRPC 项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="870d4-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

!["新建 gRPC 项目" 对话框](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="870d4-117">目前，创建服务的选项是有限的。</span><span class="sxs-lookup"><span data-stu-id="870d4-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="870d4-118">此时将在本书中引入 Docker，因此请将该复选框保留为未选中状态，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="870d4-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="870d4-119">将生成第一个 ASP.NET Core 3.0 gRPC 项目，并将其添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="870d4-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="870d4-120">如果你不想了解如何使用 `dotnet CLI`，请跳到[清除示例代码](#clean-up-the-example-code)部分。</span><span class="sxs-lookup"><span data-stu-id="870d4-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="870d4-121">使用 .NET Core CLI 创建项目</span><span class="sxs-lookup"><span data-stu-id="870d4-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="870d4-122">本部分介绍如何从命令行创建解决方案和项目。</span><span class="sxs-lookup"><span data-stu-id="870d4-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="870d4-123">创建解决方案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="870d4-123">Create the solution as shown below.</span></span> <span data-ttu-id="870d4-124">`-o` （或 `--output`）标志指定将在当前目录中创建的输出目录（如果不存在）。</span><span class="sxs-lookup"><span data-stu-id="870d4-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="870d4-125">该解决方案将提供与该目录相同的名称，即 `TraderSys.sln`。您可以使用 `-n` （或 `--name`）标志来提供不同的名称。</span><span class="sxs-lookup"><span data-stu-id="870d4-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="870d4-126">ASP.NET Core 3.0 附带了 gRPC services 的 CLI 模板。</span><span class="sxs-lookup"><span data-stu-id="870d4-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="870d4-127">使用此模板创建新项目，并将其放入 `src` 子目录，就像 ASP.NET Core 项目的约定。</span><span class="sxs-lookup"><span data-stu-id="870d4-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="870d4-128">除非使用 `-n` 标志指定其他名称，否则将在目录（即 `TraderSys.Portfolios.csproj`）后面命名项目。</span><span class="sxs-lookup"><span data-stu-id="870d4-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="870d4-129">最后，使用 `dotnet sln` 命令将项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="870d4-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="870d4-130">由于给定的目录只包含单个 `.csproj` 文件，因此，您可以只指定用于保存键入内容的目录。</span><span class="sxs-lookup"><span data-stu-id="870d4-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="870d4-131">你现在可以在 Visual Studio 2019、Visual Studio Code 或你喜欢的任何编辑器中打开此解决方案。</span><span class="sxs-lookup"><span data-stu-id="870d4-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="870d4-132">清理示例代码</span><span class="sxs-lookup"><span data-stu-id="870d4-132">Clean up the example code</span></span>

<span data-ttu-id="870d4-133">现在，你已使用 gRPC 模板创建了一个示例服务，该模板已在本书前面回顾过。</span><span class="sxs-lookup"><span data-stu-id="870d4-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="870d4-134">这在我们的股票交易环境中并不有用，因此我们将为第一个项目编辑一些内容。</span><span class="sxs-lookup"><span data-stu-id="870d4-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="870d4-135">重命名和编辑协议文件</span><span class="sxs-lookup"><span data-stu-id="870d4-135">Rename and edit the proto file</span></span>

<span data-ttu-id="870d4-136">继续将 `Protos/greet.proto` 文件重命名为 `Protos/portfolios.proto` 并在编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="870d4-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="870d4-137">删除 `package` 行后面的所有内容，然后更改 `option csharp_namespace`、`package` 和 `service` 名称，并删除默认 `SayHello` 服务，使代码如下所示。</span><span class="sxs-lookup"><span data-stu-id="870d4-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="870d4-138">默认情况下，此模板不会添加 `Protos` 命名空间部分，但是添加它可以更轻松地将 gRPC 生成的类和自己的类在代码中明确分隔。</span><span class="sxs-lookup"><span data-stu-id="870d4-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="870d4-139">如果重命名集成开发环境（IDE）中的 `greet.proto` 文件（如 Visual Studio），则会在 `.csproj` 文件中自动更新对此文件的引用。</span><span class="sxs-lookup"><span data-stu-id="870d4-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="870d4-140">但在某些其他编辑器中，如 Visual Studio Code，此引用不会自动更新，因此需要手动编辑项目文件。</span><span class="sxs-lookup"><span data-stu-id="870d4-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="870d4-141">在 gRPC 生成目标中，有一个 `Protobuf` item 元素，它允许您指定应编译哪些 `.proto` 文件以及需要哪种类型的代码生成（即，"服务器" 或 "客户端"）。</span><span class="sxs-lookup"><span data-stu-id="870d4-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="870d4-142">重命名 GreeterService 类</span><span class="sxs-lookup"><span data-stu-id="870d4-142">Rename the GreeterService class</span></span>

<span data-ttu-id="870d4-143">`GreeterService` 类位于 `Services` 文件夹中，并从 `Greeter.GreeterBase`继承。</span><span class="sxs-lookup"><span data-stu-id="870d4-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="870d4-144">将其重命名为 `PortfolioService`，并将基类更改为 `Portfolios.PortfoliosBase`。</span><span class="sxs-lookup"><span data-stu-id="870d4-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="870d4-145">删除 `override` 方法。</span><span class="sxs-lookup"><span data-stu-id="870d4-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="870d4-146">`Startup` 类的 `Configure` 方法中存在对 `GreeterService` 类的引用。</span><span class="sxs-lookup"><span data-stu-id="870d4-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="870d4-147">如果使用了重构来重命名类，则应自动更新此引用。</span><span class="sxs-lookup"><span data-stu-id="870d4-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="870d4-148">但是，如果没有，则需要手动编辑。</span><span class="sxs-lookup"><span data-stu-id="870d4-148">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="870d4-149">在下一部分中，我们将向此新服务添加功能。</span><span class="sxs-lookup"><span data-stu-id="870d4-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="870d4-150">[上一页](migrate-wcf-to-grpc.md)
>[下一页](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="870d4-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
