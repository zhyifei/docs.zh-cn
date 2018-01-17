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
ms.workload: dotnetcore
ms.openlocfilehash: a650e971afd63171b0cc12f679d81bc222a609a5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="running-selective-unit-tests"></a>运行选择性单元测试

下面的示例使用 `dotnet test`。 如果使用的是 `vstest.console.exe`，请将 `--filter ` 替换成 `--testcasefilter:`。

## <a name="mstest"></a>MSTest

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

| 表达式 | 结果 |
| ---------- | ------ |
| `dotnet test --filter Method` | 运行 `FullyQualifiedName` 包含 `Method` 的测试。 在 `vstest 15.1+` 中可用。 |
| `dotnet test --filter Name~TestMethod1` | 运行名称包含 `TestMethod1` 的测试。 |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | 运行属于类 `MSTestNamespace.UnitTestClass1` 的测试。<br>**注意：**由于 `ClassName` 值应有命名空间，因此 `ClassName=UnitTestClass1` 无效。 |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | 运行除 `MSTestNamespace.UnitTestClass1.TestMethod1` 之外的其他所有测试。 |
| `dotnet test --filter TestCategory=CategoryA` | 运行含 `[TestCategory("CategoryA")]` 批注的测试。 |
| `dotnet test --filter Priority=3` | 运行含 `[Priority(3)]` 批注的测试。<br>**注意：**`Priority~3` 值无效，因为它不是字符串。 |

**使用条件运算符 | 和 &amp;**

| 表达式 | 结果 |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | 运行 `FullyQualifiedName` 包含 `UnitTestClass1` **或** `TestCategory` 是 `CategoryA` 的测试。 |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | 运行 `FullyQualifiedName` 包含 `UnitTestClass1` **且** `TestCategory` 是 `CategoryA` 的测试。 |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | 运行 `FullyQualifiedName` 包含 `UnitTestClass1` **且** `TestCategory` 是 `CategoryA` **或** `Priority` 是 1 的测试。 |

## <a name="xunit"></a>xUnit

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

| 表达式 | 结果 |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | 仅运行一个测试，即 `XUnitNamespace.TestClass1.Test1`。 |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | 运行除 `XUnitNamespace.TestClass1.Test1` 之外的其他所有测试。 |
| `dotnet test --filter DisplayName~TestClass1` | 运行显示名称包含 `TestClass1` 的测试。 |

在代码示例中，包含键 `Category` 和 `Priority` 的已定义特征可用于筛选。

| 表达式 | 结果 |
| ---------- | ------ |
| `dotnet test --filter XUnit` | 运行 `FullyQualifiedName` 包含 `XUnit` 的测试。  在 `vstest 15.1+` 中可用。 |
| `dotnet test --filter Category=bvt` | 运行包含 `[Trait("Category", "bvt")]` 的测试。 |

**使用条件运算符 | 和 &amp;**

| 表达式 | 结果 |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | 运行 `FullyQualifiedName` 包含 `TestClass1` **或** `Category`是 `Nightly` 的测试。 |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | 运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category`是 `Nightly` 的测试。 |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | 运行 `FullyQualifiedName` 包含 `TestClass1` **且** `Category` 是 `CategoryA` **或** `Priority` 是 1 的测试。 |
