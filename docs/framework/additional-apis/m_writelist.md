---
title: "Connection.m_WriteList 字段"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.Connection.m_WriteList
api_location: System.dll
api_type: Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3849fdd327923e480cd88c932cfdce6580d3f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="f03c7-102">Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="f03c7-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="f03c7-103">`Connection.m_WriteList`是<xref:System.Collections.ArrayList>的<xref:System.Net.HttpWebRequest>排队等待通过 HTTP 发送的对象。</span><span class="sxs-lookup"><span data-stu-id="f03c7-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="f03c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="f03c7-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="f03c7-105">`Connection.m_WriteList`字段是私有，且不是在你的代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="f03c7-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="f03c7-106">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="f03c7-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f03c7-107">惠?</span><span class="sxs-lookup"><span data-stu-id="f03c7-107">Requirements</span></span>

<span data-ttu-id="f03c7-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f03c7-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f03c7-109">**程序集：**系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="f03c7-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f03c7-110">**.NET framework 版本：**自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="f03c7-110">**.NET Framework versions:** Available since 2.0.</span></span>
