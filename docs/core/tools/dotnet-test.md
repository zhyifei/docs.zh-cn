---
title: dotnet test 命令 - .NET Core CLI
description: dotnet test 命令可用于在给定项目中执行单元测试。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 7946196b27489870da1c16b15cbf5f078ae89c61
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666897"
---
# <a name="dotnet-test"></a><span data-ttu-id="ea3cc-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ea3cc-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ea3cc-104">name</span><span class="sxs-lookup"><span data-stu-id="ea3cc-104">Name</span></span>

<span data-ttu-id="ea3cc-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ea3cc-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ea3cc-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ea3cc-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ea3cc-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ea3cc-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ea3cc-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ea3cc-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ea3cc-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ea3cc-110">描述</span><span class="sxs-lookup"><span data-stu-id="ea3cc-110">Description</span></span>

<span data-ttu-id="ea3cc-111">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="ea3cc-112">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="ea3cc-113">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="ea3cc-114">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="ea3cc-115">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="ea3cc-116">自变量</span><span class="sxs-lookup"><span data-stu-id="ea3cc-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ea3cc-117">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-117">Path to the test project.</span></span> <span data-ttu-id="ea3cc-118">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="ea3cc-119">选项</span><span class="sxs-lookup"><span data-stu-id="ea3cc-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ea3cc-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ea3cc-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ea3cc-121">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="ea3cc-122">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="ea3cc-123">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="ea3cc-124">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ea3cc-125">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-125">Defines the build configuration.</span></span> <span data-ttu-id="ea3cc-126">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ea3cc-127">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-127">Enables data collector for the test run.</span></span> <span data-ttu-id="ea3cc-128">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ea3cc-129">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ea3cc-130">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ea3cc-131">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ea3cc-132">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ea3cc-133">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ea3cc-134">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ea3cc-135">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ea3cc-136">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ea3cc-137">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ea3cc-138">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ea3cc-139">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ea3cc-140">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ea3cc-141">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ea3cc-142">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ea3cc-143">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ea3cc-144">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ea3cc-145">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ea3cc-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ea3cc-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ea3cc-147">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ea3cc-148">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-148">Defines the build configuration.</span></span> <span data-ttu-id="ea3cc-149">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ea3cc-150">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-150">Enables data collector for the test run.</span></span> <span data-ttu-id="ea3cc-151">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ea3cc-152">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ea3cc-153">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ea3cc-154">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ea3cc-155">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ea3cc-156">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ea3cc-157">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ea3cc-158">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ea3cc-159">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ea3cc-160">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ea3cc-161">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ea3cc-162">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ea3cc-163">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ea3cc-164">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ea3cc-165">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ea3cc-166">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ea3cc-167">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ea3cc-168">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ea3cc-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ea3cc-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ea3cc-170">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ea3cc-171">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-171">Defines the build configuration.</span></span> <span data-ttu-id="ea3cc-172">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ea3cc-173">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ea3cc-174">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ea3cc-175">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ea3cc-176">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ea3cc-177">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ea3cc-178">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ea3cc-179">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ea3cc-180">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ea3cc-181">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ea3cc-182">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ea3cc-183">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ea3cc-184">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ea3cc-185">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ea3cc-186">示例</span><span class="sxs-lookup"><span data-stu-id="ea3cc-186">Examples</span></span>

<span data-ttu-id="ea3cc-187">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="ea3cc-188">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="ea3cc-189">在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-189">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="ea3cc-190">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="ea3cc-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ea3cc-191">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="ea3cc-192">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="ea3cc-193">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="ea3cc-194">测试框架</span><span class="sxs-lookup"><span data-stu-id="ea3cc-194">Test Framework</span></span> | <span data-ttu-id="ea3cc-195">支持的属性</span><span class="sxs-lookup"><span data-stu-id="ea3cc-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ea3cc-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="ea3cc-196">MSTest</span></span>         | <ul><li><span data-ttu-id="ea3cc-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ea3cc-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="ea3cc-198">name</span><span class="sxs-lookup"><span data-stu-id="ea3cc-198">Name</span></span></li><li><span data-ttu-id="ea3cc-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="ea3cc-199">ClassName</span></span></li><li><span data-ttu-id="ea3cc-200">优先级</span><span class="sxs-lookup"><span data-stu-id="ea3cc-200">Priority</span></span></li><li><span data-ttu-id="ea3cc-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="ea3cc-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="ea3cc-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="ea3cc-202">xUnit</span></span>          | <ul><li><span data-ttu-id="ea3cc-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ea3cc-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="ea3cc-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ea3cc-204">DisplayName</span></span></li><li><span data-ttu-id="ea3cc-205">特征</span><span class="sxs-lookup"><span data-stu-id="ea3cc-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="ea3cc-206">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="ea3cc-207">运算符</span><span class="sxs-lookup"><span data-stu-id="ea3cc-207">Operator</span></span> | <span data-ttu-id="ea3cc-208">函数</span><span class="sxs-lookup"><span data-stu-id="ea3cc-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="ea3cc-209">完全匹配</span><span class="sxs-lookup"><span data-stu-id="ea3cc-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="ea3cc-210">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="ea3cc-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="ea3cc-211">包含</span><span class="sxs-lookup"><span data-stu-id="ea3cc-211">Contains</span></span>        |

<span data-ttu-id="ea3cc-212">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-212">`<value>` is a string.</span></span> <span data-ttu-id="ea3cc-213">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-213">All the lookups are case insensitive.</span></span>

<span data-ttu-id="ea3cc-214">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-214">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="ea3cc-215">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="ea3cc-215">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="ea3cc-216">运算符</span><span class="sxs-lookup"><span data-stu-id="ea3cc-216">Operator</span></span>            | <span data-ttu-id="ea3cc-217">函数</span><span class="sxs-lookup"><span data-stu-id="ea3cc-217">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="ea3cc-218">或</span><span class="sxs-lookup"><span data-stu-id="ea3cc-218">OR</span></span>       |
| `&`                 | <span data-ttu-id="ea3cc-219">AND</span><span class="sxs-lookup"><span data-stu-id="ea3cc-219">AND</span></span>      |

<span data-ttu-id="ea3cc-220">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-220">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="ea3cc-221">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-221">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea3cc-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea3cc-222">See also</span></span>

* [<span data-ttu-id="ea3cc-223">框架和目标</span><span class="sxs-lookup"><span data-stu-id="ea3cc-223">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="ea3cc-224">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="ea3cc-224">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
