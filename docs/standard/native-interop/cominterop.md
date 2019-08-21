---
title: .NET 中的 COM 互操作
description: 了解如何在 .NET 中与 COM 库进行互操作。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 07/11/2019
ms.openlocfilehash: 9355e2ae84da623ffa725f5b2ac1bdee25b966d8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971893"
---
# <a name="com-interop-in-net"></a>.NET 中的 COM 互操作

组件对象模型 (COM) 允许对象向其他组件公开其功能并在 Windows 平台上托管应用程序。 为帮助用户实现与其现有代码库的互操作，.NET Framework 始终为与 COM 库进行互操作提供强大支持。 在 .NET Core 3.0 中，此支持中的很大一部分已添加到 Windows 上的 .NET Core。 此处的文档说明了公共 COM 互操作技术的工作原理，以及如何利用它们与现有 COM 库进行互操作。

- [COM 包装](./com-wrappers.md)
- [COM 可调用包装器](./com-callable-wrapper.md)
- [运行时可调用包装器](./runtime-callable-wrapper.md)
- [为 COM 互操作限定 .NET 类型](./qualify-net-types-for-interoperation.md)
