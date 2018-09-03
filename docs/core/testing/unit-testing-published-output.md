---
title: 通过 dotnet vstest 测试已发布的输出
description: 学习如何通过 dotnet vstest 命令测试已发布的输出。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404710"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="7968f-103">通过 dotnet vstest 测试已发布的输出</span><span class="sxs-lookup"><span data-stu-id="7968f-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="7968f-104">可以使用 `dotnet vstest` 命令测试已发布的输出。</span><span class="sxs-lookup"><span data-stu-id="7968f-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="7968f-105">这将适用于 xUnit、MSTest 和 NUnit 测试。</span><span class="sxs-lookup"><span data-stu-id="7968f-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="7968f-106">只需找到属于已发布输出的 DLL 文件，然后运行：</span><span class="sxs-lookup"><span data-stu-id="7968f-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="7968f-107">其中，`<MyPublishedTests>` 是已发布的测试项目的名称。</span><span class="sxs-lookup"><span data-stu-id="7968f-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="7968f-108">在已发布的 DLL 中运行测试的示例</span><span class="sxs-lookup"><span data-stu-id="7968f-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="7968f-109">注意：如果你的应用以 `netcoreapp` 之外的框架为目标，则仍然可以通过使用框架标志传入目标框架来运行 `dotnet vstest` 命令。</span><span class="sxs-lookup"><span data-stu-id="7968f-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="7968f-110">例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。</span><span class="sxs-lookup"><span data-stu-id="7968f-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="7968f-111">在 Visual Studio 2017 Update 5 中，自动检测所需的框架。</span><span class="sxs-lookup"><span data-stu-id="7968f-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="7968f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7968f-112">See also</span></span>
- [<span data-ttu-id="7968f-113">使用 dotnet 测试和 xUnit 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="7968f-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="7968f-114">使用 dotnet 测试和 NUnit 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="7968f-114">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="7968f-115">使用 dotnet 测试和 MSTest 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="7968f-115">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
