---
title: dotnet test 命令
description: dotnet test 命令可用于在给定项目中执行单元测试。
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624886"
---
# <a name="dotnet-test"></a><span data-ttu-id="cc02c-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="cc02c-103">dotnet test</span></span>

<span data-ttu-id="cc02c-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="cc02c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cc02c-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="cc02c-105">Name</span></span>

<span data-ttu-id="cc02c-106">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="cc02c-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cc02c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="cc02c-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="cc02c-108">描述</span><span class="sxs-lookup"><span data-stu-id="cc02c-108">Description</span></span>

<span data-ttu-id="cc02c-109">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="cc02c-110">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc02c-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="cc02c-111">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="cc02c-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="cc02c-112">如果所有测试均成功，测试运行程序将返回 0 作为退出代码；否则将返回 1。</span><span class="sxs-lookup"><span data-stu-id="cc02c-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="cc02c-113">对于多目标项目，将为每个目标框架运行测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="cc02c-114">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="cc02c-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="cc02c-115">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="cc02c-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="cc02c-116">隐式还原</span><span class="sxs-lookup"><span data-stu-id="cc02c-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="cc02c-117">自变量</span><span class="sxs-lookup"><span data-stu-id="cc02c-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="cc02c-118">测试项目或解决方案的路径。</span><span class="sxs-lookup"><span data-stu-id="cc02c-118">Path to the test project or solution.</span></span> <span data-ttu-id="cc02c-119">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="cc02c-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="cc02c-120">选项</span><span class="sxs-lookup"><span data-stu-id="cc02c-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="cc02c-121">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="cc02c-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="cc02c-122">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="cc02c-123">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="cc02c-124">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。</span><span class="sxs-lookup"><span data-stu-id="cc02c-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="cc02c-125">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="cc02c-125">Defines the build configuration.</span></span> <span data-ttu-id="cc02c-126">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="cc02c-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="cc02c-127">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="cc02c-127">Enables data collector for the test run.</span></span> <span data-ttu-id="cc02c-128">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="cc02c-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="cc02c-129">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="cc02c-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="cc02c-130">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="cc02c-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="cc02c-131">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cc02c-132">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="cc02c-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cc02c-133">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="cc02c-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="cc02c-134">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cc02c-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="cc02c-135">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="cc02c-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="cc02c-136">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc02c-136">For example, to complete authentication.</span></span> <span data-ttu-id="cc02c-137">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="cc02c-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="cc02c-138">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="cc02c-138">Specifies a logger for test results.</span></span> <span data-ttu-id="cc02c-139">与 MSBuild 不同，dotnet 测试不接受缩写，应使用 `-l "console;verbosity=detailed"`，而不使用 `-l "console;v=d"`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="cc02c-140">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="cc02c-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="cc02c-141">还将隐式设置 - `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="cc02c-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="cc02c-142">运行测试，而不显示 Microsoft TestPlatform 横幅。</span><span class="sxs-lookup"><span data-stu-id="cc02c-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="cc02c-143">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="cc02c-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="cc02c-144">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="cc02c-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="cc02c-145">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="cc02c-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="cc02c-146">如果未指定，则默认路径为 `./bin/<configuration>/<framework>/`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="cc02c-147">对于具有多个目标框架的项目（通过 `TargetFrameworks` 属性），在指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="cc02c-148">`dotnet test` 始终从输出目录运行测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="cc02c-149">可以使用 <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> 以使用输出目录中的测试资产。</span><span class="sxs-lookup"><span data-stu-id="cc02c-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="cc02c-150">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="cc02c-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="cc02c-151">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="cc02c-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="cc02c-152">默认值为包含项目文件的目录中的 `TestResults`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="cc02c-153">要针对其测试的目标运行时。</span><span class="sxs-lookup"><span data-stu-id="cc02c-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="cc02c-154">`.runsettings` 文件用于运行测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="cc02c-155">请注意，`TargetPlatform` 元素 (x86|x64) 对 `dotnet test` 不起作用。</span><span class="sxs-lookup"><span data-stu-id="cc02c-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="cc02c-156">若要运行面向 x86 的测试，请安装 .NET Core 的 x86 版本。</span><span class="sxs-lookup"><span data-stu-id="cc02c-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="cc02c-157">路径上 dotnet.exe 的位数是用于运行测试的内容  。</span><span class="sxs-lookup"><span data-stu-id="cc02c-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="cc02c-158">有关更多信息，请参见以下资源：</span><span class="sxs-lookup"><span data-stu-id="cc02c-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="cc02c-159">使用 `.runsettings` 文件配置单元测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="cc02c-160">配置测试运行</span><span class="sxs-lookup"><span data-stu-id="cc02c-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="cc02c-161">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="cc02c-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="cc02c-162">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="cc02c-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cc02c-163">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cc02c-164">默认值为 `minimal`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-164">The default is `minimal`.</span></span> <span data-ttu-id="cc02c-165">有关详细信息，请参阅 <xref:Microsoft.Build.Framework.LoggerVerbosity>。</span><span class="sxs-lookup"><span data-stu-id="cc02c-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="cc02c-166">`RunSettings` 参数</span><span class="sxs-lookup"><span data-stu-id="cc02c-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="cc02c-167">参数在测试中作为 `RunSettings` 配置传递。</span><span class="sxs-lookup"><span data-stu-id="cc02c-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="cc02c-168">参数在“-- ”（注意 -- 后的空格）后被指定为 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="cc02c-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="cc02c-169">空格用于分隔多个 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="cc02c-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="cc02c-170">示例：`dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="cc02c-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="cc02c-171">有关详细信息，请参阅[通过命令行传递 RunSettings 参数](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)。</span><span class="sxs-lookup"><span data-stu-id="cc02c-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="cc02c-172">示例</span><span class="sxs-lookup"><span data-stu-id="cc02c-172">Examples</span></span>

