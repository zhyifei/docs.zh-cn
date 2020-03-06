---
title: dotnet test 命令
description: dotnet test 命令可用于在给定项目中执行单元测试。
ms.date: 02/27/2020
ms.openlocfilehash: 6e906ab396a788905c99f50e73390b765b240efc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157005"
---
# <a name="dotnet-test"></a><span data-ttu-id="8bf7a-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="8bf7a-103">dotnet test</span></span>

<span data-ttu-id="8bf7a-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8bf7a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8bf7a-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="8bf7a-105">Name</span></span>

<span data-ttu-id="8bf7a-106">`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8bf7a-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8bf7a-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame]
    [-c|--configuration] [--collect] [-d|--diag] [-f|--framework]
    [--filter] [-l|--logger] [--no-build] [--no-restore]
    [-o|--output] [-r|--results-directory] [-s|--settings]
    [-t|--list-tests] [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8bf7a-108">描述</span><span class="sxs-lookup"><span data-stu-id="8bf7a-108">Description</span></span>

<span data-ttu-id="8bf7a-109">`dotnet test` 命令用于执行给定项目中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="8bf7a-110">`dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="8bf7a-111">测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="8bf7a-112">如果所有测试均成功，测试运行程序将返回 0 作为退出代码；否则将返回 1。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="8bf7a-113">测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="8bf7a-114">测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="8bf7a-115">自变量</span><span class="sxs-lookup"><span data-stu-id="8bf7a-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="8bf7a-116">指向测试项目的路径。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-116">Path to the test project.</span></span> <span data-ttu-id="8bf7a-117">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="8bf7a-118">选项</span><span class="sxs-lookup"><span data-stu-id="8bf7a-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="8bf7a-119">在测试运行中使用来自指定路径的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="8bf7a-120">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="8bf7a-121">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="8bf7a-122">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration {Debug|Release}`**

  <span data-ttu-id="8bf7a-123">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-123">Defines the build configuration.</span></span> <span data-ttu-id="8bf7a-124">默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="8bf7a-125">为测试运行启用数据收集器。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-125">Enables data collector for the test run.</span></span> <span data-ttu-id="8bf7a-126">有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="8bf7a-127">启用测试平台的诊断模式，并将诊断消息写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8bf7a-128">查找特定[框架](../../standard/frameworks.md)的测试二进制文件。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="8bf7a-129">使用给定表达式筛选掉当前项目中的测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="8bf7a-130">有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="8bf7a-131">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="8bf7a-132">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-132">Prints out a short help for the command.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="8bf7a-133">指定测试结果记录器。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-133">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="8bf7a-134">不在运行测试项目之前生成它。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-134">Doesn't build the test project before running it.</span></span> <span data-ttu-id="8bf7a-135">还将隐式设置 - `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-135">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8bf7a-136">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-136">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8bf7a-137">查找要运行的二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-137">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="8bf7a-138">用于放置测试结果的目录。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-138">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="8bf7a-139">如果指定的目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-139">If the specified directory doesn't exist, it's created.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="8bf7a-140">`.runsettings` 文件用于运行测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-140">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="8bf7a-141">使用 `.runsettings` 文件配置单元测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-141">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="8bf7a-142">列出当前项目中发现的所有测试。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-142">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8bf7a-143">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8bf7a-144">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="8bf7a-145">`RunSettings` 参数</span><span class="sxs-lookup"><span data-stu-id="8bf7a-145">`RunSettings` arguments</span></span>

  <span data-ttu-id="8bf7a-146">参数在测试中作为 `RunSettings` 配置传递。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-146">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="8bf7a-147">参数在“-- ”（注意 -- 后的空格）后被指定为 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-147">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="8bf7a-148">空格用于分隔多个 `[name]=[value]` 对。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-148">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="8bf7a-149">示例：`dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="8bf7a-149">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="8bf7a-150">有关详细信息，请参阅 [vstest.console.exe：传递 RunSettings 参数](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-150">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="8bf7a-151">示例</span><span class="sxs-lookup"><span data-stu-id="8bf7a-151">Examples</span></span>

