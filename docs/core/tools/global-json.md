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
# <a name="globaljson-reference"></a><span data-ttu-id="b505b-103">global.json 引用</span><span class="sxs-lookup"><span data-stu-id="b505b-103">global.json reference</span></span>

<span data-ttu-id="b505b-104">global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。</span><span class="sxs-lookup"><span data-stu-id="b505b-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="b505b-105">.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。</span><span class="sxs-lookup"><span data-stu-id="b505b-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="b505b-106">SDK</span><span class="sxs-lookup"><span data-stu-id="b505b-106">sdk</span></span>
<span data-ttu-id="b505b-107">类型：Object</span><span class="sxs-lookup"><span data-stu-id="b505b-107">Type: Object</span></span>

<span data-ttu-id="b505b-108">指定 SDK 相关信息。</span><span class="sxs-lookup"><span data-stu-id="b505b-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="b505b-109">version</span><span class="sxs-lookup"><span data-stu-id="b505b-109">version</span></span>
<span data-ttu-id="b505b-110">类型：String</span><span class="sxs-lookup"><span data-stu-id="b505b-110">Type: String</span></span>

<span data-ttu-id="b505b-111">要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b505b-111">The version of the SDK to use.</span></span>

<span data-ttu-id="b505b-112">例如:</span><span class="sxs-lookup"><span data-stu-id="b505b-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
