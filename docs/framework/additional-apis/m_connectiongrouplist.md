---
title: ServicePoint. m_ConnectionGroupList 字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1991dae4d03f617857b860f920077531f7937bf1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120051"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="7a4c2-102">ServicePoint\_ConnectionGroupList 字段</span><span class="sxs-lookup"><span data-stu-id="7a4c2-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="7a4c2-103">`ServicePoint.m_ConnectionGroupList` 是连接组的 <xref:System.Collections.Hashtable>，每个组都具有 <xref:System.Net.ServicePoint>URI 的连接。</span><span class="sxs-lookup"><span data-stu-id="7a4c2-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a4c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a4c2-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="7a4c2-105">`ServicePoint.m_ConnectionGroupList` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="7a4c2-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="7a4c2-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="7a4c2-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a4c2-107">要求</span><span class="sxs-lookup"><span data-stu-id="7a4c2-107">Requirements</span></span>

<span data-ttu-id="7a4c2-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7a4c2-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7a4c2-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="7a4c2-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7a4c2-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="7a4c2-110">**.NET Framework versions:** Available since 2.0.</span></span>
