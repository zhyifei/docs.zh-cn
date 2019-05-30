---
title: Connection.m_WriteList 字段
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d138e0490e849ff26f540077ec7d23ae42737606
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300906"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="41ffa-102">Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="41ffa-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="41ffa-103">`Connection.m_WriteList` 是<xref:System.Collections.ArrayList>的<xref:System.Net.HttpWebRequest>排队等待通过 HTTP 发送的对象。</span><span class="sxs-lookup"><span data-stu-id="41ffa-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="41ffa-104">语法</span><span class="sxs-lookup"><span data-stu-id="41ffa-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="41ffa-105">`Connection.m_WriteList`字段是私有的不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="41ffa-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="41ffa-106">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="41ffa-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="41ffa-107">要求</span><span class="sxs-lookup"><span data-stu-id="41ffa-107">Requirements</span></span>

<span data-ttu-id="41ffa-108">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="41ffa-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="41ffa-109">**程序集：** （在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="41ffa-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="41ffa-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="41ffa-110">**.NET Framework versions:** Available since 2.0.</span></span>
