---
title: "dotnet test 命令 - .NET Core CLI"
description: "dotnet test 命令可用于在给定项目中执行单元测试。"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 9eb5be38549711717c11767332bfc84920ea927a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="dotnet-test"></a><span data-ttu-id="15d67-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="15d67-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="15d67-104">名称</span><span class="sxs-lookup"><span data-stu-id="15d67-104">Name</span></span>

<span data-ttu-id="15d67-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="15d67-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="15d67-106">摘要</span><span class="sxs-lookup"><span data-stu-id="15d67-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="15d67-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="15d67-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="15d67-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="15d67-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="15d67-109">描述</span><span class="sxs-lookup"><span data-stu-id="15d67-109">Description</span></span>

<span data-ttu-id="15d67-110">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="15d67-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="15d67-111">单元测试是控制台应用程序项目，它包含单元测试框架（如 MSTest、NUnit 或 xUnit）和该框架的 dotnet 测试运行程序上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="15d67-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="15d67-112">单元测试打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="15d67-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="15d67-113">测试项目还必须指定测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="15d67-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="15d67-114">使用普通 `<PackageReference>` 元素指定，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="15d67-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="15d67-115">参数</span><span class="sxs-lookup"><span data-stu-id="15d67-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="15d67-116">指定测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="15d67-116">Specifies a path to the test project.</span></span> <span data-ttu-id="15d67-117">如果省略，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="15d67-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="15d67-118">选项</span><span class="sxs-lookup"><span data-stu-id="15d67-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="15d67-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="15d67-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="15d67-120">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="15d67-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="15d67-121">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="15d67-121">Defines the build configuration.</span></span> <span data-ttu-id="15d67-122">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="15d67-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="15d67-123">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="15d67-123">Enables data collector for the test run.</span></span> <span data-ttu-id="15d67-124">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="15d67-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="15d67-125">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="15d67-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="15d67-126">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="15d67-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="15d67-127">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="15d67-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="15d67-128">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="15d67-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="15d67-129">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="15d67-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="15d67-130">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="15d67-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="15d67-131">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="15d67-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="15d67-132">运行前不生成测试项目。</span><span class="sxs-lookup"><span data-stu-id="15d67-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="15d67-133">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="15d67-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="15d67-134">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="15d67-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="15d67-135">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="15d67-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="15d67-136">如果没有，将创建指定目录。</span><span class="sxs-lookup"><span data-stu-id="15d67-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="15d67-137">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="15d67-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="15d67-138">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="15d67-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="15d67-139">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="15d67-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="15d67-140">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="15d67-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="15d67-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="15d67-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="15d67-142">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="15d67-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="15d67-143">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="15d67-143">Defines the build configuration.</span></span> <span data-ttu-id="15d67-144">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="15d67-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="15d67-145">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="15d67-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="15d67-146">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="15d67-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="15d67-147">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="15d67-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="15d67-148">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="15d67-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="15d67-149">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="15d67-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="15d67-150">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="15d67-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="15d67-151">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="15d67-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="15d67-152">运行前不生成测试项目。</span><span class="sxs-lookup"><span data-stu-id="15d67-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="15d67-153">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="15d67-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="15d67-154">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="15d67-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="15d67-155">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="15d67-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="15d67-156">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="15d67-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="15d67-157">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="15d67-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="15d67-158">示例</span><span class="sxs-lookup"><span data-stu-id="15d67-158">Examples</span></span>

<span data-ttu-id="15d67-159">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="15d67-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="15d67-160">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="15d67-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="15d67-161">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="15d67-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="15d67-162">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="15d67-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="15d67-163">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="15d67-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="15d67-164">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="15d67-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="15d67-165">测试框架</span><span class="sxs-lookup"><span data-stu-id="15d67-165">Test Framework</span></span> | <span data-ttu-id="15d67-166">支持的属性</span><span class="sxs-lookup"><span data-stu-id="15d67-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="15d67-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="15d67-167">MSTest</span></span>         | <ul><li><span data-ttu-id="15d67-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="15d67-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="15d67-169">名称</span><span class="sxs-lookup"><span data-stu-id="15d67-169">Name</span></span></li><li><span data-ttu-id="15d67-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="15d67-170">ClassName</span></span></li><li><span data-ttu-id="15d67-171">优先级</span><span class="sxs-lookup"><span data-stu-id="15d67-171">Priority</span></span></li><li><span data-ttu-id="15d67-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="15d67-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="15d67-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="15d67-173">Xunit</span></span>          | <ul><li><span data-ttu-id="15d67-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="15d67-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="15d67-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="15d67-175">DisplayName</span></span></li><li><span data-ttu-id="15d67-176">特征</span><span class="sxs-lookup"><span data-stu-id="15d67-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="15d67-177">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="15d67-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="15d67-178">运算符</span><span class="sxs-lookup"><span data-stu-id="15d67-178">Operator</span></span> | <span data-ttu-id="15d67-179">函数</span><span class="sxs-lookup"><span data-stu-id="15d67-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="15d67-180">完全匹配</span><span class="sxs-lookup"><span data-stu-id="15d67-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="15d67-181">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="15d67-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="15d67-182">包含</span><span class="sxs-lookup"><span data-stu-id="15d67-182">Contains</span></span>        |

<span data-ttu-id="15d67-183">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="15d67-183">`<value>` is a string.</span></span> <span data-ttu-id="15d67-184">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="15d67-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="15d67-185">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="15d67-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="15d67-186">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="15d67-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="15d67-187">运算符</span><span class="sxs-lookup"><span data-stu-id="15d67-187">Operator</span></span> | <span data-ttu-id="15d67-188">函数</span><span class="sxs-lookup"><span data-stu-id="15d67-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="15d67-189">或</span><span class="sxs-lookup"><span data-stu-id="15d67-189">OR</span></span>       |
| `&`      | <span data-ttu-id="15d67-190">AND</span><span class="sxs-lookup"><span data-stu-id="15d67-190">AND</span></span>      |

<span data-ttu-id="15d67-191">可以将表达式括在括号中，使用条件运算符时 (例如， `(Name~TestMethod1) | (Name~TestMethod2)`)。</span><span class="sxs-lookup"><span data-stu-id="15d67-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="15d67-192">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="15d67-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15d67-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="15d67-193">See also</span></span>

 [<span data-ttu-id="15d67-194">框架和目标</span><span class="sxs-lookup"><span data-stu-id="15d67-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="15d67-195">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="15d67-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