- <span data-ttu-id="cc02c-173">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="cc02c-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="cc02c-174">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="cc02c-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="cc02c-175">在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：</span><span class="sxs-lookup"><span data-stu-id="cc02c-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="cc02c-176">在当前目录中运行项目中的测试，并将详细的测试结果记录到控制台：</span><span class="sxs-lookup"><span data-stu-id="cc02c-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="cc02c-177">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="cc02c-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cc02c-178">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="cc02c-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="cc02c-179">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="cc02c-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="cc02c-180">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="cc02c-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="cc02c-181">测试框架</span><span class="sxs-lookup"><span data-stu-id="cc02c-181">Test Framework</span></span> | <span data-ttu-id="cc02c-182">支持的属性</span><span class="sxs-lookup"><span data-stu-id="cc02c-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cc02c-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="cc02c-183">MSTest</span></span>         | <ul><li><span data-ttu-id="cc02c-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cc02c-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="cc02c-185">“属性”</span><span class="sxs-lookup"><span data-stu-id="cc02c-185">Name</span></span></li><li><span data-ttu-id="cc02c-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="cc02c-186">ClassName</span></span></li><li><span data-ttu-id="cc02c-187">Priority</span><span class="sxs-lookup"><span data-stu-id="cc02c-187">Priority</span></span></li><li><span data-ttu-id="cc02c-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="cc02c-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="cc02c-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="cc02c-189">xUnit</span></span>          | <ul><li><span data-ttu-id="cc02c-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cc02c-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="cc02c-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cc02c-191">DisplayName</span></span></li><li><span data-ttu-id="cc02c-192">Traits</span><span class="sxs-lookup"><span data-stu-id="cc02c-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="cc02c-193">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="cc02c-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="cc02c-194">运算符</span><span class="sxs-lookup"><span data-stu-id="cc02c-194">Operator</span></span> | <span data-ttu-id="cc02c-195">函数</span><span class="sxs-lookup"><span data-stu-id="cc02c-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="cc02c-196">完全匹配</span><span class="sxs-lookup"><span data-stu-id="cc02c-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="cc02c-197">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="cc02c-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="cc02c-198">包含</span><span class="sxs-lookup"><span data-stu-id="cc02c-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="cc02c-199">不包含</span><span class="sxs-lookup"><span data-stu-id="cc02c-199">Not contains</span></span>    |

<span data-ttu-id="cc02c-200">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="cc02c-200">`<value>` is a string.</span></span> <span data-ttu-id="cc02c-201">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cc02c-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="cc02c-202">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="cc02c-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="cc02c-203">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="cc02c-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="cc02c-204">运算符</span><span class="sxs-lookup"><span data-stu-id="cc02c-204">Operator</span></span>            | <span data-ttu-id="cc02c-205">函数</span><span class="sxs-lookup"><span data-stu-id="cc02c-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="cc02c-206">或</span><span class="sxs-lookup"><span data-stu-id="cc02c-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="cc02c-207">AND</span><span class="sxs-lookup"><span data-stu-id="cc02c-207">AND</span></span>      |

<span data-ttu-id="cc02c-208">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="cc02c-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="cc02c-209">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="cc02c-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc02c-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc02c-210">See also</span></span>

- [<span data-ttu-id="cc02c-211">框架和目标</span><span class="sxs-lookup"><span data-stu-id="cc02c-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="cc02c-212">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="cc02c-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="cc02c-213">通过命令行传递 runsettings 参数</span><span class="sxs-lookup"><span data-stu-id="cc02c-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
