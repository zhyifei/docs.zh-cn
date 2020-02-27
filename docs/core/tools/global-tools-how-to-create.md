---
title: 教程：创建 .NET Core 工具
description: 了解如何创建 .NET Core 工具。 工具是一个通过使用 .NET Core CLI 安装的控制台应用程序。
ms.date: 02/12/2020
ms.openlocfilehash: 558bf9e37efc8de68a61f1384fababe342ab7d66
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543399"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a><span data-ttu-id="f1476-104">教程：使用 .NET Core CLI 创建 .NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="f1476-104">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>

<span data-ttu-id="f1476-105"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="f1476-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="f1476-106">本教程介绍如何创建和打包 .NET Core 工具。</span><span class="sxs-lookup"><span data-stu-id="f1476-106">This tutorial teaches you how to create and package a .NET Core tool.</span></span> <span data-ttu-id="f1476-107">使用 .NET Core CLI，可以创建一个控制台应用程序作为工具，便于其他人安装并运行。</span><span class="sxs-lookup"><span data-stu-id="f1476-107">The .NET Core CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="f1476-108">.NET Core 工具是从 .NET Core CLI 安装的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="f1476-108">.NET Core tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="f1476-109">有关工具的详细信息，请参阅 [.NET Core 工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f1476-109">For more information about tools, see [.NET Core tools overview](global-tools.md).</span></span>

<span data-ttu-id="f1476-110">将创建的工具是一个控制台应用程序，它将消息作为输入，并显示消息以及用于创建机器人图像的文本行。</span><span class="sxs-lookup"><span data-stu-id="f1476-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="f1476-111">这是一系列教程（包含三个教程）中的第一个。</span><span class="sxs-lookup"><span data-stu-id="f1476-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="f1476-112">在本教程中，将创建并打包工具。</span><span class="sxs-lookup"><span data-stu-id="f1476-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="f1476-113">在接下来的两个教程中，[使用该工具作为全局工具](global-tools-how-to-use.md)并[使用该工具作为本地工具](local-tools-how-to-use.md)。</span><span class="sxs-lookup"><span data-stu-id="f1476-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1476-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="f1476-114">Prerequisites</span></span>

- <span data-ttu-id="f1476-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f1476-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="f1476-116">本教程和下面的[全局工具教程](global-tools-how-to-use.md)适用于 .NET Core SDK 2.1 及更高版本，因为全局工具从该版本开始可用。</span><span class="sxs-lookup"><span data-stu-id="f1476-116">This tutorial and the following [tutorial for global tools](global-tools-how-to-use.md) apply to .NET Core SDK 2.1 and later versions because global tools are available starting in that version.</span></span> <span data-ttu-id="f1476-117">但本教程假定你已安装 3.1 或更高版本，因此你可以选择继续学习[本地工具教程](local-tools-how-to-use.md)。</span><span class="sxs-lookup"><span data-stu-id="f1476-117">But this tutorial assumes you have installed 3.1 or later so that you have the option of continuing on to the [local tools tutorial](local-tools-how-to-use.md).</span></span> <span data-ttu-id="f1476-118">本地工具从 .NET Core SDK 3.0 开始可用。</span><span class="sxs-lookup"><span data-stu-id="f1476-118">Local tools are available starting in .NET Core SDK 3.0.</span></span> <span data-ttu-id="f1476-119">无论你是将工具用作全局工具还是用作本地工具，创建工具的过程都是相同的。</span><span class="sxs-lookup"><span data-stu-id="f1476-119">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>
  
- <span data-ttu-id="f1476-120">按需选择的文本编辑器或代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="f1476-120">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="f1476-121">创建项目</span><span class="sxs-lookup"><span data-stu-id="f1476-121">Create a project</span></span>

1. <span data-ttu-id="f1476-122">打开命令提示符，创建一个名为“repository”  的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1476-122">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="f1476-123">导航到“repository”  文件夹，然后输入以下命令，将 `<name>` 替换为唯一值，使项目名称唯一。</span><span class="sxs-lookup"><span data-stu-id="f1476-123">Navigate to the *repository* folder and enter the following command, replacing `<name>` with a unique value to make the project name unique.</span></span> 

   ```dotnetcli
   dotnet new console -n botsay-<name>
   ```

   <span data-ttu-id="f1476-124">例如，你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f1476-124">For example, you could run the following command:</span></span>

   ```dotnetcli
   dotnet new console -n botsay-nancydavolio
   ```

   <span data-ttu-id="f1476-125">此命令将在“repository”  文件夹下创建一个名为“botsay-\<name>”  的新文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1476-125">The command creates a new folder named *botsay-\<name>* under the *repository* folder.</span></span>

1. <span data-ttu-id="f1476-126">导航到“botsay-\<name>”  文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1476-126">Navigate to the *botsay-\<name>* folder.</span></span>

   ```console
   cd botsay-<name>
   ```

## <a name="add-the-code"></a><span data-ttu-id="f1476-127">添加代码</span><span class="sxs-lookup"><span data-stu-id="f1476-127">Add the code</span></span>

