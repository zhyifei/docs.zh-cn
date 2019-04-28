---
title: ServicePointManager.s_ServicePointTable Field
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ebcf5c3f13b3bd30a8e091be09ae546eee1eaffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675437"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="7b1fc-102">ServicePointManager.s\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="7b1fc-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="7b1fc-103">`ServicePointManager.s_ServicePointTable` 是<xref:System.Collections.Hashtable>包含活动的 HTTP 连接的列表 (<xref:System.Net.ServicePoint>s) 中<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="7b1fc-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b1fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b1fc-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="7b1fc-105">`ServicePointManager.s_ServicePointTable`字段是私有的不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="7b1fc-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="7b1fc-106">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="7b1fc-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b1fc-107">要求</span><span class="sxs-lookup"><span data-stu-id="7b1fc-107">Requirements</span></span>

<span data-ttu-id="7b1fc-108">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7b1fc-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7b1fc-109">**程序集：**（在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="7b1fc-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7b1fc-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="7b1fc-110">**.NET Framework versions:** Available since 2.0.</span></span>
