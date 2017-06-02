---
title: "global.json 引用 |Microsoft 文档"
description: "global.json 引用"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.translationtype: Human Translation
ms.sourcegitcommit: ec7028d43e7236056e5a53160f6017edadfec8c2
ms.openlocfilehash: a35938d355cb86205e9c822736862298508cf861
ms.contentlocale: zh-cn
ms.lasthandoff: 04/06/2017

---

# <a name="globaljson-reference"></a>global.json 引用

global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。

.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。

## <a name="sdk"></a>SDK
类型：Object

指定 SDK 相关信息。

### <a name="version"></a>版本
类型：String

要使用的 SDK 版本。

例如：

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

