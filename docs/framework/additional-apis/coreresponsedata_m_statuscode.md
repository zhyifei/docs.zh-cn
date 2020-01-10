---
title: CoreResponseData 字段 m_StatusCode
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_StatusCode
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 8abe619a57cc61fc3502807f60deccbbd578f382
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741001"
---
# <a name="coreresponsedatam_statuscode-field"></a><span data-ttu-id="acc2a-102">CoreResponseData\_StatusCode 字段</span><span class="sxs-lookup"><span data-stu-id="acc2a-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="acc2a-103">`CoreResponseData.m_StatusCode` 是包含响应状态的 <xref:System.Net.HttpStatusCode>。</span><span class="sxs-lookup"><span data-stu-id="acc2a-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="acc2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="acc2a-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="acc2a-105">此 API 不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="acc2a-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="acc2a-106">相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。</span><span class="sxs-lookup"><span data-stu-id="acc2a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="acc2a-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="acc2a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="acc2a-108">在任何情况下，Microsoft 不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="acc2a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="acc2a-109">需求</span><span class="sxs-lookup"><span data-stu-id="acc2a-109">Requirements</span></span>

<span data-ttu-id="acc2a-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="acc2a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="acc2a-111">**程序集**：系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="acc2a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="acc2a-112">**.NET framework 版本**：自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="acc2a-112">**.NET Framework versions:** Available since 2.0.</span></span>
