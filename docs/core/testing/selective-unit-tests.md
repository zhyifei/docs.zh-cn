---
title: 运行选择性单元测试
description: 如何使用筛选表达式通过 .NET Core 中的 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543503"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="3fbf2-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="3fbf2-103">Running selective unit tests</span></span>

<span data-ttu-id="3fbf2-104">借助 .NET Core 中的 `dotnet test` 命令，可以使用筛选表达式来运行选择性测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="3fbf2-105">本文演示如何筛选运行哪些测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="3fbf2-106">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="3fbf2-107">如果使用的是 `vstest.console.exe`，请将 `--filter` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="3fbf2-108">在 `*nix` 上使用包含感叹号 (!)的筛选器需要转义，因为保留了 `!`。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="3fbf2-109">例如，如果命名空间包含 IntegrationTests `dotnet test --filter FullyQualifiedName\!~IntegrationTests`，则此筛选器将跳过所有测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="3fbf2-110">请注意感叹号前面的反斜杠。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="3fbf2-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="3fbf2-111">MSTest</span></span>

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

| <span data-ttu-id="3fbf2-112">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-112">Expression</span></span> | <span data-ttu-id="3fbf2-113">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="3fbf2-114">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="3fbf2-115">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3fbf2-116">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="3fbf2-117">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="3fbf2-118">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3fbf2-119">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3fbf2-120">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3fbf2-121">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="3fbf2-122">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="3fbf2-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3fbf2-123">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-123">Expression</span></span> | <span data-ttu-id="3fbf2-124">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="3fbf2-125">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="3fbf2-126">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3fbf2-127">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="3fbf2-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="3fbf2-128">xUnit</span></span>

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

| <span data-ttu-id="3fbf2-129">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-129">Expression</span></span> | <span data-ttu-id="3fbf2-130">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3fbf2-131">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3fbf2-132">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="3fbf2-133">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="3fbf2-134">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="3fbf2-135">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-135">Expression</span></span> | <span data-ttu-id="3fbf2-136">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="3fbf2-137">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="3fbf2-138">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="3fbf2-139">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="3fbf2-140">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="3fbf2-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3fbf2-141">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-141">Expression</span></span> | <span data-ttu-id="3fbf2-142">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="3fbf2-143">运行 `FullyQualifiedName` 包含 `TestClass1` 或 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="3fbf2-144">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3fbf2-145">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="3fbf2-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="3fbf2-146">NUnit</span></span>

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

| <span data-ttu-id="3fbf2-147">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-147">Expression</span></span> | <span data-ttu-id="3fbf2-148">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="3fbf2-149">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="3fbf2-150">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3fbf2-151">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="3fbf2-152">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3fbf2-153">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3fbf2-154">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3fbf2-155">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="3fbf2-156">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="3fbf2-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3fbf2-157">表达式</span><span class="sxs-lookup"><span data-stu-id="3fbf2-157">Expression</span></span> | <span data-ttu-id="3fbf2-158">结果</span><span class="sxs-lookup"><span data-stu-id="3fbf2-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="3fbf2-159">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="3fbf2-160">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3fbf2-161">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="3fbf2-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
