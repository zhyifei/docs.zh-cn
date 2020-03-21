---
title: httpWeb请求._HttpResponse字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._HttpResponse
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: eab9b789-beb4-4c28-b2d8-78debc7ba129
ms.openlocfilehash: 0c5bfc56299aa06dd59c2598588044e81a69933a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156241"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="a84c5-102">HttpWeb请求。\_Http 响应字段</span><span class="sxs-lookup"><span data-stu-id="a84c5-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="a84c5-103">`HttpWebRequest._HttpResponse`是<xref:System.Net.HttpWebResponse>包含 HTTP 请求的 HTTP 响应详细信息。</span><span class="sxs-lookup"><span data-stu-id="a84c5-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="a84c5-104">它可以直到`null`收到 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="a84c5-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="a84c5-105">语法</span><span class="sxs-lookup"><span data-stu-id="a84c5-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="a84c5-106">该`HttpWebRequest._HttpResponse`字段是内部字段，不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="a84c5-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a84c5-107">在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="a84c5-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a84c5-108">要求</span><span class="sxs-lookup"><span data-stu-id="a84c5-108">Requirements</span></span>

<span data-ttu-id="a84c5-109">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a84c5-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a84c5-110">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="a84c5-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a84c5-111">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="a84c5-111">**.NET Framework versions:** Available since 2.0.</span></span>
