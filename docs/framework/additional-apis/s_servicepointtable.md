---
title: ServicePointManager. s_ServicePointTable 字段
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120004"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="daa88-102">ServicePointManager\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="daa88-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="daa88-103">`ServicePointManager.s_ServicePointTable` 是包含 <xref:System.AppDomain>中的活动 HTTP 连接（<xref:System.Net.ServicePoint>）列表的 <xref:System.Collections.Hashtable>。</span><span class="sxs-lookup"><span data-stu-id="daa88-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="daa88-104">语法</span><span class="sxs-lookup"><span data-stu-id="daa88-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="daa88-105">`ServicePointManager.s_ServicePointTable` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="daa88-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="daa88-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="daa88-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="daa88-107">要求</span><span class="sxs-lookup"><span data-stu-id="daa88-107">Requirements</span></span>

<span data-ttu-id="daa88-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="daa88-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="daa88-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="daa88-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="daa88-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="daa88-110">**.NET Framework versions:** Available since 2.0.</span></span>
