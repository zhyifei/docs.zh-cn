---
title: 运行选择性单元测试
description: 如何使用筛选表达式通过 .NET Core 中的 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: 57428dad2de6c2507ca2cdc42e3df9e83a1edd69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715464"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="99b89-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="99b89-103">Running selective unit tests</span></span>

<span data-ttu-id="99b89-104">借助 .NET Core 中的 `dotnet test` 命令，可以使用筛选表达式来运行选择性测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="99b89-105">本文演示如何筛选运行哪些测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="99b89-106">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="99b89-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="99b89-107">如果使用的是 `vstest.console.exe`，请将 `--filter` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="99b89-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="99b89-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="99b89-108">MSTest</span></span>

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

| <span data-ttu-id="99b89-109">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-109">Expression</span></span> | <span data-ttu-id="99b89-110">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="99b89-111">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="99b89-112">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="99b89-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="99b89-113">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="99b89-114">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="99b89-115">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="99b89-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="99b89-116">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="99b89-117">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="99b89-118">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="99b89-119">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="99b89-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="99b89-120">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-120">Expression</span></span> | <span data-ttu-id="99b89-121">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="99b89-122">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="99b89-123">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="99b89-124">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="99b89-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="99b89-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="99b89-125">xUnit</span></span>

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

| <span data-ttu-id="99b89-126">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-126">Expression</span></span> | <span data-ttu-id="99b89-127">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="99b89-128">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="99b89-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="99b89-129">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="99b89-130">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="99b89-131">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="99b89-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="99b89-132">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-132">Expression</span></span> | <span data-ttu-id="99b89-133">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="99b89-134">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="99b89-135">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="99b89-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="99b89-136">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="99b89-137">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="99b89-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="99b89-138">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-138">Expression</span></span> | <span data-ttu-id="99b89-139">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="99b89-140">运行 `FullyQualifiedName` 包含 `TestClass1` 或 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="99b89-141">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="99b89-142">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="99b89-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="99b89-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="99b89-143">NUnit</span></span>

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

| <span data-ttu-id="99b89-144">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-144">Expression</span></span> | <span data-ttu-id="99b89-145">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="99b89-146">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="99b89-147">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="99b89-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="99b89-148">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="99b89-149">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="99b89-150">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="99b89-151">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="99b89-152">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="99b89-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="99b89-153">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="99b89-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="99b89-154">表达式</span><span class="sxs-lookup"><span data-stu-id="99b89-154">Expression</span></span> | <span data-ttu-id="99b89-155">结果</span><span class="sxs-lookup"><span data-stu-id="99b89-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="99b89-156">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="99b89-157">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="99b89-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="99b89-158">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="99b89-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
