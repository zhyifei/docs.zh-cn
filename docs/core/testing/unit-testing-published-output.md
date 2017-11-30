---
title: "测试已发布的输出，其中 dotnet 则 vstest"
description: "了解如何在已发布的输出，其中 dotnet 则 vstest 命令上运行测试。"
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="a0ef4-103">测试已发布的输出，其中 dotnet 则 vstest</span><span class="sxs-lookup"><span data-stu-id="a0ef4-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="a0ef4-104">你可以在已发布的输出上运行测试，通过使用`dotnet vstest`命令。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="a0ef4-105">这将在处理 xUnit、 MSTest 和 NUnit 测试。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="a0ef4-106">只需找到已发布输出的一部分的 DLL 文件，并运行：</span><span class="sxs-lookup"><span data-stu-id="a0ef4-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="a0ef4-107">其中`<MyPublishedTests>`是发布的测试项目的名称。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="a0ef4-108">在已发布的 DLL 中运行测试的示例</span><span class="sxs-lookup"><span data-stu-id="a0ef4-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="a0ef4-109">注意： 如果你的应用面向一个框架的以外`netcoreapp`你仍可运行`dotnet vstest`命令通过传入 framework 标志的目标 framework。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="a0ef4-110">例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="a0ef4-111">在 Visual Studio 2017 更新 5 中自动检测到所需的框架。</span><span class="sxs-lookup"><span data-stu-id="a0ef4-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="a0ef4-112">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0ef4-112">Related topics</span></span>
- [<span data-ttu-id="a0ef4-113">与 dotnet 测试和 xUnit 的单元测试</span><span class="sxs-lookup"><span data-stu-id="a0ef4-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="a0ef4-114">与 dotnet 测试和 MSTest 的单元测试</span><span class="sxs-lookup"><span data-stu-id="a0ef4-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
