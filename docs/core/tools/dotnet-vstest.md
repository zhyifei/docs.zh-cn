---
title: "dotnet vstest 命令 - .NET Core CLI"
description: "dotnet vstest 命令可生成项目及其所有依赖项。"
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: c5a7ee0ba306cea641b0ff34f0b521c92bd03719
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-vstest"></a><span data-ttu-id="d5ea1-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="d5ea1-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d5ea1-104">名称</span><span class="sxs-lookup"><span data-stu-id="d5ea1-104">Name</span></span>

<span data-ttu-id="d5ea1-105">`dotnet-vstest` - 从指定文件运行测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d5ea1-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d5ea1-106">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="d5ea1-107">说明</span><span class="sxs-lookup"><span data-stu-id="d5ea1-107">Description</span></span>

<span data-ttu-id="d5ea1-108">`dotnet-vstest` 命令运行 `VSTest.Console` 命令行应用程序以运行自动化单元测试和编码的 UI 应用程序测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-108">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="d5ea1-109">参数</span><span class="sxs-lookup"><span data-stu-id="d5ea1-109">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="d5ea1-110">从指定的程序集运行测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-110">Run tests from the specified assemblies.</span></span> <span data-ttu-id="d5ea1-111">用空格分隔多个测试程序集名称。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-111">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="d5ea1-112">选项</span><span class="sxs-lookup"><span data-stu-id="d5ea1-112">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="d5ea1-113">运行测试时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-113">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="d5ea1-114">运行具有与提供的值匹配的名称的测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-114">Run tests with names that match the provided values.</span></span> <span data-ttu-id="d5ea1-115">用逗号分隔多个值。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-115">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="d5ea1-116">在测试运行中使用来自给定路径（如果有）的自定义测试适配器。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-116">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="d5ea1-117">用于执行测试的目标平台体系结构。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-117">Target platform architecture used for test execution.</span></span> <span data-ttu-id="d5ea1-118">有效值为 `x86`、`x64` 和 `ARM`。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-118">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="d5ea1-119">用于测试执行的目标 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-119">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="d5ea1-120">有效值的示例为 `.NETFramework,Version=v4.6`、`.NETCoreApp,Version=v1.0` 等。其他支持的值为 `Framework35`、`Framework40`、`Framework45` 和 `FrameworkCore10`。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-120">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="d5ea1-121">并行执行测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-121">Execute tests in parallel.</span></span> <span data-ttu-id="d5ea1-122">默认情况下，计算机上的所有可用内核都可供使用。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-122">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="d5ea1-123">使用设置文件设置显式内核数量。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-123">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="d5ea1-124">运行与给定表达式匹配的测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-124">Run tests that match the given expression.</span></span> <span data-ttu-id="d5ea1-125">`<Expression>` 的格式为 `<property>Operator<value>[|&<Expression>]`，其中运算符是 `=`、`!=` 或 `~` 之一。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-125">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="d5ea1-126">运算符 `~` 具有“包含”语义，并适用于字符串属性，如 `DisplayName`。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-126">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="d5ea1-127">括号 `()` 用于组的子表达式。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-127">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="d5ea1-128">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-128">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="d5ea1-129">为测试结果指定一个记录器。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-129">Specify a logger for test results.</span></span>  

* <span data-ttu-id="d5ea1-130">若要将测试结果发布到 Team Foundation Server，请使用 `TfsPublisher` 记录器提供程序：</span><span class="sxs-lookup"><span data-stu-id="d5ea1-130">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="d5ea1-131">若要将结果记录到 Visual Studio 测试结果文件 (TRX)，请使用 `trx` 记录器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-131">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="d5ea1-132">此开关使用给定的日志文件名在测试结果目录中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-132">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="d5ea1-133">如果未提供 `LogFileName`，将创建唯一的文件名以保留测试结果。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-133">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="d5ea1-134">列出给定测试容器中的已发现的测试。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-134">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="d5ea1-135">父进程的进程 ID 负责启动当前进程。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-135">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="d5ea1-136">指定套接字连接和接收事件消息的端口。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-136">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="d5ea1-137">为测试平台启用详细日志。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-137">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="d5ea1-138">日志被写入到所提供的文件。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-138">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="d5ea1-139">指定要传递到适配器的额外参数。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-139">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="d5ea1-140">参数被指定为 `<n>=<v>` 格式的名称值对，其中 `<n>` 是参数名称，`<v>` 是参数值。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-140">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="d5ea1-141">使用空格分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="d5ea1-141">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="d5ea1-142">示例</span><span class="sxs-lookup"><span data-stu-id="d5ea1-142">Examples</span></span>

<span data-ttu-id="d5ea1-143">在 `mytestproject.dll` 中运行测试：</span><span class="sxs-lookup"><span data-stu-id="d5ea1-143">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="d5ea1-144">在 `mytestproject.dll` 和 `myothertestproject.exe` 中运行测试：</span><span class="sxs-lookup"><span data-stu-id="d5ea1-144">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="d5ea1-145">运行 `TestMethod1` 测试：</span><span class="sxs-lookup"><span data-stu-id="d5ea1-145">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="d5ea1-146">运行 `TestMethod1` 和 `TestMethod2` 测试：</span><span class="sxs-lookup"><span data-stu-id="d5ea1-146">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
