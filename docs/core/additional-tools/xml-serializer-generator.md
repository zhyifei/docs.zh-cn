---
title: "在 .NET Core 上使用 Microsoft XML 序列化程序生成器"
description: "Microsoft XML 序列化程序生成器概述。"
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: b2f52a068d128b2eb978c9e086508bd87e103ebc
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="69328-103">在 .NET Core 上使用 Microsoft XML 序列化程序生成器</span><span class="sxs-lookup"><span data-stu-id="69328-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="69328-104">本教程介绍如何在 C# .NET Core 应用程序中使用 Microsoft XML 序列化程序生成器。</span><span class="sxs-lookup"><span data-stu-id="69328-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="69328-105">在本教程中可学习：
</span><span class="sxs-lookup"><span data-stu-id="69328-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="69328-106">如何创建 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="69328-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="69328-107">如何向 Microsoft.XmlSerializer.Generator 包中添加引用</span><span class="sxs-lookup"><span data-stu-id="69328-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="69328-108">如何编辑 MyApp.csproj 以添加依赖项</span><span class="sxs-lookup"><span data-stu-id="69328-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="69328-109">如何添加类和 XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="69328-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="69328-110">如何生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="69328-110">How to build and run the application</span></span> 

<span data-ttu-id="69328-111">正如适用于 .NET Framework 的 [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)，[Microsoft.XmlSerializer.Generator NuGet 包](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) 是适用于 .NET Core 和 .NET 标准项目的等效项。</span><span class="sxs-lookup"><span data-stu-id="69328-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="69328-112">它为程序集中包含的类型创建 XML 序列化程序集，从而提高使用 <xref:System.Xml.Serialization.XmlSerializer> 序列化或反序列化这些类型对象时，XML 序列化的启动性能。</span><span class="sxs-lookup"><span data-stu-id="69328-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69328-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="69328-113">Prerequisites</span></span>

<span data-ttu-id="69328-114">完成本教程：</span><span class="sxs-lookup"><span data-stu-id="69328-114">To complete this tutorial:</span></span>

* <span data-ttu-id="69328-115">安装 [.NET Core SDK 2.1.3 或更高版本](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="69328-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="69328-116">安装常用的代码编辑器（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="69328-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="69328-117">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="69328-117">Need to install a code editor?</span></span> <span data-ttu-id="69328-118">试用 [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)！</span><span class="sxs-lookup"><span data-stu-id="69328-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="69328-119">在 .NET Core 控制台应用程序中使用 Microsoft XML 序列化程序生成器</span><span class="sxs-lookup"><span data-stu-id="69328-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="69328-120">以下说明将展示如何在 .NET Core 控制台应用程序中使用 XML 序列化程序生成器。</span><span class="sxs-lookup"><span data-stu-id="69328-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="69328-121">创建 .NET Core 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="69328-121">Create a .NET Core console application</span></span>

<span data-ttu-id="69328-122">打开命令提示符，创建一个名为“MyApp”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="69328-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="69328-123">导航到创建的文件夹，并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="69328-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="69328-124">在 MyApp 项目中向 Microsoft.XmlSerializer.Generator 包添加引用</span><span class="sxs-lookup"><span data-stu-id="69328-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="69328-125">使用 [`dotnet add package`](../tools//dotnet-add-package.md) 命令在项目中添加引用。</span><span class="sxs-lookup"><span data-stu-id="69328-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="69328-126">类型：</span><span class="sxs-lookup"><span data-stu-id="69328-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="69328-127">添加包后，验证对 MyApp.csproj 的更改</span><span class="sxs-lookup"><span data-stu-id="69328-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="69328-128">打开代码编辑器并开始操作！</span><span class="sxs-lookup"><span data-stu-id="69328-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="69328-129">仍从生成了应用的 MyApp 目录中进行操作。</span><span class="sxs-lookup"><span data-stu-id="69328-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="69328-130">在文本编辑器中打开 MyApp.csproj。</span><span class="sxs-lookup"><span data-stu-id="69328-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="69328-131">运行 [`dotnet add package`](../tools//dotnet-add-package.md) 命令后，会将以下行添加到 MyApp.csproj 项目文件中：</span><span class="sxs-lookup"><span data-stu-id="69328-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="69328-132">为 .NET Core CLI 工具支持添加其他 ItemGroup 部分</span><span class="sxs-lookup"><span data-stu-id="69328-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="69328-133">在已检查的 `ItemGroup` 部分后添加以下行：</span><span class="sxs-lookup"><span data-stu-id="69328-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="69328-134">在应用程序中添加类</span><span class="sxs-lookup"><span data-stu-id="69328-134">Add a class in the application</span></span>

<span data-ttu-id="69328-135">在文本编辑器中打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="69328-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="69328-136">在 Program.cs 中添加名为“MyClass”的类。</span><span class="sxs-lookup"><span data-stu-id="69328-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="69328-137">为 MyClass 创建 `XmlSerializer`</span><span class="sxs-lookup"><span data-stu-id="69328-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="69328-138">在 Main 中添加以下行，为 MyClass 创建 `XmlSerializer`：</span><span class="sxs-lookup"><span data-stu-id="69328-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="69328-139">编译和运行应用程序</span><span class="sxs-lookup"><span data-stu-id="69328-139">Build and run the application</span></span>

<span data-ttu-id="69328-140">继续在 MyApp 文件夹中，通过 [`dotnet run`](../tools/dotnet-run.md) 运行应用程序，并在运行时自动加载和使用预生成的序列化程序。</span><span class="sxs-lookup"><span data-stu-id="69328-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="69328-141">在控制台窗口中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="69328-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="69328-142">[`dotnet run`](../tools/dotnet-run.md) 调用 [`dotnet build`](../tools/dotnet-build.md) 来确保已生成要生成的目标，然后调用 `dotnet <assembly.dll>` 运行目标应用程序。</span><span class="sxs-lookup"><span data-stu-id="69328-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69328-143">本教程中用来运行应用程序的命令和步骤仅用于开发过程。</span><span class="sxs-lookup"><span data-stu-id="69328-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="69328-144">准备好部署应用后，查看适用于 .NET Core 应用的不同[部署策略](../deploying/index.md)和 [`dotnet publish`](../tools/dotnet-publish.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="69328-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="69328-145">如果一切顺利，则会在输出文件夹中生成名为“MyApp.XmlSerializers.dll”的程序集。</span><span class="sxs-lookup"><span data-stu-id="69328-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="69328-146">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="69328-146">Congratulations!</span></span> <span data-ttu-id="69328-147">你刚才已完成：</span><span class="sxs-lookup"><span data-stu-id="69328-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="69328-148">创建 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="69328-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="69328-149">向 Microsoft.XmlSerializer.Generator 包中添加引用。</span><span class="sxs-lookup"><span data-stu-id="69328-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="69328-150">编辑 MyApp.csproj 以添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="69328-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="69328-151">添加类和 XmlSerializer。</span><span class="sxs-lookup"><span data-stu-id="69328-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="69328-152">生成和运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="69328-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="69328-153">相关资源</span><span class="sxs-lookup"><span data-stu-id="69328-153">Related Resources</span></span>

* [<span data-ttu-id="69328-154">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="69328-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="69328-155">如何：使用 XmlSerializer 进行序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="69328-155">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
* [<span data-ttu-id="69328-156">如何：使用 XmlSerializer 进行序列化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69328-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
