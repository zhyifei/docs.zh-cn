---
title: "运行选择性单元测试"
description: "介绍了如何使用筛选表达式通过 dotnet 测试命令运行选择性单元测试。"
keywords: ".NET, .NET Core, 单元测试, 选择性测试"
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="running-selective-unit-tests"></a><span data-ttu-id="f4cf9-104">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="f4cf9-104">Running selective unit tests</span></span>

<span data-ttu-id="f4cf9-105">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="f4cf9-106">如果使用的是 `vstest.console.exe`，请将 `--filter ` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="f4cf9-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="f4cf9-107">MSTest</span></span>

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="f4cf9-108">Expression</span><span class="sxs-lookup"><span data-stu-id="f4cf9-108">Expression</span></span> | <span data-ttu-id="f4cf9-109">结果</span><span class="sxs-lookup"><span data-stu-id="f4cf9-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f4cf9-110">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f4cf9-111">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f4cf9-112">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="f4cf9-113">运行属于类 `MSTestNamespace.UnitTestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="f4cf9-114">**注意：**由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTestClass1` 无效。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="f4cf9-115">运行除 `MSTestNamespace.UnitTestClass1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f4cf9-116">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="f4cf9-117">运行含 `[Priority(3)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="f4cf9-118">**注意：**`Priority~3` 值无效，因为它不是字符串。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="f4cf9-119">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="f4cf9-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f4cf9-120">Expression</span><span class="sxs-lookup"><span data-stu-id="f4cf9-120">Expression</span></span> | <span data-ttu-id="f4cf9-121">结果</span><span class="sxs-lookup"><span data-stu-id="f4cf9-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f4cf9-122">运行 `FullyQualifiedName` 包含 `UnitTestClass1` **或** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="f4cf9-123">运行 `FullyQualifiedName` 包含 `UnitTestClass1` **且** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f4cf9-124">运行 `FullyQualifiedName` 包含 `UnitTestClass1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="f4cf9-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="f4cf9-125">xUnit</span></span>

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| <span data-ttu-id="f4cf9-126">Expression</span><span class="sxs-lookup"><span data-stu-id="f4cf9-126">Expression</span></span> | <span data-ttu-id="f4cf9-127">结果</span><span class="sxs-lookup"><span data-stu-id="f4cf9-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f4cf9-128">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f4cf9-129">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="f4cf9-130">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="f4cf9-131">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="f4cf9-132">Expression</span><span class="sxs-lookup"><span data-stu-id="f4cf9-132">Expression</span></span> | <span data-ttu-id="f4cf9-133">结果</span><span class="sxs-lookup"><span data-stu-id="f4cf9-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="f4cf9-134">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="f4cf9-135">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="f4cf9-136">运行包含 `[Trait("Category", "bvt")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="f4cf9-137">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="f4cf9-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f4cf9-138">Expression</span><span class="sxs-lookup"><span data-stu-id="f4cf9-138">Expression</span></span> | <span data-ttu-id="f4cf9-139">结果</span><span class="sxs-lookup"><span data-stu-id="f4cf9-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="f4cf9-140">运行 `FullyQualifiedName` 包含 `TestClass1` **或** `Category`是 `Nightly` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="f4cf9-141">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category`是 `Nightly` 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="f4cf9-142">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="f4cf9-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

