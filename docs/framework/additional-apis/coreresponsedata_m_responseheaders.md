---
title: CoreResponseData 字段 m_ResponseHeaders
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: df0b592a5f85d4c99dee4ecb60963f4abb560a13
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741008"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="c8a14-102">CoreResponseData\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="c8a14-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="c8a14-103">`CoreResponseData.m_ResponseHeaders` 是与服务器响应关联的标头的 <xref:System.Net.WebHeaderCollection>。</span><span class="sxs-lookup"><span data-stu-id="c8a14-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8a14-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8a14-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="c8a14-105">此 API 不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="c8a14-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="c8a14-106">相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。</span><span class="sxs-lookup"><span data-stu-id="c8a14-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c8a14-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a14-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="c8a14-108">在任何情况下，Microsoft 不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="c8a14-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8a14-109">需求</span><span class="sxs-lookup"><span data-stu-id="c8a14-109">Requirements</span></span>

<span data-ttu-id="c8a14-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c8a14-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c8a14-111">**程序集**：系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="c8a14-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c8a14-112">**.NET framework 版本**：自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="c8a14-112">**.NET Framework versions:** Available since 2.0.</span></span>
