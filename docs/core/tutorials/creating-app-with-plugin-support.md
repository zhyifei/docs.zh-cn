---
title: 使用插件创建 .NET Core 应用程序
description: 了解如何创建支持插件的 .NET Core 应用程序。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: f2997c778b87ecd88c0fd2fadf491763066a4950
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739588"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="32aa9-103">使用插件创建 .NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="32aa9-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="32aa9-104">本教程介绍了如何：</span><span class="sxs-lookup"><span data-stu-id="32aa9-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="32aa9-105">构建支持插件的项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-105">Structure a project to support plugins.</span></span>
- <span data-ttu-id="32aa9-106">创建自定义 <xref:System.Runtime.Loader.AssemblyLoadContext> 加载每个插件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-106">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="32aa9-107">使用 `System.Runtime.Loader.AssemblyDependencyResolver` 类型允许插件具有依赖项。</span><span class="sxs-lookup"><span data-stu-id="32aa9-107">Use the `System.Runtime.Loader.AssemblyDependencyResolver` type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="32aa9-108">只需复制生成项目就可以轻松部署的作者插件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-108">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32aa9-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="32aa9-109">Prerequisites</span></span>

- <span data-ttu-id="32aa9-110">安装 [.NET Core 3.0 预览版 2 SDK](https://www.microsoft.com/net/core) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="32aa9-110">Install the [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) or a newer version.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="32aa9-111">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="32aa9-111">Create the application</span></span>

<span data-ttu-id="32aa9-112">第一步是创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="32aa9-112">The first step is to create the application:</span></span>

1. <span data-ttu-id="32aa9-113">创建新文件夹，并在该文件夹中运行 `dotnet new console -o AppWithPlugin`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-113">Create a new folder, and in that folder run `dotnet new console -o AppWithPlugin`.</span></span> 
2. <span data-ttu-id="32aa9-114">为了更容易生成项目，创建 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-114">To make building the project easier, create a Visual Studio solution file.</span></span> <span data-ttu-id="32aa9-115">在同一文件夹中运行 `dotnet new sln`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-115">Run `dotnet new sln` in the same folder.</span></span> 
3. <span data-ttu-id="32aa9-116">运行 `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` 向解决方案添加应用项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-116">Run `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` to add the app project to the solution.</span></span>

<span data-ttu-id="32aa9-117">现在，我们可以填写应用程序的主干。</span><span class="sxs-lookup"><span data-stu-id="32aa9-117">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="32aa9-118">使用下面的代码替换 AppWithPlugin/Program.cs 文件中的代码：</span><span class="sxs-lookup"><span data-stu-id="32aa9-118">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="32aa9-119">创建插件接口</span><span class="sxs-lookup"><span data-stu-id="32aa9-119">Create the plugin interfaces</span></span>

<span data-ttu-id="32aa9-120">使用插件生成应用的下一步是定义插件需要实现的接口。</span><span class="sxs-lookup"><span data-stu-id="32aa9-120">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="32aa9-121">我们建议创建类库，其中包含计划用于在应用和插件之间通信的任何类型。</span><span class="sxs-lookup"><span data-stu-id="32aa9-121">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="32aa9-122">此部分允许将插件接口作为包发布，而无需发布完整的应用程序。</span><span class="sxs-lookup"><span data-stu-id="32aa9-122">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="32aa9-123">在项目的根文件夹中，运行 `dotnet new classlib -o PluginBase`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-123">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="32aa9-124">并运行 `dotnet sln add PluginBase/PluginBase.csproj` 向解决方案文件添加项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-124">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="32aa9-125">删除 `PluginBase/Class1.cs` 文件，并使用以下接口定义在名为 `ICommand.cs` 的 `PluginBase` 文件夹中创建新的文件：</span><span class="sxs-lookup"><span data-stu-id="32aa9-125">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

<span data-ttu-id="32aa9-126">此 `ICommand` 接口是所有插件将实现的接口。</span><span class="sxs-lookup"><span data-stu-id="32aa9-126">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="32aa9-127">由于已定义 `ICommand` 接口，所以应用程序项目可以填写更多内容。</span><span class="sxs-lookup"><span data-stu-id="32aa9-127">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="32aa9-128">使用根文件夹中的 `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` 命令将引用从 `AppWithPlugin` 项目添加到 `PluginBase` 项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-128">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="32aa9-129">使用以下代码片段替换 `// Load commands from plugins` 注释，使其能够从给定文件路径加载插件：</span><span class="sxs-lookup"><span data-stu-id="32aa9-129">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```



<span data-ttu-id="32aa9-130">然后用以下代码片段替换 `// Output the loaded commands` 注释：</span><span class="sxs-lookup"><span data-stu-id="32aa9-130">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="32aa9-131">使用以下代码片段替换 `// Execute the command with the name passed as an argument` 注释：</span><span class="sxs-lookup"><span data-stu-id="32aa9-131">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="32aa9-132">最后，将静态方法添加到名为 `LoadPlugin` 和 `CreateCommands` 的 `Program` 类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32aa9-132">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a><span data-ttu-id="32aa9-133">加载插件</span><span class="sxs-lookup"><span data-stu-id="32aa9-133">Load plugins</span></span>

<span data-ttu-id="32aa9-134">现在，应用程序可以正确加载和实例化来自已加载的插件程序集的命令，但仍然无法加载插件程序集。</span><span class="sxs-lookup"><span data-stu-id="32aa9-134">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it is still unable to load the plugin assemblies.</span></span> <span data-ttu-id="32aa9-135">使用以下内容在 AppWithPlugin 文件夹中创建名为 PluginLoadContext.cs 的文件：</span><span class="sxs-lookup"><span data-stu-id="32aa9-135">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="32aa9-136">`PluginLoadContext` 类型派生自 <xref:System.Runtime.Loader.AssemblyLoadContext>。</span><span class="sxs-lookup"><span data-stu-id="32aa9-136">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="32aa9-137">`AssemblyLoadContext` 类型是运行时中的特殊类型，该类型允许开发人员将已加载的程序集隔离到不同的组中，以确保程序集版本不冲突。</span><span class="sxs-lookup"><span data-stu-id="32aa9-137">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions do not conflict.</span></span> <span data-ttu-id="32aa9-138">此外，自定义 `AssemblyLoadContext` 可以选择不同路径来加载程序集格式并重写默认行为。</span><span class="sxs-lookup"><span data-stu-id="32aa9-138">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="32aa9-139">`PluginLoadContext` 使用 .NET Core 3.0 中引入的 `AssemblyDependencyResolver` 类型的实例将程序集名称解析为路径。</span><span class="sxs-lookup"><span data-stu-id="32aa9-139">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="32aa9-140">`AssemblyDependencyResolver` 对象是使用 .NET 类库的路径构造的。</span><span class="sxs-lookup"><span data-stu-id="32aa9-140">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="32aa9-141">它根据类库的 deps.json 文件（其路径传递给 `AssemblyDependencyResolver` 构造函数）将程序集和本机库解析为它们的相对路径。</span><span class="sxs-lookup"><span data-stu-id="32aa9-141">It resolves assemblies and native libraries to their relative paths based on the *deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="32aa9-142">自定义 `AssemblyLoadContext` 使插件能够拥有自己的依赖项，`AssemblyDependencyResolver` 使正确加载依赖项变得容易。</span><span class="sxs-lookup"><span data-stu-id="32aa9-142">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="32aa9-143">由于 `AppWithPlugin` 项目具有 `PluginLoadContext` 类型，所以请使用以下正文更新 `Program.LoadPlugin` 方法：</span><span class="sxs-lookup"><span data-stu-id="32aa9-143">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

<span data-ttu-id="32aa9-144">通过为每个插件使用不同的 `PluginLoadContext` 实例，插件可以具有不同的甚至冲突的依赖项，而不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="32aa9-144">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="create-a-simple-plugin-with-no-dependencies"></a><span data-ttu-id="32aa9-145">创建不具有依赖项的简单插件</span><span class="sxs-lookup"><span data-stu-id="32aa9-145">Create a simple plugin with no dependencies</span></span>

<span data-ttu-id="32aa9-146">返回到根文件夹，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="32aa9-146">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="32aa9-147">运行 `dotnet new classlib -o HelloPlugin` 创建名为 `HelloPlugin` 的新类库项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-147">Run `dotnet new classlib -o HelloPlugin` to create a new class library project named `HelloPlugin`.</span></span>
2. <span data-ttu-id="32aa9-148">运行 `dotnet sln add HelloPlugin/HelloPlugin.csproj` 向 `AppWithPlugin` 解决方案添加项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-148">Run `dotnet sln add HelloPlugin/HelloPlugin.csproj` to add the project to the `AppWithPlugin` solution.</span></span> 
3. <span data-ttu-id="32aa9-149">使用以下内容将 HelloPlugin/Class1.cs 文件替换为名为 HelloCommand.cs 的文件：</span><span class="sxs-lookup"><span data-stu-id="32aa9-149">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="32aa9-150">现在，打开 HelloPlugin.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-150">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="32aa9-151">它应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="32aa9-151">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="32aa9-152">在 `<Project>` 标记之间添加以下元素：</span><span class="sxs-lookup"><span data-stu-id="32aa9-152">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

<span data-ttu-id="32aa9-153">`<Private>false</Private>` 元素非常重要。</span><span class="sxs-lookup"><span data-stu-id="32aa9-153">The `<Private>false</Private>` element is very important.</span></span> <span data-ttu-id="32aa9-154">它告知 MSBuild 不要将 PluginBase.dll 复制到 HelloPlugin 的输出目录。</span><span class="sxs-lookup"><span data-stu-id="32aa9-154">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="32aa9-155">如果 PluginBase.dll 程序集出现在输出目录中，`PluginLoadContext` 将在那里查找到该程序集并在加载 HelloPlugin.dll 程序集时加载它。</span><span class="sxs-lookup"><span data-stu-id="32aa9-155">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="32aa9-156">此时，`HelloPlugin.HelloCommand` 类型将从 `HelloPlugin` 项目的输出目录中的 PluginBase.dll 实现 `ICommand` 接口，而不是加载到默认加载上下文中的 `ICommand` 接口。</span><span class="sxs-lookup"><span data-stu-id="32aa9-156">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="32aa9-157">因为运行时将这两种类型视为不同程序集的不同类型，所以 `AppWithPlugin.Program.CreateCommands` 方法将找不到命令。</span><span class="sxs-lookup"><span data-stu-id="32aa9-157">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method will not find the commands.</span></span> <span data-ttu-id="32aa9-158">因此，对包含插件接口的程序集的引用需要 `<Private>false</Private>` 元数据。</span><span class="sxs-lookup"><span data-stu-id="32aa9-158">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="32aa9-159">因为 `HelloPlugin` 项目已完成，所以我们应该更新 `AppWithPlugin` 项目，以确认可以找到 `HelloPlugin` 插件的位置。</span><span class="sxs-lookup"><span data-stu-id="32aa9-159">Now that the `HelloPlugin` project is complete, we should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="32aa9-160">在 `// Paths to plugins to load` 注释之后，添加 `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` 作为 `pluginPaths` 数组的元素。</span><span class="sxs-lookup"><span data-stu-id="32aa9-160">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` as an element of the `pluginPaths` array.</span></span>

## <a name="create-a-plugin-with-library-dependencies"></a><span data-ttu-id="32aa9-161">创建具有库依赖项的插件</span><span class="sxs-lookup"><span data-stu-id="32aa9-161">Create a plugin with library dependencies</span></span>

<span data-ttu-id="32aa9-162">几乎所有插件都比简单的“Hello World”更复杂，而且许多插件都具有其他库上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="32aa9-162">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="32aa9-163">示例中的 `JsonPlugin` 和 `OldJson` 插件项目显示了具有 `Newtonsoft.Json` 上的 NuGet 包依赖项的两个插件示例。</span><span class="sxs-lookup"><span data-stu-id="32aa9-163">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="32aa9-164">项目文件本身没有关于项目引用的任何特殊信息，并且（在将插件路径添加到 `pluginPaths` 数组之后）即使是在 AppWithPlugin 应用的同一执行中运行，插件也能完美运行。</span><span class="sxs-lookup"><span data-stu-id="32aa9-164">The project files themselves do not have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="32aa9-165">但是，这些项目不会将引用的程序集复制到它们的输出目录中，因此需要将这些程序集呈递到用户的计算机上，以便插件能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="32aa9-165">However, these projects do not copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="32aa9-166">解决此问题有两种方法。</span><span class="sxs-lookup"><span data-stu-id="32aa9-166">There are two ways to work around this problem.</span></span> <span data-ttu-id="32aa9-167">第一种是使用 `dotnet publish` 命令发布类库。</span><span class="sxs-lookup"><span data-stu-id="32aa9-167">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="32aa9-168">或者，如果希望能够将 `dotnet build` 的输出用于插件，可以在插件的项目文件中的 `<PropertyGroup>` 标记之间添加 `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` 属性。</span><span class="sxs-lookup"><span data-stu-id="32aa9-168">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="32aa9-169">有关示例，请参阅 `XcopyablePlugin` 插件项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-169">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-plugin-examples-in-the-sample"></a><span data-ttu-id="32aa9-170">示例中的其他插件示例</span><span class="sxs-lookup"><span data-stu-id="32aa9-170">Other plugin examples in the sample</span></span>

<span data-ttu-id="32aa9-171">`AssemblyDependencyResolver` 对象还可以解析 NuGet 包和已本地化的附属程序集中所包含的本机库。</span><span class="sxs-lookup"><span data-stu-id="32aa9-171">The `AssemblyDependencyResolver` object can also resolve native libraries included in NuGet packages as well as localized satellite assemblies.</span></span> <span data-ttu-id="32aa9-172">`UVPlugin` 和 `FrenchPlugin` 分别演示了这些场景。</span><span class="sxs-lookup"><span data-stu-id="32aa9-172">The `UVPlugin` and `FrenchPlugin` demonstrate these scenarios respectively.</span></span>

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a><span data-ttu-id="32aa9-173">如何引用 NuGet 包中定义的插件接口程序集</span><span class="sxs-lookup"><span data-stu-id="32aa9-173">How to reference a plugin interface assembly defined in a NuGet package</span></span>

<span data-ttu-id="32aa9-174">假设存在应用 A，它具有 NuGet 包（名为 `A.PluginBase`）中定义的插件接口。</span><span class="sxs-lookup"><span data-stu-id="32aa9-174">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="32aa9-175">如何在插件项目中正确引用包？</span><span class="sxs-lookup"><span data-stu-id="32aa9-175">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="32aa9-176">对于项目引用，使用项目文件的 `ProjectReference` 元素上的 `<Private>false</Private>` 元数据会阻止将 dll 复制到输出。</span><span class="sxs-lookup"><span data-stu-id="32aa9-176">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="32aa9-177">若要正确引用 `A.PluginBase` 包，应将项目文件中的 `<PackageReference>` 元素更改为以下内容：</span><span class="sxs-lookup"><span data-stu-id="32aa9-177">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="32aa9-178">此操作会阻止将 `A.PluginBase` 程序集复制到插件的输出目录，并确保插件将使用 A 版本的 `A.PluginBase`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-178">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="32aa9-179">插件目标框架建议</span><span class="sxs-lookup"><span data-stu-id="32aa9-179">Plugin target framework recommendations</span></span>

<span data-ttu-id="32aa9-180">因为插件依赖项加载使用 deps.json 文件，所以存在一个与插件的目标框架相关的问题。</span><span class="sxs-lookup"><span data-stu-id="32aa9-180">Because plugin dependency loading uses the *deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="32aa9-181">具体来说，插件应该以运行时为目标，比如 .NET Core 3.0，而不是某一版本的 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="32aa9-181">Specifically, your plugins should target a runtime, such as .NET Core 3.0, instead of a version of .NET Standard.</span></span> <span data-ttu-id="32aa9-182">`deps.json` 文件基于项目所针对的框架生成，而且由于许多与 .NET Standard 兼容的包提供了用于针对 .NET Standard 进行生成的引用程序集和用于特定运行时的实现程序集，因此 `deps.json` 可能无法正确查看实现程序集，或者它可能会获取 .NET Standard 版本的程序集，而不是期望的 .NET Core 版本的程序集。</span><span class="sxs-lookup"><span data-stu-id="32aa9-182">The `deps.json` file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the `deps.json` may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>