1. <span data-ttu-id="f1476-128">使用代码编辑器打开 `Program.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="f1476-128">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="f1476-129">将下面的 `using` 指令添加到文件的顶部：</span><span class="sxs-lookup"><span data-stu-id="f1476-129">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="f1476-130">将 `Main` 方法替换为以下代码，以便处理应用程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="f1476-130">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="f1476-131">如果未传递任何参数，将显示简短的帮助消息。</span><span class="sxs-lookup"><span data-stu-id="f1476-131">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="f1476-132">否则，所有参数都将连接到单个字符串中，并通过调用在下一步中创建的 `ShowBot` 方法进行打印。</span><span class="sxs-lookup"><span data-stu-id="f1476-132">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="f1476-133">添加一个名为 `ShowBot` 的新方法，该方法采用一个字符串参数。</span><span class="sxs-lookup"><span data-stu-id="f1476-133">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="f1476-134">该方法使用文本行打印出消息和机器人图像。</span><span class="sxs-lookup"><span data-stu-id="f1476-134">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="f1476-135">保存更改。</span><span class="sxs-lookup"><span data-stu-id="f1476-135">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="f1476-136">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="f1476-136">Test the application</span></span>

<span data-ttu-id="f1476-137">运行项目并观察输出。</span><span class="sxs-lookup"><span data-stu-id="f1476-137">Run the project and see the output.</span></span> <span data-ttu-id="f1476-138">尝试使用命令行处的这些变体来查看不同的结果：</span><span class="sxs-lookup"><span data-stu-id="f1476-138">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="f1476-139">位于 `--` 分隔符后的所有参数均会传递给应用程序。</span><span class="sxs-lookup"><span data-stu-id="f1476-139">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="f1476-140">打包工具</span><span class="sxs-lookup"><span data-stu-id="f1476-140">Package the tool</span></span>

<span data-ttu-id="f1476-141">在将应用程序作为工具打包并分发之前，你需要修改项目文件。</span><span class="sxs-lookup"><span data-stu-id="f1476-141">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span> 

1. <span data-ttu-id="f1476-142">打开“botsay-\<name>.csproj”  文件，然后将三个新的 XML 节点添加到 `<PropertyGroup>` 节点的末尾：</span><span class="sxs-lookup"><span data-stu-id="f1476-142">Open the *botsay-\<name>.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="f1476-143">`<ToolCommandName>` 是一个可选元素，用于指定在安装工具后将调用该工具的命令。</span><span class="sxs-lookup"><span data-stu-id="f1476-143">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="f1476-144">如果未提供此元素，则该工具的命令名称为没有“.csproj”  扩展名的项目文件名。</span><span class="sxs-lookup"><span data-stu-id="f1476-144">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="f1476-145">`<PackageOutputPath>` 是一个可选元素，用于确定将在何处生成 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="f1476-145">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="f1476-146">NuGet 包是.NET Core CLI 用于安装你的工具的包。</span><span class="sxs-lookup"><span data-stu-id="f1476-146">The NuGet package is what the .NET Core CLI uses to install your tool.</span></span>

   <span data-ttu-id="f1476-147">项目文件现在类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="f1476-147">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="f1476-148">通过运行 [dotnet pack](dotnet-pack.md) 命令创建 NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="f1476-148">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="f1476-149">“botsay-\<name>.1.0.0.nupkg”  文件在由“botsay-\<name>.csproj”  文件的 `<PackageOutputPath>` 值标识的文件夹中创建，在本示例中为“./nupkg”  文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1476-149">The *botsay-\<name>.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *botsay-\<name>.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="f1476-150">如果想要公开发布一个工具，你可以将其上传到 `https://www.nuget.org`。</span><span class="sxs-lookup"><span data-stu-id="f1476-150">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="f1476-151">该工具在 NuGet 上可用后，开发人员就可以使用 [dotnet tool install](dotnet-tool-install.md) 命令安装该工具。</span><span class="sxs-lookup"><span data-stu-id="f1476-151">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="f1476-152">在本教程中，你将直接从本地“nupkg”  文件夹安装包，因此无需将包上传到 NuGet。</span><span class="sxs-lookup"><span data-stu-id="f1476-152">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="f1476-153">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f1476-153">Troubleshoot</span></span>

<span data-ttu-id="f1476-154">如果在学习本教程时收到错误消息，请参阅[排查 .NET Core 工具使用问题](troubleshoot-usage-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f1476-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1476-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f1476-155">Next steps</span></span>

<span data-ttu-id="f1476-156">在本教程中，你创建了一个控制台应用程序并将其打包为工具。</span><span class="sxs-lookup"><span data-stu-id="f1476-156">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="f1476-157">若要了解如何使用该工具作为全局工具，请转到下一教程。</span><span class="sxs-lookup"><span data-stu-id="f1476-157">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f1476-158">安装和使用全局工具</span><span class="sxs-lookup"><span data-stu-id="f1476-158">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="f1476-159">如果需要，可以跳过全局工具教程，直接转到本地工具教程。</span><span class="sxs-lookup"><span data-stu-id="f1476-159">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f1476-160">安装和使用本地工具</span><span class="sxs-lookup"><span data-stu-id="f1476-160">Install and use a local tool</span></span>](local-tools-how-to-use.md)
