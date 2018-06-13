---
title: global.json 引用
description: 参阅 global.json 文件的架构，可以通过它来设置 .NET Core 工具版本。
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33209965"
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
