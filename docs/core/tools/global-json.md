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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="globaljson-reference"></a><span data-ttu-id="9c171-104">global.json 引用</span><span class="sxs-lookup"><span data-stu-id="9c171-104">global.json reference</span></span>

<span data-ttu-id="9c171-105">global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。</span><span class="sxs-lookup"><span data-stu-id="9c171-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="9c171-106">.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。</span><span class="sxs-lookup"><span data-stu-id="9c171-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="9c171-107">SDK</span><span class="sxs-lookup"><span data-stu-id="9c171-107">sdk</span></span>
<span data-ttu-id="9c171-108">类型：Object</span><span class="sxs-lookup"><span data-stu-id="9c171-108">Type: Object</span></span>

<span data-ttu-id="9c171-109">指定 SDK 相关信息。</span><span class="sxs-lookup"><span data-stu-id="9c171-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="9c171-110">版本</span><span class="sxs-lookup"><span data-stu-id="9c171-110">version</span></span>
<span data-ttu-id="9c171-111">类型：String</span><span class="sxs-lookup"><span data-stu-id="9c171-111">Type: String</span></span>

<span data-ttu-id="9c171-112">要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="9c171-112">The version of the SDK to use.</span></span>

<span data-ttu-id="9c171-113">例如：</span><span class="sxs-lookup"><span data-stu-id="9c171-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

