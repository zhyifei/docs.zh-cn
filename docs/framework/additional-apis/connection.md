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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ed1fce1d16f9ddbe3a3ede91fecb1a3ca6b3d407
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146532"
---
# <a name="connection-class"></a><span data-ttu-id="70640-102">连接类</span><span class="sxs-lookup"><span data-stu-id="70640-102">Connection Class</span></span>

<span data-ttu-id="70640-103">`Connection`类分析服务器响应，队列请求，请求管道。</span><span class="sxs-lookup"><span data-stu-id="70640-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="70640-104">语法</span><span class="sxs-lookup"><span data-stu-id="70640-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="70640-105">`Connection`类内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="70640-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="70640-106">在生产应用程序在任何情况下，Microsoft 不支持此类使用。</span><span class="sxs-lookup"><span data-stu-id="70640-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="70640-107">要求</span><span class="sxs-lookup"><span data-stu-id="70640-107">Requirements</span></span>

<span data-ttu-id="70640-108">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="70640-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="70640-109">**程序集：**（在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="70640-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="70640-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="70640-110">**.NET Framework versions:** Available since 2.0.</span></span>
