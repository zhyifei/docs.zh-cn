---
title: 连接类
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a305b28a34a70112cc80c33b11f30ab02213f0c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120070"
---
# <a name="connection-class"></a><span data-ttu-id="4d8a8-102">连接类</span><span class="sxs-lookup"><span data-stu-id="4d8a8-102">Connection Class</span></span>

<span data-ttu-id="4d8a8-103">`Connection` 类分析服务器响应、队列请求和管道请求。</span><span class="sxs-lookup"><span data-stu-id="4d8a8-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d8a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d8a8-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="4d8a8-105">`Connection` 类是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="4d8a8-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="4d8a8-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="4d8a8-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4d8a8-107">要求</span><span class="sxs-lookup"><span data-stu-id="4d8a8-107">Requirements</span></span>

<span data-ttu-id="4d8a8-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4d8a8-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4d8a8-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="4d8a8-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4d8a8-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="4d8a8-110">**.NET Framework versions:** Available since 2.0.</span></span>
