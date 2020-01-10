---
title: CoreResponseData 类
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: fd0ffb982c22b0a8b6cb5dd677faafb9921bf5d9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741017"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="fc4c9-102">CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="fc4c9-102">CoreResponseData Class</span></span>

<span data-ttu-id="fc4c9-103">`CoreResponseData` 类表示 HTTP 标头和响应正文的分析。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc4c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc4c9-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="fc4c9-105">此 API 是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="fc4c9-106">相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="fc4c9-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="fc4c9-108">在任何情况下，Microsoft 不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc4c9-109">需求</span><span class="sxs-lookup"><span data-stu-id="fc4c9-109">Requirements</span></span>

<span data-ttu-id="fc4c9-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fc4c9-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fc4c9-111">**程序集**：系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="fc4c9-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="fc4c9-112">**.NET framework 版本**：自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="fc4c9-112">**.NET Framework versions:** Available since 2.0.</span></span>
