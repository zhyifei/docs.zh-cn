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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743155"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="44353-102">Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="44353-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="44353-103">`Connection.m_WriteList` 是<xref:System.Collections.ArrayList>的<xref:System.Net.HttpWebRequest>排队等待通过 HTTP 发送的对象。</span><span class="sxs-lookup"><span data-stu-id="44353-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="44353-104">语法</span><span class="sxs-lookup"><span data-stu-id="44353-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="44353-105">`Connection.m_WriteList`字段是私有，且不是在你的代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="44353-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="44353-106">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="44353-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="44353-107">要求</span><span class="sxs-lookup"><span data-stu-id="44353-107">Requirements</span></span>

<span data-ttu-id="44353-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="44353-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="44353-109">**程序集：** 系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="44353-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="44353-110">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="44353-110">**.NET Framework versions:** Available since 2.0.</span></span>
