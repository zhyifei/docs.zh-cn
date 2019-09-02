---
title: 通过 dotnet vstest 测试已发布的输出
description: 了解如何使用 dotnet vstest 命令在已发布的库上运行测试，而不在源代码上运行测试。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 9ac03053bc762d0176e087545871ca8a145cd41e
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168294"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="5b12c-103">通过 dotnet vstest 测试已发布的输出</span><span class="sxs-lookup"><span data-stu-id="5b12c-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="5b12c-104">可以使用 `dotnet vstest` 命令测试已发布的输出。</span><span class="sxs-lookup"><span data-stu-id="5b12c-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="5b12c-105">这将适用于 xUnit、MSTest 和 NUnit 测试。</span><span class="sxs-lookup"><span data-stu-id="5b12c-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="5b12c-106">只需找到属于已发布输出的 DLL 文件，然后运行：</span><span class="sxs-lookup"><span data-stu-id="5b12c-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```console
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="5b12c-107">其中，`<MyPublishedTests>` 是已发布的测试项目的名称。</span><span class="sxs-lookup"><span data-stu-id="5b12c-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="5b12c-108">示例</span><span class="sxs-lookup"><span data-stu-id="5b12c-108">Example</span></span>

<span data-ttu-id="5b12c-109">下面的命令演示在已发布的 DLL 上运行测试。</span><span class="sxs-lookup"><span data-stu-id="5b12c-109">The commands below demonstrate running tests on a published DLL.</span></span>

```console
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="5b12c-110">注意：如果你的应用以 `netcoreapp` 之外的框架为目标，则仍然可以通过使用框架标志传入目标框架来运行 `dotnet vstest` 命令。</span><span class="sxs-lookup"><span data-stu-id="5b12c-110">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="5b12c-111">例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。</span><span class="sxs-lookup"><span data-stu-id="5b12c-111">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="5b12c-112">在 Visual Studio 2017 Update 5 中，自动检测所需的框架。</span><span class="sxs-lookup"><span data-stu-id="5b12c-112">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b12c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b12c-113">See also</span></span>

- [<span data-ttu-id="5b12c-114">使用 dotnet 测试和 xUnit 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="5b12c-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="5b12c-115">使用 dotnet 测试和 NUnit 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="5b12c-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="5b12c-116">使用 dotnet 测试和 MSTest 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="5b12c-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
