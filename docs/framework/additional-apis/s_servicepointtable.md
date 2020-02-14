---
title: ServicePointManager 字段 s_ServicePointTable
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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214921"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="a150f-102">ServicePointManager\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="a150f-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="a150f-103">`ServicePointManager.s_ServicePointTable` 是包含 <xref:System.AppDomain>中的活动 HTTP 连接（<xref:System.Net.ServicePoint>）列表的 <xref:System.Collections.Hashtable>。</span><span class="sxs-lookup"><span data-stu-id="a150f-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="a150f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a150f-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="a150f-105">`ServicePointManager.s_ServicePointTable` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a150f-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a150f-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="a150f-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a150f-107">要求</span><span class="sxs-lookup"><span data-stu-id="a150f-107">Requirements</span></span>

<span data-ttu-id="a150f-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a150f-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a150f-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="a150f-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a150f-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="a150f-110">**.NET Framework versions:** Available since 2.0.</span></span>
