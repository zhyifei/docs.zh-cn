---
title: 为 WCF 开发人员创建新的 ASP.NET Core gRPC 项目-gRPC
description: 了解如何使用 Visual Studio 或命令行创建 gRPC 项目。
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711439"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="90130-103">创建新的 ASP.NET Core gRPC 项目</span><span class="sxs-lookup"><span data-stu-id="90130-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="90130-104">该 .NET Core SDK 附带了功能强大的 CLI 工具，`dotnet`，使你能够从命令行创建和管理项目和解决方案。</span><span class="sxs-lookup"><span data-stu-id="90130-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="90130-105">SDK 与 Visual Studio 紧密集成，因此，所有内容也可通过熟悉的图形用户界面获得。</span><span class="sxs-lookup"><span data-stu-id="90130-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="90130-106">本章介绍了两种创建新 ASP.NET Core gRPC 项目的方法。</span><span class="sxs-lookup"><span data-stu-id="90130-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="90130-107">使用 Visual Studio 创建项目</span><span class="sxs-lookup"><span data-stu-id="90130-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90130-108">若要开发任何 ASP.NET Core 3.0 应用，需要安装**ASP.NET 和 web 开发**工作负荷的 Visual Studio 2019 16.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="90130-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="90130-109">从*空白解决方案*模板创建名为**TraderSys**的空解决方案。</span><span class="sxs-lookup"><span data-stu-id="90130-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="90130-110">添加一个名为 `src`的解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="90130-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="90130-111">然后，右键单击该文件夹，然后选择 "**添加**" > "**新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="90130-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="90130-112">在模板搜索框中输入 `grpc`，应会看到名为 `gRPC Service`的项目模板。</span><span class="sxs-lookup"><span data-stu-id="90130-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

!["添加新项目" 对话框的屏幕截图](media/create-project/new-grpc-project.png)

<span data-ttu-id="90130-114">选择 "**下一步**" 以继续进入 "**配置新项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="90130-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="90130-115">将项目命名为 `TraderSys.Portfolios`，并将 `src` 子目录添加到该**位置**。</span><span class="sxs-lookup"><span data-stu-id="90130-115">Name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

!["配置新项目" 对话框的屏幕截图](media/create-project/configure-project.png)

<span data-ttu-id="90130-117">选择 "**下一步**" 以继续转到 "**创建新的 gRPC 服务**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="90130-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

