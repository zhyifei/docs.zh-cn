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
# <a name="globaljson-reference"></a><span data-ttu-id="ac1e1-103">global.json 引用</span><span class="sxs-lookup"><span data-stu-id="ac1e1-103">global.json reference</span></span>

<span data-ttu-id="ac1e1-104">global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。</span><span class="sxs-lookup"><span data-stu-id="ac1e1-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="ac1e1-105">.NET Core CLI 工具在当前工作目录（不必与项目目录相同）或它的一个父目录中查找此文件。</span><span class="sxs-lookup"><span data-stu-id="ac1e1-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="ac1e1-106">SDK</span><span class="sxs-lookup"><span data-stu-id="ac1e1-106">sdk</span></span>
<span data-ttu-id="ac1e1-107">类型：Object</span><span class="sxs-lookup"><span data-stu-id="ac1e1-107">Type: Object</span></span>

<span data-ttu-id="ac1e1-108">指定 SDK 相关信息。</span><span class="sxs-lookup"><span data-stu-id="ac1e1-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="ac1e1-109">version</span><span class="sxs-lookup"><span data-stu-id="ac1e1-109">version</span></span>
<span data-ttu-id="ac1e1-110">类型：String</span><span class="sxs-lookup"><span data-stu-id="ac1e1-110">Type: String</span></span>

<span data-ttu-id="ac1e1-111">要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="ac1e1-111">The version of the SDK to use.</span></span>

<span data-ttu-id="ac1e1-112">例如:</span><span class="sxs-lookup"><span data-stu-id="ac1e1-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
