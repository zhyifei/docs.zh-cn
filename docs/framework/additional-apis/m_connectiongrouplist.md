---
title: 服务点.m_ConnectionGroupList字段
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
ms.openlocfilehash: 2b1b46085ed035b67fd01447727b406fe3895980
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155890"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="c6f64-102">服务点.m\_连接组列表字段</span><span class="sxs-lookup"><span data-stu-id="c6f64-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="c6f64-103">`ServicePoint.m_ConnectionGroupList`是连接<xref:System.Collections.Hashtable>组，每个组都持有<xref:System.Net.ServicePoint>URI 的连接。</span><span class="sxs-lookup"><span data-stu-id="c6f64-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6f64-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="c6f64-105">该`ServicePoint.m_ConnectionGroupList`字段是私有的，不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="c6f64-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c6f64-106">在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="c6f64-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6f64-107">要求</span><span class="sxs-lookup"><span data-stu-id="c6f64-107">Requirements</span></span>

<span data-ttu-id="c6f64-108">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c6f64-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c6f64-109">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="c6f64-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c6f64-110">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="c6f64-110">**.NET Framework versions:** Available since 2.0.</span></span>
