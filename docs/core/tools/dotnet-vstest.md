---
title: dotnet vstest 命令
description: dotnet vstest 命令可生成项目及其所有依赖项。
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975389"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="cd295-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="cd295-103">dotnet vstest</span></span>

<span data-ttu-id="cd295-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="cd295-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd295-105">`dotnet vstest` 命令被 `dotnet test` 取代，后者现在可用于运行程序集。</span><span class="sxs-lookup"><span data-stu-id="cd295-105">The `dotnet vstest` command is superseded by `dotnet test`, which can now be used to run assemblies.</span></span> <span data-ttu-id="cd295-106">请参阅 [`dotnet test`](dotnet-test.md)。</span><span class="sxs-lookup"><span data-stu-id="cd295-106">See [`dotnet test`](dotnet-test.md).</span></span>

## <a name="name"></a><span data-ttu-id="cd295-107">“属性”</span><span class="sxs-lookup"><span data-stu-id="cd295-107">Name</span></span>

<span data-ttu-id="cd295-108">`dotnet-vstest` - 从指定的程序集运行测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-108">`dotnet-vstest` - Runs tests from the specified assemblies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cd295-109">摘要</span><span class="sxs-lookup"><span data-stu-id="cd295-109">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="cd295-110">描述</span><span class="sxs-lookup"><span data-stu-id="cd295-110">Description</span></span>

