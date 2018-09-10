---
title: 运行选择性单元测试
description: 介绍了如何使用筛选表达式通过 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: 428e31014f5d8d487deb7c4b4317ebcef13c294d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517215"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="d56c6-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="d56c6-103">Running selective unit tests</span></span>

<span data-ttu-id="d56c6-104">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="d56c6-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="d56c6-105">如果使用的是 `vstest.console.exe`，请将 `--filter ` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="d56c6-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="d56c6-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="d56c6-106">MSTest</span></span>

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

| <span data-ttu-id="d56c6-107">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-107">Expression</span></span> | <span data-ttu-id="d56c6-108">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="d56c6-109">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="d56c6-110">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="d56c6-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="d56c6-111">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="d56c6-112">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="d56c6-113">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="d56c6-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="d56c6-114">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="d56c6-115">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="d56c6-116">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="d56c6-117">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="d56c6-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="d56c6-118">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-118">Expression</span></span> | <span data-ttu-id="d56c6-119">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="d56c6-120">运行 `FullyQualifiedName` 包含 `UnitTest1` **或** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="d56c6-121">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="d56c6-122">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="d56c6-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="d56c6-123">xUnit</span></span>

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

| <span data-ttu-id="d56c6-124">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-124">Expression</span></span> | <span data-ttu-id="d56c6-125">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="d56c6-126">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="d56c6-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="d56c6-127">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="d56c6-128">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="d56c6-129">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="d56c6-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="d56c6-130">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-130">Expression</span></span> | <span data-ttu-id="d56c6-131">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="d56c6-132">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="d56c6-133">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="d56c6-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="d56c6-134">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="d56c6-135">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="d56c6-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="d56c6-136">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-136">Expression</span></span> | <span data-ttu-id="d56c6-137">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="d56c6-138">运行 `FullyQualifiedName` 包含 `TestClass1` **或** `Category`是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="d56c6-139">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category`是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="d56c6-140">运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="d56c6-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="d56c6-141">NUnit</span></span>

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

| <span data-ttu-id="d56c6-142">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-142">Expression</span></span> | <span data-ttu-id="d56c6-143">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="d56c6-144">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="d56c6-145">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="d56c6-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="d56c6-146">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="d56c6-147">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="d56c6-148">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="d56c6-149">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="d56c6-150">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="d56c6-151">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="d56c6-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="d56c6-152">表达式</span><span class="sxs-lookup"><span data-stu-id="d56c6-152">Expression</span></span> | <span data-ttu-id="d56c6-153">结果</span><span class="sxs-lookup"><span data-stu-id="d56c6-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="d56c6-154">运行 `FullyQualifiedName` 包含 `UnitTest1` **或** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="d56c6-155">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="d56c6-156">运行 `FullyQualifiedName` 包含 `UnitTest1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。</span><span class="sxs-lookup"><span data-stu-id="d56c6-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
