---
title: "dotnet-test 命令 - .NET Core CLI"
description: "“dotnet test”命令用于执行给定项目中的单元测试。"
keywords: "dotnet-test, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3308488672df2621c04de40f642c732f81284019
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

#<a name="dotnet-test"></a><span data-ttu-id="68a86-104">dotnet-test</span><span class="sxs-lookup"><span data-stu-id="68a86-104">dotnet-test</span></span>

## <a name="name"></a><span data-ttu-id="68a86-105">名称</span><span class="sxs-lookup"><span data-stu-id="68a86-105">Name</span></span>

<span data-ttu-id="68a86-106">`dotnet-test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="68a86-106">`dotnet-test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68a86-107">摘要</span><span class="sxs-lookup"><span data-stu-id="68a86-107">Synopsis</span></span>

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="68a86-108">描述</span><span class="sxs-lookup"><span data-stu-id="68a86-108">Description</span></span>

<span data-ttu-id="68a86-109">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="68a86-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="68a86-110">单元测试是控制台应用程序项目，它包含单元测试框架（如 MSTest、NUnit 或 xUnit）和该框架的 dotnet 测试运行程序上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="68a86-110">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="68a86-111">单元测试打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="68a86-111">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="68a86-112">测试项目还必须指定测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="68a86-112">Test projects also must specify the test runner.</span></span> <span data-ttu-id="68a86-113">使用普通 `<PackageReference>` 元素指定，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="68a86-113">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="68a86-114">[!code-xml[XUnit 基本模板](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="68a86-114">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="options"></a><span data-ttu-id="68a86-115">选项</span><span class="sxs-lookup"><span data-stu-id="68a86-115">Options</span></span>

`PROJECT`
    
<span data-ttu-id="68a86-116">指定测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="68a86-116">Specifies a path to the test project.</span></span> <span data-ttu-id="68a86-117">如果省略，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="68a86-117">If omitted, it defaults to current directory.</span></span>

`-h|--help`

<span data-ttu-id="68a86-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="68a86-118">Prints out a short help for the command.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="68a86-119">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="68a86-119">Settings to use when running tests.</span></span> 

`-t|--list-tests`

<span data-ttu-id="68a86-120">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="68a86-120">List all of the discovered tests in the current project.</span></span> 

`--filter <EXPRESSION>`

<span data-ttu-id="68a86-121">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="68a86-121">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="68a86-122">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="68a86-122">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="68a86-123">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="68a86-123">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="68a86-124">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="68a86-124">Use the custom test adapters from the specified path in the test run.</span></span> 

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="68a86-125">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="68a86-125">Specifies a logger for test results.</span></span> 

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="68a86-126">生成所根据的配置。</span><span class="sxs-lookup"><span data-stu-id="68a86-126">Configuration under which to build.</span></span> <span data-ttu-id="68a86-127">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="68a86-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="68a86-128">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="68a86-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="68a86-129">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="68a86-129">Directory in which to find the binaries to run.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="68a86-130">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="68a86-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span> 

`--no-build` 

<span data-ttu-id="68a86-131">运行前不生成测试项目。</span><span class="sxs-lookup"><span data-stu-id="68a86-131">Does not build the test project prior to running it.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="68a86-132">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="68a86-132">Sets the verbosity level of the command.</span></span> <span data-ttu-id="68a86-133">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="68a86-133">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="68a86-134">示例</span><span class="sxs-lookup"><span data-stu-id="68a86-134">Examples</span></span>

<span data-ttu-id="68a86-135">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="68a86-135">Run the tests in the project in the current directory:</span></span>

`dotnet test` 

<span data-ttu-id="68a86-136">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="68a86-136">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="68a86-137">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="68a86-137">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="68a86-138">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="68a86-138">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="68a86-139">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="68a86-139">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="68a86-140">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="68a86-140">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="68a86-141">测试框架</span><span class="sxs-lookup"><span data-stu-id="68a86-141">Test Framework</span></span> | <span data-ttu-id="68a86-142">支持的属性</span><span class="sxs-lookup"><span data-stu-id="68a86-142">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="68a86-143">MSTest</span><span class="sxs-lookup"><span data-stu-id="68a86-143">MSTest</span></span>         | <ul><li><span data-ttu-id="68a86-144">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="68a86-144">FullyQualifiedName</span></span></li><li><span data-ttu-id="68a86-145">名称</span><span class="sxs-lookup"><span data-stu-id="68a86-145">Name</span></span></li><li><span data-ttu-id="68a86-146">ClassName</span><span class="sxs-lookup"><span data-stu-id="68a86-146">ClassName</span></span></li><li><span data-ttu-id="68a86-147">优先级</span><span class="sxs-lookup"><span data-stu-id="68a86-147">Priority</span></span></li><li><span data-ttu-id="68a86-148">TestCategory</span><span class="sxs-lookup"><span data-stu-id="68a86-148">TestCategory</span></span></li></ul> |
| <span data-ttu-id="68a86-149">Xunit</span><span class="sxs-lookup"><span data-stu-id="68a86-149">Xunit</span></span>          | <ul><li><span data-ttu-id="68a86-150">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="68a86-150">FullyQualifiedName</span></span></li><li><span data-ttu-id="68a86-151">DisplayName</span><span class="sxs-lookup"><span data-stu-id="68a86-151">DisplayName</span></span></li><li><span data-ttu-id="68a86-152">特征</span><span class="sxs-lookup"><span data-stu-id="68a86-152">Traits</span></span></li></ul>                                   |

<span data-ttu-id="68a86-153">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="68a86-153">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="68a86-154">运算符</span><span class="sxs-lookup"><span data-stu-id="68a86-154">Operator</span></span> | <span data-ttu-id="68a86-155">函数</span><span class="sxs-lookup"><span data-stu-id="68a86-155">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="68a86-156">完全匹配</span><span class="sxs-lookup"><span data-stu-id="68a86-156">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="68a86-157">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="68a86-157">Not exact match</span></span> |
| `~`      | <span data-ttu-id="68a86-158">包含</span><span class="sxs-lookup"><span data-stu-id="68a86-158">Contains</span></span>        |

<span data-ttu-id="68a86-159">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="68a86-159">`<value>` is a string.</span></span> <span data-ttu-id="68a86-160">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="68a86-160">All the lookups are case insensitive.</span></span>

<span data-ttu-id="68a86-161">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="68a86-161">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="68a86-162">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="68a86-162">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="68a86-163">运算符</span><span class="sxs-lookup"><span data-stu-id="68a86-163">Operator</span></span> | <span data-ttu-id="68a86-164">函数</span><span class="sxs-lookup"><span data-stu-id="68a86-164">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="68a86-165">或</span><span class="sxs-lookup"><span data-stu-id="68a86-165">OR</span></span>       |
| `&`      | <span data-ttu-id="68a86-166">AND</span><span class="sxs-lookup"><span data-stu-id="68a86-166">AND</span></span>      |

<span data-ttu-id="68a86-167">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="68a86-167">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="68a86-168">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="68a86-168">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68a86-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="68a86-169">See also</span></span>

<span data-ttu-id="68a86-170">[框架和目标](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="68a86-170">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
[<span data-ttu-id="68a86-171">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="68a86-171">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

