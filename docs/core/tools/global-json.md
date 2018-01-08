---
title: "global.json 引用"
description: "参阅 global.json 文件的架构，可以通过它来设置 .NET Core 工具版本。"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.workload: dotnetcore
ms.openlocfilehash: c7e64995ed00a6b2df1b7e1dfa43c6bea5cf4535
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="globaljson-reference"></a><span data-ttu-id="19e8f-104">global.json 引用</span><span class="sxs-lookup"><span data-stu-id="19e8f-104">global.json reference</span></span>

<span data-ttu-id="19e8f-105">global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。</span><span class="sxs-lookup"><span data-stu-id="19e8f-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="19e8f-106">.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。</span><span class="sxs-lookup"><span data-stu-id="19e8f-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="19e8f-107">SDK</span><span class="sxs-lookup"><span data-stu-id="19e8f-107">sdk</span></span>
<span data-ttu-id="19e8f-108">类型：Object</span><span class="sxs-lookup"><span data-stu-id="19e8f-108">Type: Object</span></span>

<span data-ttu-id="19e8f-109">指定 SDK 相关信息。</span><span class="sxs-lookup"><span data-stu-id="19e8f-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="19e8f-110">version</span><span class="sxs-lookup"><span data-stu-id="19e8f-110">version</span></span>
<span data-ttu-id="19e8f-111">类型：String</span><span class="sxs-lookup"><span data-stu-id="19e8f-111">Type: String</span></span>

<span data-ttu-id="19e8f-112">要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="19e8f-112">The version of the SDK to use.</span></span>

<span data-ttu-id="19e8f-113">例如:</span><span class="sxs-lookup"><span data-stu-id="19e8f-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
