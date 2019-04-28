---
title: ConnectionGroup 类
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 8fddc2cd537963ad2aa1e0858476e7b9b9c6c032
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706138"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="7e9e9-102">ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="7e9e9-102">ConnectionGroup Class</span></span>

<span data-ttu-id="7e9e9-103">`ConnectionGroup`类中的连接列表进行分组<xref:System.Net.ServicePoint>上下文和用于维护的网络资源 （例如，代理和单独的客户端） 的上下文。</span><span class="sxs-lookup"><span data-stu-id="7e9e9-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="7e9e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e9e9-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="7e9e9-105">`ConnectionGroup`类内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="7e9e9-105">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="7e9e9-106">在生产应用程序在任何情况下，Microsoft 不支持此类使用。</span><span class="sxs-lookup"><span data-stu-id="7e9e9-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e9e9-107">要求</span><span class="sxs-lookup"><span data-stu-id="7e9e9-107">Requirements</span></span>

<span data-ttu-id="7e9e9-108">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7e9e9-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7e9e9-109">**程序集：**（在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="7e9e9-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7e9e9-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="7e9e9-110">**.NET Framework versions:** Available since 2.0.</span></span>
