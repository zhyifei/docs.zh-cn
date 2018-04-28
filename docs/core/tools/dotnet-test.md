---
title: dotnet test 命令 - .NET Core CLI
description: dotnet test 命令可用于在给定项目中执行单元测试。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 04af96bb53cc4fdac2e52311f9197eb1ee2b112d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="dfe3f-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="dfe3f-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="dfe3f-104">name</span><span class="sxs-lookup"><span data-stu-id="dfe3f-104">Name</span></span>

<span data-ttu-id="dfe3f-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dfe3f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="dfe3f-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dfe3f-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dfe3f-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfe3f-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfe3f-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="dfe3f-109">描述</span><span class="sxs-lookup"><span data-stu-id="dfe3f-109">Description</span></span>

<span data-ttu-id="dfe3f-110">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="dfe3f-111">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="dfe3f-112">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="dfe3f-113">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="dfe3f-114">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="dfe3f-115">自变量</span><span class="sxs-lookup"><span data-stu-id="dfe3f-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="dfe3f-116">指定测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-116">Specifies a path to the test project.</span></span> <span data-ttu-id="dfe3f-117">如果省略，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="dfe3f-118">选项</span><span class="sxs-lookup"><span data-stu-id="dfe3f-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dfe3f-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dfe3f-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="dfe3f-120">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="dfe3f-121">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-121">Defines the build configuration.</span></span> <span data-ttu-id="dfe3f-122">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="dfe3f-123">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-123">Enables data collector for the test run.</span></span> <span data-ttu-id="dfe3f-124">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="dfe3f-125">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="dfe3f-126">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="dfe3f-127">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="dfe3f-128">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="dfe3f-129">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="dfe3f-130">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="dfe3f-131">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="dfe3f-132">运行前不生成测试项目。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="dfe3f-133">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="dfe3f-134">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="dfe3f-135">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="dfe3f-136">如果没有，将创建指定目录。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="dfe3f-137">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="dfe3f-138">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="dfe3f-139">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="dfe3f-140">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfe3f-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfe3f-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="dfe3f-142">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="dfe3f-143">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-143">Defines the build configuration.</span></span> <span data-ttu-id="dfe3f-144">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="dfe3f-145">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="dfe3f-146">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="dfe3f-147">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="dfe3f-148">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="dfe3f-149">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="dfe3f-150">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="dfe3f-151">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="dfe3f-152">运行前不生成测试项目。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="dfe3f-153">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="dfe3f-154">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="dfe3f-155">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="dfe3f-156">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="dfe3f-157">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="dfe3f-158">示例</span><span class="sxs-lookup"><span data-stu-id="dfe3f-158">Examples</span></span>

<span data-ttu-id="dfe3f-159">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="dfe3f-160">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="dfe3f-161">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="dfe3f-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="dfe3f-162">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="dfe3f-163">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="dfe3f-164">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="dfe3f-165">测试框架</span><span class="sxs-lookup"><span data-stu-id="dfe3f-165">Test Framework</span></span> | <span data-ttu-id="dfe3f-166">支持的属性</span><span class="sxs-lookup"><span data-stu-id="dfe3f-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="dfe3f-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="dfe3f-167">MSTest</span></span>         | <ul><li><span data-ttu-id="dfe3f-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="dfe3f-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="dfe3f-169">name</span><span class="sxs-lookup"><span data-stu-id="dfe3f-169">Name</span></span></li><li><span data-ttu-id="dfe3f-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="dfe3f-170">ClassName</span></span></li><li><span data-ttu-id="dfe3f-171">优先级</span><span class="sxs-lookup"><span data-stu-id="dfe3f-171">Priority</span></span></li><li><span data-ttu-id="dfe3f-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="dfe3f-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="dfe3f-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="dfe3f-173">Xunit</span></span>          | <ul><li><span data-ttu-id="dfe3f-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="dfe3f-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="dfe3f-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dfe3f-175">DisplayName</span></span></li><li><span data-ttu-id="dfe3f-176">特征</span><span class="sxs-lookup"><span data-stu-id="dfe3f-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="dfe3f-177">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="dfe3f-178">运算符</span><span class="sxs-lookup"><span data-stu-id="dfe3f-178">Operator</span></span> | <span data-ttu-id="dfe3f-179">函数</span><span class="sxs-lookup"><span data-stu-id="dfe3f-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="dfe3f-180">完全匹配</span><span class="sxs-lookup"><span data-stu-id="dfe3f-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="dfe3f-181">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="dfe3f-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="dfe3f-182">包含</span><span class="sxs-lookup"><span data-stu-id="dfe3f-182">Contains</span></span>        |

<span data-ttu-id="dfe3f-183">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-183">`<value>` is a string.</span></span> <span data-ttu-id="dfe3f-184">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="dfe3f-185">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="dfe3f-186">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="dfe3f-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="dfe3f-187">运算符</span><span class="sxs-lookup"><span data-stu-id="dfe3f-187">Operator</span></span> | <span data-ttu-id="dfe3f-188">函数</span><span class="sxs-lookup"><span data-stu-id="dfe3f-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="dfe3f-189">或</span><span class="sxs-lookup"><span data-stu-id="dfe3f-189">OR</span></span>       |
| `&`      | <span data-ttu-id="dfe3f-190">AND</span><span class="sxs-lookup"><span data-stu-id="dfe3f-190">AND</span></span>      |

<span data-ttu-id="dfe3f-191">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="dfe3f-192">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="dfe3f-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfe3f-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfe3f-193">See also</span></span>

 [<span data-ttu-id="dfe3f-194">框架和目标</span><span class="sxs-lookup"><span data-stu-id="dfe3f-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="dfe3f-195">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="dfe3f-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
