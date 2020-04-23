---
title: dotnet vstest 命令
description: dotnet vstest 命令可生成项目及其所有依赖项。
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463284"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="d6f86-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="d6f86-103">dotnet vstest</span></span>

<span data-ttu-id="d6f86-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d6f86-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d6f86-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="d6f86-105">Name</span></span>

<span data-ttu-id="d6f86-106">`dotnet-vstest` - 从指定文件运行测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d6f86-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d6f86-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="d6f86-108">描述</span><span class="sxs-lookup"><span data-stu-id="d6f86-108">Description</span></span>

<span data-ttu-id="d6f86-109">`dotnet-vstest` 命令运行 `VSTest.Console` 命令行应用程序以运行自动化单元测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="d6f86-110">自变量</span><span class="sxs-lookup"><span data-stu-id="d6f86-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="d6f86-111">从指定的程序集运行测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="d6f86-112">用空格分隔多个测试程序集名称。</span><span class="sxs-lookup"><span data-stu-id="d6f86-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="d6f86-113">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="d6f86-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="d6f86-114">选项</span><span class="sxs-lookup"><span data-stu-id="d6f86-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="d6f86-115">在意见模式中运行测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="d6f86-116">此选项有助于隔离导致测试主机出现故障的有问题的测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="d6f86-117">它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。</span><span class="sxs-lookup"><span data-stu-id="d6f86-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="d6f86-118">为测试平台启用详细日志。</span><span class="sxs-lookup"><span data-stu-id="d6f86-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="d6f86-119">日志被写入到所提供的文件。</span><span class="sxs-lookup"><span data-stu-id="d6f86-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="d6f86-120">用于测试执行的目标 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="d6f86-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="d6f86-121">有效值的示例为 `.NETFramework,Version=v4.6` 或 `.NETCoreApp,Version=v1.0`。</span><span class="sxs-lookup"><span data-stu-id="d6f86-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="d6f86-122">其他支持的值为 `Framework40`、`Framework45`、`FrameworkCore10` 和 `FrameworkUap10`。</span><span class="sxs-lookup"><span data-stu-id="d6f86-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="d6f86-123">在隔离的进程中运行测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="d6f86-124">虽然这使得 vstest.console.exe 进程不太可能在测试出错时停止，但测试的运行速度会较慢  。</span><span class="sxs-lookup"><span data-stu-id="d6f86-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="d6f86-125">列出给定测试容器中所有已发现的测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="d6f86-126">为测试结果指定一个记录器。</span><span class="sxs-lookup"><span data-stu-id="d6f86-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="d6f86-127">若要将测试结果发布到 Team Foundation Server，请使用 `TfsPublisher` 记录器提供程序：</span><span class="sxs-lookup"><span data-stu-id="d6f86-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="d6f86-128">若要将结果记录到 Visual Studio 测试结果文件 (TRX)，请使用 `trx` 记录器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d6f86-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="d6f86-129">此开关使用给定的日志文件名在测试结果目录中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="d6f86-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="d6f86-130">如果未提供 `LogFileName`，将创建唯一的文件名以保留测试结果。</span><span class="sxs-lookup"><span data-stu-id="d6f86-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="d6f86-131">并行运行测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-131">Run tests in parallel.</span></span> <span data-ttu-id="d6f86-132">默认情况下，计算机上的所有可用内核都可供使用。</span><span class="sxs-lookup"><span data-stu-id="d6f86-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="d6f86-133">通过在 runsettings 文件的 `RunConfiguration` 节点下设置 `MaxCpuCount` 属性来指定显式内核数  。</span><span class="sxs-lookup"><span data-stu-id="d6f86-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="d6f86-134">父进程的进程 ID 负责启动当前进程。</span><span class="sxs-lookup"><span data-stu-id="d6f86-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="d6f86-135">用于执行测试的目标平台体系结构。</span><span class="sxs-lookup"><span data-stu-id="d6f86-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="d6f86-136">有效值为 `x86`、`x64` 和 `ARM`。</span><span class="sxs-lookup"><span data-stu-id="d6f86-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="d6f86-137">指定套接字连接和接收事件消息的端口。</span><span class="sxs-lookup"><span data-stu-id="d6f86-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="d6f86-138">如果不存在，则将在指定路径中创建测试结果目录。</span><span class="sxs-lookup"><span data-stu-id="d6f86-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="d6f86-139">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="d6f86-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="d6f86-140">在测试运行中使用来自给定路径（如果有）的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="d6f86-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="d6f86-141">运行与给定表达式匹配的测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-141">Run tests that match the given expression.</span></span> <span data-ttu-id="d6f86-142">`<EXPRESSION>` 的格式为 `<property>Operator<value>[|&<EXPRESSION>]`，其中运算符是 `=`、`!=` 或 `~` 之一。</span><span class="sxs-lookup"><span data-stu-id="d6f86-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="d6f86-143">运算符 `~` 具有“包含”语义，并适用于字符串属性，如 `DisplayName`。</span><span class="sxs-lookup"><span data-stu-id="d6f86-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="d6f86-144">括号 `()` 用于组的子表达式。</span><span class="sxs-lookup"><span data-stu-id="d6f86-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="d6f86-145">有关详细信息，请参阅 [TestCase 筛选器](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)</span><span class="sxs-lookup"><span data-stu-id="d6f86-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="d6f86-146">运行具有与提供的值匹配的名称的测试。</span><span class="sxs-lookup"><span data-stu-id="d6f86-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="d6f86-147">用逗号分隔多个值。</span><span class="sxs-lookup"><span data-stu-id="d6f86-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="d6f86-148">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d6f86-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="d6f86-149">有关更多选项，请阅读响应文件。</span><span class="sxs-lookup"><span data-stu-id="d6f86-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="d6f86-150">指定要传递到适配器的额外参数。</span><span class="sxs-lookup"><span data-stu-id="d6f86-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="d6f86-151">参数被指定为 `<n>=<v>` 格式的名称值对，其中 `<n>` 是参数名称，`<v>` 是参数值。</span><span class="sxs-lookup"><span data-stu-id="d6f86-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="d6f86-152">使用空格分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="d6f86-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="d6f86-153">示例</span><span class="sxs-lookup"><span data-stu-id="d6f86-153">Examples</span></span>

<span data-ttu-id="d6f86-154">在 mytestproject.dll 中运行测试  ：</span><span class="sxs-lookup"><span data-stu-id="d6f86-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="d6f86-155">在 mytestproject.dll 中运行测试，并使用自定义名称导出到自定义文件夹  ：</span><span class="sxs-lookup"><span data-stu-id="d6f86-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="d6f86-156">在 mytestproject.dll 和 myothertestproject.exe 中运行测试   ：</span><span class="sxs-lookup"><span data-stu-id="d6f86-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="d6f86-157">运行 `TestMethod1` 测试：</span><span class="sxs-lookup"><span data-stu-id="d6f86-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="d6f86-158">运行 `TestMethod1` 和 `TestMethod2` 测试：</span><span class="sxs-lookup"><span data-stu-id="d6f86-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="d6f86-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6f86-159">See also</span></span>

- [<span data-ttu-id="d6f86-160">VSTest.Console.exe 命令行选项</span><span class="sxs-lookup"><span data-stu-id="d6f86-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
