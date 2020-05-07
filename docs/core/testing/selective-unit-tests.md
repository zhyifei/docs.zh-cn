---
title: 运行选择性单元测试
description: 如何使用筛选表达式通过 .NET Core 中的 dotnet 测试命令运行选择性单元测试。
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728184"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="957cb-103">运行选择性单元测试</span><span class="sxs-lookup"><span data-stu-id="957cb-103">Run selective unit tests</span></span>

<span data-ttu-id="957cb-104">借助 .NET Core 中的 `dotnet test` 命令，可以使用筛选表达式来运行选择性测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="957cb-105">本文演示如何筛选运行哪些测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="957cb-106">下面的示例使用 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="957cb-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="957cb-107">如果使用的是 `vstest.console.exe`，请将 `--filter` 替换成 `--testcasefilter:`。</span><span class="sxs-lookup"><span data-stu-id="957cb-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="957cb-108">字符转义</span><span class="sxs-lookup"><span data-stu-id="957cb-108">Character escaping</span></span>

<span data-ttu-id="957cb-109">在 `*nix` 上使用包含感叹号 (!)的筛选器需要转义，因为保留了 `!`。</span><span class="sxs-lookup"><span data-stu-id="957cb-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="957cb-110">例如，如果命名空间包含 IntegrationTests `dotnet test --filter FullyQualifiedName\!~IntegrationTests`，则此筛选器将跳过所有测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="957cb-111">请注意感叹号前面的反斜杠。</span><span class="sxs-lookup"><span data-stu-id="957cb-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="957cb-112">对于包含泛型类型参数的逗号的 `FullyQualifiedName` 值，请使用 `%2C` 来转义逗号。</span><span class="sxs-lookup"><span data-stu-id="957cb-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="957cb-113">例如：</span><span class="sxs-lookup"><span data-stu-id="957cb-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="957cb-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="957cb-114">MSTest</span></span>

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

| <span data-ttu-id="957cb-115">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-115">Expression</span></span> | <span data-ttu-id="957cb-116">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="957cb-117">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="957cb-118">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="957cb-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="957cb-119">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="957cb-120">运行属于类 `MSTestNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="957cb-121">**注意：** 由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTest1` 无效。</span><span class="sxs-lookup"><span data-stu-id="957cb-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="957cb-122">运行除 `MSTestNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="957cb-123">运行含 `[TestCategory("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="957cb-124">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="957cb-125">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="957cb-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cb-126">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-126">Expression</span></span> | <span data-ttu-id="957cb-127">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="957cb-128">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="957cb-129">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cb-130">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="957cb-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="957cb-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="957cb-131">xUnit</span></span>

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

| <span data-ttu-id="957cb-132">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-132">Expression</span></span> | <span data-ttu-id="957cb-133">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="957cb-134">仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。</span><span class="sxs-lookup"><span data-stu-id="957cb-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="957cb-135">运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="957cb-136">运行显示名称包含 `TestClass1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="957cb-137">在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。</span><span class="sxs-lookup"><span data-stu-id="957cb-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="957cb-138">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-138">Expression</span></span> | <span data-ttu-id="957cb-139">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="957cb-140">运行 `FullyQualifiedName` 包含 `XUnit` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="957cb-141">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="957cb-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="957cb-142">运行包含 `[Trait("Category", "CategoryA")]` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="957cb-143">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="957cb-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cb-144">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-144">Expression</span></span> | <span data-ttu-id="957cb-145">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="957cb-146">运行 `FullyQualifiedName` 包含 `TestClass1` 或 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="957cb-147">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cb-148">运行 `FullyQualifiedName` 包含 `TestClass1` 且 `Category` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="957cb-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="957cb-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="957cb-149">NUnit</span></span>

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

| <span data-ttu-id="957cb-150">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-150">Expression</span></span> | <span data-ttu-id="957cb-151">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="957cb-152">运行 `FullyQualifiedName` 包含 `Method` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="957cb-153">在 `vstest 15.1+` 中可用。</span><span class="sxs-lookup"><span data-stu-id="957cb-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="957cb-154">运行名称包含 `TestMethod1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="957cb-155">运行属于类 `NUnitNamespace.UnitTest1` 的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="957cb-156">运行除 `NUnitNamespace.UnitTest1.TestMethod1` 之外的其他所有测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="957cb-157">运行含 `[Category("CategoryA")]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="957cb-158">运行含 `[Priority(2)]` 批注的测试。</span><span class="sxs-lookup"><span data-stu-id="957cb-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="957cb-159">**使用条件运算符 | 和 &amp;**</span><span class="sxs-lookup"><span data-stu-id="957cb-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cb-160">表达式</span><span class="sxs-lookup"><span data-stu-id="957cb-160">Expression</span></span> | <span data-ttu-id="957cb-161">结果</span><span class="sxs-lookup"><span data-stu-id="957cb-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="957cb-162">运行 `FullyQualifiedName` 包含 `UnitTest1` 或 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="957cb-163">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 的测试  。</span><span class="sxs-lookup"><span data-stu-id="957cb-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cb-164">运行 `FullyQualifiedName` 包含 `UnitTest1` 且 `TestCategory` 是 `CategoryA` 或 `Priority` 是 1 的测试   。</span><span class="sxs-lookup"><span data-stu-id="957cb-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="957cb-165">有关详细信息，请参阅 [TestCase 筛选器](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)</span><span class="sxs-lookup"><span data-stu-id="957cb-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