!["创建新的 gRPC 服务" 对话框的屏幕截图](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="90130-119">目前，为服务创建提供了有限的选项。</span><span class="sxs-lookup"><span data-stu-id="90130-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="90130-120">Docker 将在以后推出，因此现在，请将该选项保持未选中状态。</span><span class="sxs-lookup"><span data-stu-id="90130-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="90130-121">只需选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="90130-121">Just select **Create**.</span></span> <span data-ttu-id="90130-122">将生成第一个 ASP.NET Core 3.0 gRPC 项目，并将其添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="90130-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="90130-123">如果你不想了解如何使用 `dotnet CLI`，请跳到[清除示例代码](#clean-up-the-example-code)部分。</span><span class="sxs-lookup"><span data-stu-id="90130-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="90130-124">使用 .NET Core CLI 创建项目</span><span class="sxs-lookup"><span data-stu-id="90130-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="90130-125">本部分介绍如何从命令行创建解决方案和项目。</span><span class="sxs-lookup"><span data-stu-id="90130-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="90130-126">创建解决方案，如以下命令所示。</span><span class="sxs-lookup"><span data-stu-id="90130-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="90130-127">`-o` （或 `--output`）标志指定将在当前目录中创建的输出目录（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="90130-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="90130-128">该解决方案具有与目录相同的名称： `TraderSys.sln`。</span><span class="sxs-lookup"><span data-stu-id="90130-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="90130-129">可以通过使用 `-n` （或 `--name`）标志来提供不同的名称。</span><span class="sxs-lookup"><span data-stu-id="90130-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="90130-130">ASP.NET Core 3.0 附带了 gRPC services 的 CLI 模板。</span><span class="sxs-lookup"><span data-stu-id="90130-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="90130-131">使用此模板创建新项目，并将其放入 `src` 子目录，与 ASP.NET Core 项目的传统一样。</span><span class="sxs-lookup"><span data-stu-id="90130-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="90130-132">该项目以目录（`TraderSys.Portfolios.csproj`）命名，除非使用 `-n` 标志指定其他名称。</span><span class="sxs-lookup"><span data-stu-id="90130-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="90130-133">最后，使用 `dotnet sln` 命令将项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="90130-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="90130-134">由于特定目录只包含单个 `.csproj` 文件，因此只需指定目录即可保存键入内容。</span><span class="sxs-lookup"><span data-stu-id="90130-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="90130-135">你现在可以在 Visual Studio 2019、Visual Studio Code 或你喜欢的任何编辑器中打开此解决方案。</span><span class="sxs-lookup"><span data-stu-id="90130-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="90130-136">清理示例代码</span><span class="sxs-lookup"><span data-stu-id="90130-136">Clean up the example code</span></span>

<span data-ttu-id="90130-137">现在，你已使用 gRPC 模板创建了一个示例服务，该模板已在本书前面回顾过。</span><span class="sxs-lookup"><span data-stu-id="90130-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="90130-138">这在我们的股票交易环境中并不有用，因此我们将为第一个项目编辑一些内容。</span><span class="sxs-lookup"><span data-stu-id="90130-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="90130-139">重命名和编辑协议文件</span><span class="sxs-lookup"><span data-stu-id="90130-139">Rename and edit the proto file</span></span>

<span data-ttu-id="90130-140">继续下一 `Protos/greet.proto` 文件，将其重命名为 `Protos/portfolios.proto`，然后在编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="90130-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="90130-141">删除 `package` 行后的所有内容。</span><span class="sxs-lookup"><span data-stu-id="90130-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="90130-142">然后，更改 `option csharp_namespace`、`package` 和 `service` 名称，并删除默认的 `SayHello` 服务。</span><span class="sxs-lookup"><span data-stu-id="90130-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="90130-143">该代码现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="90130-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="90130-144">默认情况下，此模板不会添加 `Protos` 命名空间部分，但是添加它可以更轻松地将 gRPC 生成的类和自己的类在代码中明确分隔。</span><span class="sxs-lookup"><span data-stu-id="90130-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="90130-145">如果重命名集成开发环境（IDE）中的 `greet.proto` 文件（如 Visual Studio），则会在 `.csproj` 文件中自动更新对此文件的引用。</span><span class="sxs-lookup"><span data-stu-id="90130-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="90130-146">但在某些其他编辑器中，如 Visual Studio Code，此引用不会自动更新，因此需要手动编辑项目文件。</span><span class="sxs-lookup"><span data-stu-id="90130-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="90130-147">在 gRPC 生成目标中，有一个 `Protobuf` item 元素，它允许您指定应编译哪些 `.proto` 文件以及需要哪种类型的代码生成（即，"服务器" 或 "客户端"）。</span><span class="sxs-lookup"><span data-stu-id="90130-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="90130-148">重命名 `GreeterService` 类</span><span class="sxs-lookup"><span data-stu-id="90130-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="90130-149">`GreeterService` 类位于 `Services` 文件夹中，并从 `Greeter.GreeterBase`继承。</span><span class="sxs-lookup"><span data-stu-id="90130-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="90130-150">将其重命名为 `PortfolioService`，并将基类更改为 `Portfolios.PortfoliosBase`。</span><span class="sxs-lookup"><span data-stu-id="90130-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="90130-151">删除 `override` 方法。</span><span class="sxs-lookup"><span data-stu-id="90130-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="90130-152">`Startup` 类的 `Configure` 方法中存在对 `GreeterService` 类的引用。</span><span class="sxs-lookup"><span data-stu-id="90130-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="90130-153">如果使用了重构来重命名类，则应自动更新此引用。</span><span class="sxs-lookup"><span data-stu-id="90130-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="90130-154">但是，如果没有，则需要手动编辑。</span><span class="sxs-lookup"><span data-stu-id="90130-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="90130-155">在下一部分中，我们将向此新服务添加功能。</span><span class="sxs-lookup"><span data-stu-id="90130-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="90130-156">[上一页](migrate-wcf-to-grpc.md)
>[下一页](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="90130-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
