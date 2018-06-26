---
title: dotnet test 命令 - .NET Core CLI
description: dotnet test 命令可用于在给定项目中执行单元测试。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 8a10ac9175ee5fcf8649efbb07d8d382ac3afdc7
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696265"
---
# <a name="dotnet-test"></a><span data-ttu-id="37064-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="37064-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="37064-104">name</span><span class="sxs-lookup"><span data-stu-id="37064-104">Name</span></span>

<span data-ttu-id="37064-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="37064-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="37064-106">摘要</span><span class="sxs-lookup"><span data-stu-id="37064-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="37064-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="37064-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="37064-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="37064-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="37064-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="37064-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="37064-110">描述</span><span class="sxs-lookup"><span data-stu-id="37064-110">Description</span></span>

<span data-ttu-id="37064-111">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="37064-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="37064-112">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="37064-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="37064-113">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="37064-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="37064-114">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="37064-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="37064-115">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="37064-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="37064-116">自变量</span><span class="sxs-lookup"><span data-stu-id="37064-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="37064-117">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="37064-117">Path to the test project.</span></span> <span data-ttu-id="37064-118">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="37064-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="37064-119">选项</span><span class="sxs-lookup"><span data-stu-id="37064-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="37064-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="37064-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="37064-121">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="37064-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="37064-122">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="37064-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="37064-123">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="37064-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="37064-124">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序。</span><span class="sxs-lookup"><span data-stu-id="37064-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="37064-125">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="37064-125">Defines the build configuration.</span></span> <span data-ttu-id="37064-126">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="37064-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="37064-127">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="37064-127">Enables data collector for the test run.</span></span> <span data-ttu-id="37064-128">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="37064-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="37064-129">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="37064-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="37064-130">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="37064-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="37064-131">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="37064-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="37064-132">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="37064-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="37064-133">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="37064-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="37064-134">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="37064-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="37064-135">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="37064-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="37064-136">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="37064-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="37064-137">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="37064-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="37064-138">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37064-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="37064-139">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="37064-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="37064-140">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="37064-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="37064-141">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="37064-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="37064-142">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="37064-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="37064-143">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="37064-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="37064-144">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="37064-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="37064-145">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="37064-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="37064-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="37064-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="37064-147">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="37064-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="37064-148">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="37064-148">Defines the build configuration.</span></span> <span data-ttu-id="37064-149">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="37064-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="37064-150">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="37064-150">Enables data collector for the test run.</span></span> <span data-ttu-id="37064-151">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="37064-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="37064-152">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="37064-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="37064-153">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="37064-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="37064-154">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="37064-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="37064-155">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="37064-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="37064-156">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="37064-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="37064-157">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="37064-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="37064-158">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="37064-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="37064-159">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="37064-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="37064-160">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="37064-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="37064-161">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37064-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="37064-162">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="37064-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="37064-163">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="37064-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="37064-164">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="37064-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="37064-165">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="37064-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="37064-166">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="37064-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="37064-167">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="37064-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="37064-168">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="37064-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="37064-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="37064-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="37064-170">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="37064-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="37064-171">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="37064-171">Defines the build configuration.</span></span> <span data-ttu-id="37064-172">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="37064-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="37064-173">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="37064-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="37064-174">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="37064-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="37064-175">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="37064-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="37064-176">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="37064-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="37064-177">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="37064-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="37064-178">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="37064-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="37064-179">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="37064-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="37064-180">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="37064-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="37064-181">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="37064-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="37064-182">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="37064-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="37064-183">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="37064-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="37064-184">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="37064-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="37064-185">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="37064-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="37064-186">示例</span><span class="sxs-lookup"><span data-stu-id="37064-186">Examples</span></span>

<span data-ttu-id="37064-187">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="37064-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="37064-188">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="37064-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="37064-189">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="37064-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="37064-190">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="37064-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="37064-191">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="37064-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="37064-192">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="37064-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="37064-193">测试框架</span><span class="sxs-lookup"><span data-stu-id="37064-193">Test Framework</span></span> | <span data-ttu-id="37064-194">支持的属性</span><span class="sxs-lookup"><span data-stu-id="37064-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="37064-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="37064-195">MSTest</span></span>         | <ul><li><span data-ttu-id="37064-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="37064-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="37064-197">name</span><span class="sxs-lookup"><span data-stu-id="37064-197">Name</span></span></li><li><span data-ttu-id="37064-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="37064-198">ClassName</span></span></li><li><span data-ttu-id="37064-199">优先级</span><span class="sxs-lookup"><span data-stu-id="37064-199">Priority</span></span></li><li><span data-ttu-id="37064-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="37064-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="37064-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="37064-201">xUnit</span></span>          | <ul><li><span data-ttu-id="37064-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="37064-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="37064-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="37064-203">DisplayName</span></span></li><li><span data-ttu-id="37064-204">特征</span><span class="sxs-lookup"><span data-stu-id="37064-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="37064-205">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="37064-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="37064-206">运算符</span><span class="sxs-lookup"><span data-stu-id="37064-206">Operator</span></span> | <span data-ttu-id="37064-207">函数</span><span class="sxs-lookup"><span data-stu-id="37064-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="37064-208">完全匹配</span><span class="sxs-lookup"><span data-stu-id="37064-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="37064-209">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="37064-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="37064-210">包含</span><span class="sxs-lookup"><span data-stu-id="37064-210">Contains</span></span>        |

<span data-ttu-id="37064-211">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="37064-211">`<value>` is a string.</span></span> <span data-ttu-id="37064-212">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="37064-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="37064-213">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="37064-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="37064-214">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="37064-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="37064-215">运算符</span><span class="sxs-lookup"><span data-stu-id="37064-215">Operator</span></span>            | <span data-ttu-id="37064-216">函数</span><span class="sxs-lookup"><span data-stu-id="37064-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="37064-217">或</span><span class="sxs-lookup"><span data-stu-id="37064-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="37064-218">AND</span><span class="sxs-lookup"><span data-stu-id="37064-218">AND</span></span>      |

<span data-ttu-id="37064-219">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="37064-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="37064-220">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="37064-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37064-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="37064-221">See also</span></span>

[<span data-ttu-id="37064-222">框架和目标</span><span class="sxs-lookup"><span data-stu-id="37064-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
[<span data-ttu-id="37064-223">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="37064-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
