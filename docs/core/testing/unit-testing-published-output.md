---
title: "测试已发布的输出，其中 dotnet 则 vstest"
description: "了解如何在已发布的输出，其中 dotnet 则 vstest 命令上运行测试。"
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>测试已发布的输出，其中 dotnet 则 vstest

你可以在已发布的输出上运行测试，通过使用`dotnet vstest`命令。 这将在处理 xUnit、 MSTest 和 NUnit 测试。 只需找到已发布输出的一部分的 DLL 文件，并运行：
```
dotnet vstest <MyPublishedTests>.dll
```
其中`<MyPublishedTests>`是发布的测试项目的名称。

### <a name="example-of-running-tests-on-a-published-dll"></a>在已发布的 DLL 中运行测试的示例

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] 注意： 如果你的应用面向一个框架的以外`netcoreapp`你仍可运行`dotnet vstest`命令通过传入 framework 标志的目标 framework。 例如 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。 在 Visual Studio 2017 更新 5 中自动检测到所需的框架。

### <a name="related-topics"></a>相关主题
- [与 dotnet 测试和 xUnit 的单元测试](unit-testing-with-dotnet-test.md)
- [与 dotnet 测试和 MSTest 的单元测试](unit-testing-with-mstest.md)