- <span data-ttu-id="8bf7a-152">运行当前目录所含项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-152">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="8bf7a-153">运行 `test1` 项目中的测试：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-153">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="8bf7a-154">在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-154">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="8bf7a-155">筛选选项详细信息</span><span class="sxs-lookup"><span data-stu-id="8bf7a-155">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="8bf7a-156">`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-156">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="8bf7a-157">`<property>` 是 `Test Case` 的特性。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-157">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="8bf7a-158">下面介绍了常用单元测试框架支持的属性：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-158">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="8bf7a-159">测试框架</span><span class="sxs-lookup"><span data-stu-id="8bf7a-159">Test Framework</span></span> | <span data-ttu-id="8bf7a-160">支持的属性</span><span class="sxs-lookup"><span data-stu-id="8bf7a-160">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8bf7a-161">MSTest</span><span class="sxs-lookup"><span data-stu-id="8bf7a-161">MSTest</span></span>         | <ul><li><span data-ttu-id="8bf7a-162">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8bf7a-162">FullyQualifiedName</span></span></li><li><span data-ttu-id="8bf7a-163">“属性”</span><span class="sxs-lookup"><span data-stu-id="8bf7a-163">Name</span></span></li><li><span data-ttu-id="8bf7a-164">ClassName</span><span class="sxs-lookup"><span data-stu-id="8bf7a-164">ClassName</span></span></li><li><span data-ttu-id="8bf7a-165">Priority</span><span class="sxs-lookup"><span data-stu-id="8bf7a-165">Priority</span></span></li><li><span data-ttu-id="8bf7a-166">TestCategory</span><span class="sxs-lookup"><span data-stu-id="8bf7a-166">TestCategory</span></span></li></ul> |
| <span data-ttu-id="8bf7a-167">xUnit</span><span class="sxs-lookup"><span data-stu-id="8bf7a-167">xUnit</span></span>          | <ul><li><span data-ttu-id="8bf7a-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8bf7a-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="8bf7a-169">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8bf7a-169">DisplayName</span></span></li><li><span data-ttu-id="8bf7a-170">Traits</span><span class="sxs-lookup"><span data-stu-id="8bf7a-170">Traits</span></span></li></ul>                                   |

<span data-ttu-id="8bf7a-171">`<operator>` 说明了属性和值之间的关系：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-171">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="8bf7a-172">运算符</span><span class="sxs-lookup"><span data-stu-id="8bf7a-172">Operator</span></span> | <span data-ttu-id="8bf7a-173">函数</span><span class="sxs-lookup"><span data-stu-id="8bf7a-173">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="8bf7a-174">完全匹配</span><span class="sxs-lookup"><span data-stu-id="8bf7a-174">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="8bf7a-175">非完全匹配</span><span class="sxs-lookup"><span data-stu-id="8bf7a-175">Not exact match</span></span> |
| `~`      | <span data-ttu-id="8bf7a-176">包含</span><span class="sxs-lookup"><span data-stu-id="8bf7a-176">Contains</span></span>        |
| `!~`     | <span data-ttu-id="8bf7a-177">不包含</span><span class="sxs-lookup"><span data-stu-id="8bf7a-177">Not contains</span></span>    |

<span data-ttu-id="8bf7a-178">`<value>` 是字符串。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-178">`<value>` is a string.</span></span> <span data-ttu-id="8bf7a-179">所有查找都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-179">All the lookups are case insensitive.</span></span>

<span data-ttu-id="8bf7a-180">不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-180">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="8bf7a-181">表达式可与条件运算符结合使用：</span><span class="sxs-lookup"><span data-stu-id="8bf7a-181">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="8bf7a-182">运算符</span><span class="sxs-lookup"><span data-stu-id="8bf7a-182">Operator</span></span>            | <span data-ttu-id="8bf7a-183">函数</span><span class="sxs-lookup"><span data-stu-id="8bf7a-183">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="8bf7a-184">或</span><span class="sxs-lookup"><span data-stu-id="8bf7a-184">OR</span></span>       |
| `&`                 | <span data-ttu-id="8bf7a-185">AND</span><span class="sxs-lookup"><span data-stu-id="8bf7a-185">AND</span></span>      |

<span data-ttu-id="8bf7a-186">使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-186">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="8bf7a-187">若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf7a-187">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bf7a-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bf7a-188">See also</span></span>

- [<span data-ttu-id="8bf7a-189">框架和目标</span><span class="sxs-lookup"><span data-stu-id="8bf7a-189">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="8bf7a-190">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="8bf7a-190">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
