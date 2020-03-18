---
title: 运行选择性单元测试
description: 如何使用筛选表达式通过 .NET Core 中的 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543503"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="95472-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="95472-103">Running selective unit tests</span></span>

<span data-ttu-id="95472-104">借助 .NET Core 中的 `dotnet test` 命令，可以使用筛选表达式来运行选择性测试。</span><span class="sxs-lookup"><span data-stu-id="95472-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="95472-105">本文演示如何筛选运行哪些测试。</span><span class="sxs-lookup"><span data-stu-id="95472-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="95472-106">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="95472-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="95472-107">如果使用的是 `vstest.console.exe`，请将 `--filter` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="95472-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="95472-108">在 `*nix` 上使用包含感叹号 (!)的筛选器需要转义，因为保留了 `!`。</span><span class="sxs-lookup"><span data-stu-id="95472-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="95472-109">例如，如果命名空间包含 IntegrationTests `dotnet test --filter FullyQualifiedName\!~IntegrationTests`，则此筛选器将跳过所有测试。</span><span class="sxs-lookup"><span data-stu-id="95472-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="95472-110">请注意感叹号前面的反斜杠。</span><span class="sxs-lookup"><span data-stu-id="95472-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="95472-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="95472-111">MSTest</span></span>

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

| <span data-ttu-id="95472-112">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-112">Expression</span></span> | <span data-ttu-id="95472-113">结果</span><span class="sxs-lookup"><span data-stu-id="95472-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="95472-114">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="95472-115">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="95472-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="95472-116">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="95472-117">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="95472-118">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="95472-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="95472-119">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="95472-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="95472-120">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="95472-121">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="95472-122">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="95472-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="95472-123">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-123">Expression</span></span> | <span data-ttu-id="95472-124">结果</span><span class="sxs-lookup"><span data-stu-id="95472-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="95472-125">运行 `UnitTest1` 包含 `FullyQualifiedName` 或 **是** 的测试`TestCategory``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="95472-126">运行 `UnitTest1` 包含 `FullyQualifiedName` 且 **是** 的测试`TestCategory``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="95472-127">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 **是** 或 `TestCategory` 是 1 的测试`CategoryA`  `Priority`。</span><span class="sxs-lookup"><span data-stu-id="95472-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="95472-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="95472-128">xUnit</span></span>

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

| <span data-ttu-id="95472-129">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-129">Expression</span></span> | <span data-ttu-id="95472-130">结果</span><span class="sxs-lookup"><span data-stu-id="95472-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="95472-131">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="95472-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="95472-132">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="95472-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="95472-133">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="95472-134">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="95472-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="95472-135">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-135">Expression</span></span> | <span data-ttu-id="95472-136">结果</span><span class="sxs-lookup"><span data-stu-id="95472-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="95472-137">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="95472-138">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="95472-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="95472-139">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="95472-140">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="95472-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="95472-141">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-141">Expression</span></span> | <span data-ttu-id="95472-142">结果</span><span class="sxs-lookup"><span data-stu-id="95472-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="95472-143">运行 `TestClass1` 包含 `FullyQualifiedName` 或 **是** 的测试`Category``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="95472-144">运行 `TestClass1` 包含 `FullyQualifiedName` 且 **是** 的测试`Category``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="95472-145">运行 `FullyQualifiedName` 包含 `TestClass1` 且 **是** 或 `Category` 是 1 的测试`CategoryA`  `Priority`。</span><span class="sxs-lookup"><span data-stu-id="95472-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="95472-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="95472-146">NUnit</span></span>

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

| <span data-ttu-id="95472-147">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-147">Expression</span></span> | <span data-ttu-id="95472-148">结果</span><span class="sxs-lookup"><span data-stu-id="95472-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="95472-149">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="95472-150">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="95472-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="95472-151">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="95472-152">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="95472-153">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="95472-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="95472-154">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="95472-155">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="95472-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="95472-156">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="95472-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="95472-157">Expression</span><span class="sxs-lookup"><span data-stu-id="95472-157">Expression</span></span> | <span data-ttu-id="95472-158">结果</span><span class="sxs-lookup"><span data-stu-id="95472-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="95472-159">运行 `UnitTest1` 包含 `FullyQualifiedName` 或 **是** 的测试`TestCategory``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="95472-160">运行 `UnitTest1` 包含 `FullyQualifiedName` 且 **是** 的测试`TestCategory``CategoryA`。</span><span class="sxs-lookup"><span data-stu-id="95472-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="95472-161">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 **是** 或 `TestCategory` 是 1 的测试`CategoryA`  `Priority`。</span><span class="sxs-lookup"><span data-stu-id="95472-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
