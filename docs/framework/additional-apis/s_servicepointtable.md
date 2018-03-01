---
title: "ServicePointManager.s_ServicePointTable 字段"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8dfdbab78d8efab13487575218820f8b0455248d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="c4c4f-102">ServicePointManager.s\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="c4c4f-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="c4c4f-103">`ServicePointManager.s_ServicePointTable`是<xref:System.Collections.Hashtable>其中包含的活动的 HTTP 连接的列表 (<xref:System.Net.ServicePoint>s) 中<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="c4c4f-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4c4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4c4f-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="c4c4f-105">`ServicePointManager.s_ServicePointTable`字段是私有，且不是在你的代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="c4c4f-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="c4c4f-106">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="c4c4f-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4c4f-107">惠?</span><span class="sxs-lookup"><span data-stu-id="c4c4f-107">Requirements</span></span>

<span data-ttu-id="c4c4f-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c4c4f-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c4c4f-109">**程序集：**系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="c4c4f-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c4c4f-110">**.NET framework 版本：**自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="c4c4f-110">**.NET Framework versions:** Available since 2.0.</span></span>
