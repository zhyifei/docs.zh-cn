---
title: global.json 引用
description: 参阅 global.json 文件的架构，可以通过它来设置 .NET Core 工具版本。
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a>global.json 引用

global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。

.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。

## <a name="sdk"></a>SDK
类型：Object

指定 SDK 相关信息。

### <a name="version"></a>version
类型：String

要使用的 SDK 版本。

例如:

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
