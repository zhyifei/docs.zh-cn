---
title: HttpWebRequest 字段 _HttpResponse
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
ms.openlocfilehash: 236298921ecd286ddba4e74dbce1b63e96055412
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215097"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="22a56-102">HttpWebRequest.\_Httpresponse.cache 字段</span><span class="sxs-lookup"><span data-stu-id="22a56-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="22a56-103">`HttpWebRequest._HttpResponse` 是包含 HTTP 请求中的 HTTP 响应详细信息的 <xref:System.Net.HttpWebResponse>。</span><span class="sxs-lookup"><span data-stu-id="22a56-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="22a56-104">在收到 HTTP 响应之前，可以 `null`。</span><span class="sxs-lookup"><span data-stu-id="22a56-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="22a56-105">语法</span><span class="sxs-lookup"><span data-stu-id="22a56-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="22a56-106">`HttpWebRequest._HttpResponse` 字段是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="22a56-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="22a56-107">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="22a56-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="22a56-108">要求</span><span class="sxs-lookup"><span data-stu-id="22a56-108">Requirements</span></span>

<span data-ttu-id="22a56-109">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="22a56-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="22a56-110">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="22a56-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="22a56-111">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="22a56-111">**.NET Framework versions:** Available since 2.0.</span></span>
