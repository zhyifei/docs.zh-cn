---
title: dotnet test 命令
description: dotnet test 命令可用于在给定项目中执行单元测试。
ms.date: 05/29/2018
ms.openlocfilehash: 6b67273f549edd7712237756a5aba13d5cb59a61
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410357"
---
# <a name="dotnet-test"></a><span data-ttu-id="e777d-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e777d-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e777d-104">name</span><span class="sxs-lookup"><span data-stu-id="e777d-104">Name</span></span>

<span data-ttu-id="e777d-105">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e777d-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e777d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e777d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e777d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e777d-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e777d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e777d-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e777d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e777d-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e777d-110">说明</span><span class="sxs-lookup"><span data-stu-id="e777d-110">Description</span></span>

<span data-ttu-id="e777d-111">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="e777d-112">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="e777d-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="e777d-113">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="e777d-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="e777d-114">如果所有测试均成功，测试运行程序将返回 0 作为退出代码；否则将返回 1。</span><span class="sxs-lookup"><span data-stu-id="e777d-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="e777d-115">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="e777d-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="e777d-116">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="e777d-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="e777d-117">自变量</span><span class="sxs-lookup"><span data-stu-id="e777d-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="e777d-118">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="e777d-118">Path to the test project.</span></span> <span data-ttu-id="e777d-119">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="e777d-120">选项</span><span class="sxs-lookup"><span data-stu-id="e777d-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e777d-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e777d-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="e777d-122">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="e777d-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="e777d-123">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="e777d-124">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="e777d-125">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。</span><span class="sxs-lookup"><span data-stu-id="e777d-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e777d-126">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="e777d-126">Defines the build configuration.</span></span> <span data-ttu-id="e777d-127">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="e777d-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="e777d-128">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="e777d-128">Enables data collector for the test run.</span></span> <span data-ttu-id="e777d-129">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="e777d-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="e777d-130">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e777d-131">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="e777d-132">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="e777d-133">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="e777d-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="e777d-134">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="e777d-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="e777d-135">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="e777d-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="e777d-136">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="e777d-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="e777d-137">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="e777d-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="e777d-138">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="e777d-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="e777d-139">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="e777d-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e777d-140">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="e777d-141">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="e777d-142">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="e777d-143">`.runsettings` 文件用于运行测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="e777d-144">使用 `.runsettings` 文件配置单元测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="e777d-145">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e777d-146">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="e777d-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e777d-147">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="e777d-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="e777d-148">作为测试的 RunSettings 配置传递的参数。</span><span class="sxs-lookup"><span data-stu-id="e777d-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="e777d-149">参数在“-- ”（注意 -- 后的空格）后被指定为 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="e777d-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="e777d-150">空格用于分隔多个 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="e777d-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="e777d-151">示例：`dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="e777d-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="e777d-152">有关 RunSettings 的详细信息，请参阅 [vstest.console.exe：传递 RunSettings 参数](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)。</span><span class="sxs-lookup"><span data-stu-id="e777d-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e777d-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e777d-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="e777d-154">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="e777d-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e777d-155">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="e777d-155">Defines the build configuration.</span></span> <span data-ttu-id="e777d-156">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="e777d-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="e777d-157">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="e777d-157">Enables data collector for the test run.</span></span> <span data-ttu-id="e777d-158">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="e777d-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="e777d-159">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e777d-160">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="e777d-161">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="e777d-162">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="e777d-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="e777d-163">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="e777d-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="e777d-164">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="e777d-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="e777d-165">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="e777d-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="e777d-166">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="e777d-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="e777d-167">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="e777d-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="e777d-168">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="e777d-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e777d-169">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="e777d-170">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="e777d-171">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="e777d-172">`.runsettings` 文件用于运行测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="e777d-173">使用 `.runsettings` 文件配置单元测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="e777d-174">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e777d-175">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="e777d-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e777d-176">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="e777d-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e777d-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e777d-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="e777d-178">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="e777d-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e777d-179">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="e777d-179">Defines the build configuration.</span></span> <span data-ttu-id="e777d-180">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="e777d-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="e777d-181">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e777d-182">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="e777d-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="e777d-183">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="e777d-184">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="e777d-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="e777d-185">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="e777d-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="e777d-186">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="e777d-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="e777d-187">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="e777d-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="e777d-188">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="e777d-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e777d-189">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="e777d-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="e777d-190">`.runsettings` 文件用于运行测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="e777d-191">使用 `.runsettings` 文件配置单元测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="e777d-192">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="e777d-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e777d-193">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="e777d-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e777d-194">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="e777d-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e777d-195">示例</span><span class="sxs-lookup"><span data-stu-id="e777d-195">Examples</span></span>

<span data-ttu-id="e777d-196">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="e777d-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="e777d-197">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="e777d-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="e777d-198">在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：</span><span class="sxs-lookup"><span data-stu-id="e777d-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="e777d-199">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="e777d-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="e777d-200">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="e777d-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="e777d-201">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="e777d-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="e777d-202">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="e777d-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="e777d-203">测试框架</span><span class="sxs-lookup"><span data-stu-id="e777d-203">Test Framework</span></span> | <span data-ttu-id="e777d-204">支持的属性</span><span class="sxs-lookup"><span data-stu-id="e777d-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="e777d-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="e777d-205">MSTest</span></span>         | <ul><li><span data-ttu-id="e777d-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="e777d-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="e777d-207">name</span><span class="sxs-lookup"><span data-stu-id="e777d-207">Name</span></span></li><li><span data-ttu-id="e777d-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="e777d-208">ClassName</span></span></li><li><span data-ttu-id="e777d-209">Priority</span><span class="sxs-lookup"><span data-stu-id="e777d-209">Priority</span></span></li><li><span data-ttu-id="e777d-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="e777d-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="e777d-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="e777d-211">xUnit</span></span>          | <ul><li><span data-ttu-id="e777d-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="e777d-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="e777d-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e777d-213">DisplayName</span></span></li><li><span data-ttu-id="e777d-214">Traits</span><span class="sxs-lookup"><span data-stu-id="e777d-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="e777d-215">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="e777d-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="e777d-216">运算符</span><span class="sxs-lookup"><span data-stu-id="e777d-216">Operator</span></span> | <span data-ttu-id="e777d-217">函数</span><span class="sxs-lookup"><span data-stu-id="e777d-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="e777d-218">完全匹配</span><span class="sxs-lookup"><span data-stu-id="e777d-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="e777d-219">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="e777d-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="e777d-220">包含</span><span class="sxs-lookup"><span data-stu-id="e777d-220">Contains</span></span>        |

<span data-ttu-id="e777d-221">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="e777d-221">`<value>` is a string.</span></span> <span data-ttu-id="e777d-222">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e777d-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="e777d-223">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="e777d-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="e777d-224">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="e777d-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="e777d-225">运算符</span><span class="sxs-lookup"><span data-stu-id="e777d-225">Operator</span></span>            | <span data-ttu-id="e777d-226">函数</span><span class="sxs-lookup"><span data-stu-id="e777d-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="e777d-227">或</span><span class="sxs-lookup"><span data-stu-id="e777d-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="e777d-228">AND</span><span class="sxs-lookup"><span data-stu-id="e777d-228">AND</span></span>      |

<span data-ttu-id="e777d-229">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="e777d-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="e777d-230">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="e777d-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e777d-231">请参阅</span><span class="sxs-lookup"><span data-stu-id="e777d-231">See also</span></span>

- [<span data-ttu-id="e777d-232">框架和目标</span><span class="sxs-lookup"><span data-stu-id="e777d-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="e777d-233">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="e777d-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
