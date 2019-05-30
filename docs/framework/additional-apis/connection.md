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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c50f673e77ef384ccf33803e14d60c322b6c0365
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300967"
---
# <a name="connection-class"></a><span data-ttu-id="93037-102">连接类</span><span class="sxs-lookup"><span data-stu-id="93037-102">Connection Class</span></span>

<span data-ttu-id="93037-103">`Connection`类分析服务器响应，队列请求，请求管道。</span><span class="sxs-lookup"><span data-stu-id="93037-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="93037-104">语法</span><span class="sxs-lookup"><span data-stu-id="93037-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="93037-105">`Connection`类内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="93037-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="93037-106">在生产应用程序在任何情况下，Microsoft 不支持此类使用。</span><span class="sxs-lookup"><span data-stu-id="93037-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="93037-107">要求</span><span class="sxs-lookup"><span data-stu-id="93037-107">Requirements</span></span>

<span data-ttu-id="93037-108">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="93037-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="93037-109">**程序集：** （在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="93037-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="93037-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="93037-110">**.NET Framework versions:** Available since 2.0.</span></span>