<span data-ttu-id="cd295-111">`dotnet-vstest` 命令运行 `VSTest.Console` 命令行应用程序以运行自动化单元测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="cd295-112">自变量</span><span class="sxs-lookup"><span data-stu-id="cd295-112">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="cd295-113">从指定的程序集运行测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="cd295-114">用空格分隔多个测试程序集名称。</span><span class="sxs-lookup"><span data-stu-id="cd295-114">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="cd295-115">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="cd295-115">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="cd295-116">选项</span><span class="sxs-lookup"><span data-stu-id="cd295-116">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="cd295-117">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-117">Runs the tests in blame mode.</span></span> <span data-ttu-id="cd295-118">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-118">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cd295-119">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。</span><span class="sxs-lookup"><span data-stu-id="cd295-119">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="cd295-120">为测试平台启用详细日志。</span><span class="sxs-lookup"><span data-stu-id="cd295-120">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cd295-121">日志被写入到所提供的文件。</span><span class="sxs-lookup"><span data-stu-id="cd295-121">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="cd295-122">用于测试执行的目标 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="cd295-122">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cd295-123">有效值的示例为 `.NETFramework,Version=v4.6` 或 `.NETCoreApp,Version=v1.0`。</span><span class="sxs-lookup"><span data-stu-id="cd295-123">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cd295-124">其他支持的值为 `Framework40`、`Framework45`、`FrameworkCore10` 和 `FrameworkUap10`。</span><span class="sxs-lookup"><span data-stu-id="cd295-124">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="cd295-125">在隔离的进程中运行测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-125">Runs the tests in an isolated process.</span></span> <span data-ttu-id="cd295-126">虽然这使得 vstest.console.exe 进程不太可能在测试出错时停止，但测试的运行速度会较慢  。</span><span class="sxs-lookup"><span data-stu-id="cd295-126">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="cd295-127">列出给定测试容器中所有已发现的测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-127">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="cd295-128">为测试结果指定一个记录器。</span><span class="sxs-lookup"><span data-stu-id="cd295-128">Specify a logger for test results.</span></span>

  - <span data-ttu-id="cd295-129">若要将测试结果发布到 Team Foundation Server，请使用 `TfsPublisher` 记录器提供程序：</span><span class="sxs-lookup"><span data-stu-id="cd295-129">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="cd295-130">若要将结果记录到 Visual Studio 测试结果文件 (TRX)，请使用 `trx` 记录器提供程序。</span><span class="sxs-lookup"><span data-stu-id="cd295-130">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cd295-131">此开关使用给定的日志文件名在测试结果目录中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="cd295-131">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cd295-132">如果未提供 `LogFileName`，将创建唯一的文件名以保留测试结果。</span><span class="sxs-lookup"><span data-stu-id="cd295-132">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="cd295-133">并行运行测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-133">Run tests in parallel.</span></span> <span data-ttu-id="cd295-134">默认情况下，计算机上的所有可用内核都可供使用。</span><span class="sxs-lookup"><span data-stu-id="cd295-134">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cd295-135">通过在 runsettings 文件的 `RunConfiguration` 节点下设置 `MaxCpuCount` 属性来指定显式内核数  。</span><span class="sxs-lookup"><span data-stu-id="cd295-135">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="cd295-136">父进程的进程 ID 负责启动当前进程。</span><span class="sxs-lookup"><span data-stu-id="cd295-136">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="cd295-137">用于执行测试的目标平台体系结构。</span><span class="sxs-lookup"><span data-stu-id="cd295-137">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cd295-138">有效值为 `x86`、`x64` 和 `ARM`。</span><span class="sxs-lookup"><span data-stu-id="cd295-138">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="cd295-139">指定套接字连接和接收事件消息的端口。</span><span class="sxs-lookup"><span data-stu-id="cd295-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="cd295-140">如果不存在，则将在指定路径中创建测试结果目录。</span><span class="sxs-lookup"><span data-stu-id="cd295-140">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="cd295-141">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="cd295-141">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="cd295-142">在测试运行中使用来自给定路径（如果有）的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="cd295-142">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="cd295-143">运行与给定表达式匹配的测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-143">Run tests that match the given expression.</span></span> <span data-ttu-id="cd295-144">`<EXPRESSION>` 的格式为 `<property>Operator<value>[|&<EXPRESSION>]`，其中运算符是 `=`、`!=` 或 `~` 之一。</span><span class="sxs-lookup"><span data-stu-id="cd295-144">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cd295-145">运算符 `~` 具有“包含”语义，并适用于字符串属性，如 `DisplayName`。</span><span class="sxs-lookup"><span data-stu-id="cd295-145">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cd295-146">括号 `()` 用于组的子表达式。</span><span class="sxs-lookup"><span data-stu-id="cd295-146">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="cd295-147">有关详细信息，请参阅 [TestCase 筛选器](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)</span><span class="sxs-lookup"><span data-stu-id="cd295-147">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="cd295-148">运行具有与提供的值匹配的名称的测试。</span><span class="sxs-lookup"><span data-stu-id="cd295-148">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cd295-149">用逗号分隔多个值。</span><span class="sxs-lookup"><span data-stu-id="cd295-149">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="cd295-150">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cd295-150">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="cd295-151">有关更多选项，请阅读响应文件。</span><span class="sxs-lookup"><span data-stu-id="cd295-151">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="cd295-152">指定要传递到适配器的额外参数。</span><span class="sxs-lookup"><span data-stu-id="cd295-152">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cd295-153">参数被指定为 `<n>=<v>` 格式的名称值对，其中 `<n>` 是参数名称，`<v>` 是参数值。</span><span class="sxs-lookup"><span data-stu-id="cd295-153">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cd295-154">使用空格分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="cd295-154">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="cd295-155">示例</span><span class="sxs-lookup"><span data-stu-id="cd295-155">Examples</span></span>

<span data-ttu-id="cd295-156">在 mytestproject.dll 中运行测试  ：</span><span class="sxs-lookup"><span data-stu-id="cd295-156">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="cd295-157">在 mytestproject.dll 中运行测试，并使用自定义名称导出到自定义文件夹  ：</span><span class="sxs-lookup"><span data-stu-id="cd295-157">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="cd295-158">在 mytestproject.dll 和 myothertestproject.exe 中运行测试   ：</span><span class="sxs-lookup"><span data-stu-id="cd295-158">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="cd295-159">运行 `TestMethod1` 测试：</span><span class="sxs-lookup"><span data-stu-id="cd295-159">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="cd295-160">运行 `TestMethod1` 和 `TestMethod2` 测试：</span><span class="sxs-lookup"><span data-stu-id="cd295-160">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="cd295-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd295-161">See also</span></span>

- [<span data-ttu-id="cd295-162">VSTest.Console.exe 命令行选项</span><span class="sxs-lookup"><span data-stu-id="cd295-162">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
