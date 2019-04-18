---
title: 通过 dotnet vstest 测试已发布的输出
description: 了解如何使用 dotnet vstest 命令在已发布的库上运行测试，而不在源代码上运行测试。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 660b966c6d02353b855e5728094083042a561558
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126082"
---
# <a name="test-published-output-with-dotnet-vstest"></a>通过 dotnet vstest 测试已发布的输出

可以使用 `dotnet vstest` 命令测试已发布的输出。 这将适用于 xUnit、MSTest 和 NUnit 测试。 只需找到属于已发布输出的 DLL 文件，然后运行：

```
dotnet vstest <MyPublishedTests>.dll
```

其中，`<MyPublishedTests>` 是已发布的测试项目的名称。

## <a name="example"></a>示例

下面的命令演示在已发布的 DLL 上运行测试。

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> 注意:如果你的应用以 `netcoreapp` 之外的框架为目标，则仍然可以通过使用框架标志传入目标框架来运行 `dotnet vstest` 命令。 例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。 在 Visual Studio 2017 Update 5 中，自动检测所需的框架。

## <a name="see-also"></a>请参阅

- [使用 dotnet test 和 xUnit 进行单元测试](unit-testing-with-dotnet-test.md)
- [使用 dotnet test 和 NUnit 进行单元测试](unit-testing-with-nunit.md)
- [使用 dotnet test 和 MSTest 进行单元测试](unit-testing-with-mstest.md)
