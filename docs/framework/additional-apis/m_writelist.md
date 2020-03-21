---
title: 连接.m_WriteList字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
ms.openlocfilehash: 6c60831ddf23ce8ac9afcf244383d24732c3ef8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155832"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="30932-102">连接.m\_写入列表字段</span><span class="sxs-lookup"><span data-stu-id="30932-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="30932-103">`Connection.m_WriteList`<xref:System.Collections.ArrayList>是排队通过<xref:System.Net.HttpWebRequest>HTTP 发送的对象。</span><span class="sxs-lookup"><span data-stu-id="30932-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="30932-104">语法</span><span class="sxs-lookup"><span data-stu-id="30932-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="30932-105">该`Connection.m_WriteList`字段是私有的，不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="30932-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="30932-106">在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="30932-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="30932-107">要求</span><span class="sxs-lookup"><span data-stu-id="30932-107">Requirements</span></span>

<span data-ttu-id="30932-108">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="30932-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="30932-109">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="30932-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="30932-110">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="30932-110">**.NET Framework versions:** Available since 2.0.</span></span>
