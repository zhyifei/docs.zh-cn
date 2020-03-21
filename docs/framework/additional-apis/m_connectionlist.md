---
title: 连接组.m_ConnectionList字段
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
ms.openlocfilehash: 8eb6f215c36e214f7095eeba90bf0aed66dfcea0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155845"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="50c5a-102">连接组.m\_连接列表字段</span><span class="sxs-lookup"><span data-stu-id="50c5a-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="50c5a-103">`ConnectionGroup.m_ConnectionList`是一<xref:System.Collections.ArrayList>个连接对象，用于相同的 URI，并为某些其他属性（如过期和身份验证）共享相同的值。</span><span class="sxs-lookup"><span data-stu-id="50c5a-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="50c5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="50c5a-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="50c5a-105">该`ConnectionGroup.m_ConnectionList`字段是私有的，不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="50c5a-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="50c5a-106">在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="50c5a-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="50c5a-107">要求</span><span class="sxs-lookup"><span data-stu-id="50c5a-107">Requirements</span></span>

<span data-ttu-id="50c5a-108">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="50c5a-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="50c5a-109">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="50c5a-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="50c5a-110">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="50c5a-110">**.NET Framework versions:** Available since 2.0.</span></span>
