---
title: M_WriteList 字段
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120029"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="1f709-102">Connection\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="1f709-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="1f709-103">`Connection.m_WriteList` 是排队等待通过 HTTP 发送的 <xref:System.Net.HttpWebRequest> 对象的 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="1f709-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f709-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f709-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="1f709-105">`Connection.m_WriteList` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="1f709-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="1f709-106">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="1f709-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f709-107">要求</span><span class="sxs-lookup"><span data-stu-id="1f709-107">Requirements</span></span>

<span data-ttu-id="1f709-108">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1f709-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1f709-109">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="1f709-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="1f709-110">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="1f709-110">**.NET Framework versions:** Available since 2.0.</span></span>
