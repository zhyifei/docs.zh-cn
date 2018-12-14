---
title: 运行选择性单元测试 - .NET Core
description: 如何使用筛选表达式通过 .NET Core 中的 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.custom: seodec18
ms.openlocfilehash: 3c24fb8cc5024399ae523801373b0fd8eff85f45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151741"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="8c652-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="8c652-103">Running selective unit tests</span></span>

<span data-ttu-id="8c652-104">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="8c652-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="8c652-105">如果使用的是 `vstest.console.exe`，请将 `--filter ` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="8c652-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="8c652-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="8c652-106">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="8c652-107">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-107">Expression</span></span> | <span data-ttu-id="8c652-108">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8c652-109">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8c652-110">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="8c652-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8c652-111">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="8c652-112">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="8c652-113">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="8c652-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8c652-114">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8c652-115">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8c652-116">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8c652-117">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="8c652-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8c652-118">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-118">Expression</span></span> | <span data-ttu-id="8c652-119">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8c652-120">运行 `FullyQualifiedName` 包含 `UnitTest1` **或** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8c652-121">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8c652-122">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="8c652-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="8c652-123">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="8c652-124">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-124">Expression</span></span> | <span data-ttu-id="8c652-125">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8c652-126">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="8c652-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8c652-127">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="8c652-128">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="8c652-129">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="8c652-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="8c652-130">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-130">Expression</span></span> | <span data-ttu-id="8c652-131">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="8c652-132">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="8c652-133">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="8c652-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="8c652-134">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="8c652-135">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="8c652-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8c652-136">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-136">Expression</span></span> | <span data-ttu-id="8c652-137">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="8c652-138">运行 `FullyQualifiedName` 包含 `TestClass1` **或** `Category`是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="8c652-139">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category`是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8c652-140">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="8c652-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="8c652-141">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="8c652-142">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-142">Expression</span></span> | <span data-ttu-id="8c652-143">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8c652-144">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8c652-145">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="8c652-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8c652-146">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="8c652-147">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8c652-148">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8c652-149">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8c652-150">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8c652-151">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="8c652-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8c652-152">表达式</span><span class="sxs-lookup"><span data-stu-id="8c652-152">Expression</span></span> | <span data-ttu-id="8c652-153">结果</span><span class="sxs-lookup"><span data-stu-id="8c652-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8c652-154">运行 `FullyQualifiedName` 包含 `UnitTest1` **或** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8c652-155">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8c652-156">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="8c652-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
