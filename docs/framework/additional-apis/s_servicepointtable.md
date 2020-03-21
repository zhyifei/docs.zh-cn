---
title: 服务点管理器.s_ServicePointTable字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155803"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="0b970-102">服务点管理器的服务\_点表字段</span><span class="sxs-lookup"><span data-stu-id="0b970-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="0b970-103">`ServicePointManager.s_ServicePointTable`是<xref:System.Collections.Hashtable>包含 中的活动 HTTP 连接的列表<xref:System.Net.ServicePoint>的<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="0b970-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b970-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b970-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="0b970-105">该`ServicePointManager.s_ServicePointTable`字段是私有的，不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="0b970-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0b970-106">在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="0b970-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b970-107">要求</span><span class="sxs-lookup"><span data-stu-id="0b970-107">Requirements</span></span>

<span data-ttu-id="0b970-108">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0b970-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0b970-109">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="0b970-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="0b970-110">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="0b970-110">**.NET Framework versions:** Available since 2.0.</span></span>
