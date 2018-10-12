---
title: dotnet test 命令 - .NET Core CLI
description: dotnet test 命令可用于在给定项目中执行单元测试。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e80ba874ec8d0fbc49858719dc3b9b6e02254c78
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696451"
---
# <a name="dotnet-test"></a><span data-ttu-id="77a44-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="77a44-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="77a44-104">name</span><span class="sxs-lookup"><span data-stu-id="77a44-104">Name</span></span>

<span data-ttu-id="77a44-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="77a44-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="77a44-106">摘要</span><span class="sxs-lookup"><span data-stu-id="77a44-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="77a44-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="77a44-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="77a44-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="77a44-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="77a44-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="77a44-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="77a44-110">描述</span><span class="sxs-lookup"><span data-stu-id="77a44-110">Description</span></span>

<span data-ttu-id="77a44-111">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="77a44-112">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="77a44-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="77a44-113">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="77a44-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="77a44-114">如果所有测试均成功，测试运行程序将返回 0 作为退出代码；否则将返回 1。</span><span class="sxs-lookup"><span data-stu-id="77a44-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="77a44-115">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="77a44-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="77a44-116">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="77a44-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="77a44-117">自变量</span><span class="sxs-lookup"><span data-stu-id="77a44-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="77a44-118">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="77a44-118">Path to the test project.</span></span> <span data-ttu-id="77a44-119">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="77a44-120">选项</span><span class="sxs-lookup"><span data-stu-id="77a44-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="77a44-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="77a44-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="77a44-122">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="77a44-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="77a44-123">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="77a44-124">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="77a44-125">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序。</span><span class="sxs-lookup"><span data-stu-id="77a44-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="77a44-126">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="77a44-126">Defines the build configuration.</span></span> <span data-ttu-id="77a44-127">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="77a44-128">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="77a44-128">Enables data collector for the test run.</span></span> <span data-ttu-id="77a44-129">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="77a44-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="77a44-130">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="77a44-131">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="77a44-132">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="77a44-133">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="77a44-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="77a44-134">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="77a44-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="77a44-135">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="77a44-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="77a44-136">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="77a44-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="77a44-137">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="77a44-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="77a44-138">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="77a44-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="77a44-139">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="77a44-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="77a44-140">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="77a44-141">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="77a44-142">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="77a44-143">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="77a44-144">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="77a44-145">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="77a44-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="77a44-146">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="77a44-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="77a44-147">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="77a44-147">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="77a44-148">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="77a44-148">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="77a44-149">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="77a44-149">Defines the build configuration.</span></span> <span data-ttu-id="77a44-150">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-150">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="77a44-151">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="77a44-151">Enables data collector for the test run.</span></span> <span data-ttu-id="77a44-152">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="77a44-152">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="77a44-153">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-153">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="77a44-154">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-154">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="77a44-155">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-155">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="77a44-156">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="77a44-156">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="77a44-157">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="77a44-157">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="77a44-158">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="77a44-158">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="77a44-159">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="77a44-159">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="77a44-160">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="77a44-160">Doesn't build the test project before running it.</span></span> <span data-ttu-id="77a44-161">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="77a44-161">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="77a44-162">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="77a44-162">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="77a44-163">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-163">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="77a44-164">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-164">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="77a44-165">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-165">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="77a44-166">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-166">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="77a44-167">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-167">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="77a44-168">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="77a44-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="77a44-169">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="77a44-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="77a44-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="77a44-170">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="77a44-171">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="77a44-171">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="77a44-172">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="77a44-172">Defines the build configuration.</span></span> <span data-ttu-id="77a44-173">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-173">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="77a44-174">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-174">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="77a44-175">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="77a44-175">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="77a44-176">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-176">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="77a44-177">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="77a44-177">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="77a44-178">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="77a44-178">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="77a44-179">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="77a44-179">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="77a44-180">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="77a44-180">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="77a44-181">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="77a44-181">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="77a44-182">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="77a44-182">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="77a44-183">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="77a44-183">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="77a44-184">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="77a44-184">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="77a44-185">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="77a44-185">Sets the verbosity level of the command.</span></span> <span data-ttu-id="77a44-186">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="77a44-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="77a44-187">示例</span><span class="sxs-lookup"><span data-stu-id="77a44-187">Examples</span></span>

