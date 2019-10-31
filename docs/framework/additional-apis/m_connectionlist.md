---
title: ConnectionGroup. m_ConnectionList 字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a06e535c554f765161d619d97f2e70072fbd0d5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120007"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="01485-102">ConnectionGroup\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="01485-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="01485-103">`ConnectionGroup.m_ConnectionList` 是为同一 URI 提供服务的连接对象 <xref:System.Collections.ArrayList>，并为到期和身份验证等其他某些属性共享相同的值。</span><span class="sxs-lookup"><span data-stu-id="01485-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="01485-104">语法</span><span class="sxs-lookup"><span data-stu-id="01485-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="01485-105">`ConnectionGroup.m_ConnectionList` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="01485-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="01485-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="01485-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="01485-107">要求</span><span class="sxs-lookup"><span data-stu-id="01485-107">Requirements</span></span>

<span data-ttu-id="01485-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="01485-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="01485-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="01485-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="01485-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="01485-110">**.NET Framework versions:** Available since 2.0.</span></span>
