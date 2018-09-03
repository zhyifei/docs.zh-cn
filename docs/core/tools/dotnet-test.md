---
title: dotnet test 命令 - .NET Core CLI
description: dotnet test 命令可用于在给定项目中执行单元测试。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 2bee78ca44026f28c51fac3bcf87d976b53e48a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390685"
---
# <a name="dotnet-test"></a><span data-ttu-id="1a386-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1a386-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1a386-104">name</span><span class="sxs-lookup"><span data-stu-id="1a386-104">Name</span></span>

<span data-ttu-id="1a386-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1a386-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1a386-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1a386-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1a386-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1a386-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1a386-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1a386-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1a386-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1a386-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="1a386-110">描述</span><span class="sxs-lookup"><span data-stu-id="1a386-110">Description</span></span>

<span data-ttu-id="1a386-111">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="1a386-112">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a386-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="1a386-113">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="1a386-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="1a386-114">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="1a386-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="1a386-115">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="1a386-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="1a386-116">自变量</span><span class="sxs-lookup"><span data-stu-id="1a386-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1a386-117">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="1a386-117">Path to the test project.</span></span> <span data-ttu-id="1a386-118">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1a386-119">选项</span><span class="sxs-lookup"><span data-stu-id="1a386-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1a386-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1a386-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1a386-121">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="1a386-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="1a386-122">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="1a386-123">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="1a386-124">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序。</span><span class="sxs-lookup"><span data-stu-id="1a386-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1a386-125">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="1a386-125">Defines the build configuration.</span></span> <span data-ttu-id="1a386-126">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="1a386-127">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="1a386-127">Enables data collector for the test run.</span></span> <span data-ttu-id="1a386-128">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="1a386-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1a386-129">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1a386-130">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1a386-131">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1a386-132">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="1a386-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1a386-133">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="1a386-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1a386-134">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1a386-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1a386-135">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="1a386-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1a386-136">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="1a386-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1a386-137">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="1a386-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="1a386-138">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1a386-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1a386-139">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="1a386-140">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1a386-141">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1a386-142">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="1a386-143">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1a386-144">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="1a386-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1a386-145">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1a386-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1a386-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1a386-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1a386-147">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="1a386-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1a386-148">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="1a386-148">Defines the build configuration.</span></span> <span data-ttu-id="1a386-149">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="1a386-150">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="1a386-150">Enables data collector for the test run.</span></span> <span data-ttu-id="1a386-151">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="1a386-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1a386-152">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1a386-153">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1a386-154">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1a386-155">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="1a386-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1a386-156">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="1a386-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1a386-157">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1a386-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1a386-158">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="1a386-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1a386-159">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="1a386-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1a386-160">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="1a386-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="1a386-161">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1a386-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1a386-162">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="1a386-163">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1a386-164">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1a386-165">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="1a386-166">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1a386-167">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="1a386-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1a386-168">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1a386-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1a386-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1a386-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1a386-170">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="1a386-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1a386-171">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="1a386-171">Defines the build configuration.</span></span> <span data-ttu-id="1a386-172">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1a386-173">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1a386-174">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="1a386-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1a386-175">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1a386-176">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="1a386-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1a386-177">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="1a386-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1a386-178">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1a386-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1a386-179">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="1a386-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1a386-180">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="1a386-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1a386-181">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="1a386-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1a386-182">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="1a386-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="1a386-183">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="1a386-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1a386-184">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="1a386-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1a386-185">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1a386-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="1a386-186">示例</span><span class="sxs-lookup"><span data-stu-id="1a386-186">Examples</span></span>

<span data-ttu-id="1a386-187">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="1a386-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="1a386-188">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="1a386-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="1a386-189">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="1a386-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1a386-190">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="1a386-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="1a386-191">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="1a386-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="1a386-192">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="1a386-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="1a386-193">测试框架</span><span class="sxs-lookup"><span data-stu-id="1a386-193">Test Framework</span></span> | <span data-ttu-id="1a386-194">支持的属性</span><span class="sxs-lookup"><span data-stu-id="1a386-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1a386-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="1a386-195">MSTest</span></span>         | <ul><li><span data-ttu-id="1a386-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1a386-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="1a386-197">name</span><span class="sxs-lookup"><span data-stu-id="1a386-197">Name</span></span></li><li><span data-ttu-id="1a386-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="1a386-198">ClassName</span></span></li><li><span data-ttu-id="1a386-199">优先级</span><span class="sxs-lookup"><span data-stu-id="1a386-199">Priority</span></span></li><li><span data-ttu-id="1a386-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="1a386-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="1a386-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="1a386-201">xUnit</span></span>          | <ul><li><span data-ttu-id="1a386-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1a386-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="1a386-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1a386-203">DisplayName</span></span></li><li><span data-ttu-id="1a386-204">特征</span><span class="sxs-lookup"><span data-stu-id="1a386-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="1a386-205">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="1a386-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="1a386-206">运算符</span><span class="sxs-lookup"><span data-stu-id="1a386-206">Operator</span></span> | <span data-ttu-id="1a386-207">函数</span><span class="sxs-lookup"><span data-stu-id="1a386-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="1a386-208">完全匹配</span><span class="sxs-lookup"><span data-stu-id="1a386-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="1a386-209">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="1a386-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="1a386-210">包含</span><span class="sxs-lookup"><span data-stu-id="1a386-210">Contains</span></span>        |

<span data-ttu-id="1a386-211">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="1a386-211">`<value>` is a string.</span></span> <span data-ttu-id="1a386-212">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1a386-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="1a386-213">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="1a386-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="1a386-214">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="1a386-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="1a386-215">运算符</span><span class="sxs-lookup"><span data-stu-id="1a386-215">Operator</span></span>            | <span data-ttu-id="1a386-216">函数</span><span class="sxs-lookup"><span data-stu-id="1a386-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="1a386-217">或</span><span class="sxs-lookup"><span data-stu-id="1a386-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="1a386-218">AND</span><span class="sxs-lookup"><span data-stu-id="1a386-218">AND</span></span>      |

<span data-ttu-id="1a386-219">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="1a386-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="1a386-220">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="1a386-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a386-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a386-221">See also</span></span>

* [<span data-ttu-id="1a386-222">框架和目标</span><span class="sxs-lookup"><span data-stu-id="1a386-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="1a386-223">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="1a386-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