<span data-ttu-id="77a44-188">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="77a44-188">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="77a44-189">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="77a44-189">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="77a44-190">在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：</span><span class="sxs-lookup"><span data-stu-id="77a44-190">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="77a44-191">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="77a44-191">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="77a44-192">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="77a44-192">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="77a44-193">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="77a44-193">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="77a44-194">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="77a44-194">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="77a44-195">测试框架</span><span class="sxs-lookup"><span data-stu-id="77a44-195">Test Framework</span></span> | <span data-ttu-id="77a44-196">支持的属性</span><span class="sxs-lookup"><span data-stu-id="77a44-196">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="77a44-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="77a44-197">MSTest</span></span>         | <ul><li><span data-ttu-id="77a44-198">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="77a44-198">FullyQualifiedName</span></span></li><li><span data-ttu-id="77a44-199">name</span><span class="sxs-lookup"><span data-stu-id="77a44-199">Name</span></span></li><li><span data-ttu-id="77a44-200">ClassName</span><span class="sxs-lookup"><span data-stu-id="77a44-200">ClassName</span></span></li><li><span data-ttu-id="77a44-201">优先级</span><span class="sxs-lookup"><span data-stu-id="77a44-201">Priority</span></span></li><li><span data-ttu-id="77a44-202">TestCategory</span><span class="sxs-lookup"><span data-stu-id="77a44-202">TestCategory</span></span></li></ul> |
| <span data-ttu-id="77a44-203">xUnit</span><span class="sxs-lookup"><span data-stu-id="77a44-203">xUnit</span></span>          | <ul><li><span data-ttu-id="77a44-204">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="77a44-204">FullyQualifiedName</span></span></li><li><span data-ttu-id="77a44-205">DisplayName</span><span class="sxs-lookup"><span data-stu-id="77a44-205">DisplayName</span></span></li><li><span data-ttu-id="77a44-206">特征</span><span class="sxs-lookup"><span data-stu-id="77a44-206">Traits</span></span></li></ul>                                   |

<span data-ttu-id="77a44-207">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="77a44-207">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="77a44-208">运算符</span><span class="sxs-lookup"><span data-stu-id="77a44-208">Operator</span></span> | <span data-ttu-id="77a44-209">函数</span><span class="sxs-lookup"><span data-stu-id="77a44-209">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="77a44-210">完全匹配</span><span class="sxs-lookup"><span data-stu-id="77a44-210">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="77a44-211">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="77a44-211">Not exact match</span></span> |
| `~`      | <span data-ttu-id="77a44-212">包含</span><span class="sxs-lookup"><span data-stu-id="77a44-212">Contains</span></span>        |

<span data-ttu-id="77a44-213">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="77a44-213">`<value>` is a string.</span></span> <span data-ttu-id="77a44-214">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="77a44-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="77a44-215">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="77a44-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="77a44-216">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="77a44-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="77a44-217">运算符</span><span class="sxs-lookup"><span data-stu-id="77a44-217">Operator</span></span>            | <span data-ttu-id="77a44-218">函数</span><span class="sxs-lookup"><span data-stu-id="77a44-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="77a44-219">或</span><span class="sxs-lookup"><span data-stu-id="77a44-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="77a44-220">AND</span><span class="sxs-lookup"><span data-stu-id="77a44-220">AND</span></span>      |

<span data-ttu-id="77a44-221">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="77a44-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="77a44-222">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="77a44-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77a44-223">请参阅</span><span class="sxs-lookup"><span data-stu-id="77a44-223">See also</span></span>

* [<span data-ttu-id="77a44-224">框架和目标</span><span class="sxs-lookup"><span data-stu-id="77a44-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="77a44-225">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="77a44-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
