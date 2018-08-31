---
title: 通过 dotnet vstest 测试已发布的输出
description: 学习如何通过 dotnet vstest 命令测试已发布的输出。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936021"
---
# <a name="test-published-output-with-dotnet-vstest"></a>通过 dotnet vstest 测试已发布的输出

可以使用 `dotnet vstest` 命令测试已发布的输出。 这将适用于 xUnit、MSTest 和 NUnit 测试。 只需找到属于已发布输出的 DLL 文件，然后运行：

```
dotnet vstest <MyPublishedTests>.dll
```

其中，`<MyPublishedTests>` 是已发布的测试项目的名称。

## <a name="example-of-running-tests-on-a-published-dll"></a>在已发布的 DLL 中运行测试的示例

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> 注意：如果你的应用以 `netcoreapp` 之外的框架为目标，则仍然可以通过使用框架标志传入目标框架来运行 `dotnet vstest` 命令。 例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。 在 Visual Studio 2017 Update 5 中，自动检测所需的框架。

## <a name="see-also"></a>请参阅
- [使用 dotnet 测试和 xUnit 进行单元测试](unit-testing-with-dotnet-test.md)
- [使用 dotnet 测试和 NUnit 进行单元测试](unit-testing-with-nunit.md)
- [使用 dotnet 测试和 MSTest 进行单元测试](unit-testing-with-mstest.md)
