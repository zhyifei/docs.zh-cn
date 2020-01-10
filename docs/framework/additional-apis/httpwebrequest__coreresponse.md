---
title: HttpWebRequest 字段 _CoreResponse
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740448"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="c0c93-102">HttpWebRequest.\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="c0c93-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="c0c93-103">`HttpWebRequest._CoreResponse` 是包含 HTTP 响应分析结果的对象（ [CoreResponseData](coreresponsedata.md)或 <xref:System.Exception>）。</span><span class="sxs-lookup"><span data-stu-id="c0c93-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0c93-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0c93-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="c0c93-105">此 API 不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="c0c93-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="c0c93-106">相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。</span><span class="sxs-lookup"><span data-stu-id="c0c93-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c0c93-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="c0c93-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="c0c93-108">在任何情况下，Microsoft 不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="c0c93-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0c93-109">需求</span><span class="sxs-lookup"><span data-stu-id="c0c93-109">Requirements</span></span>

<span data-ttu-id="c0c93-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c0c93-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c0c93-111">**程序集**：系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="c0c93-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c0c93-112">**.NET framework 版本**：自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="c0c93-112">**.NET Framework versions:** Available since 2.0.</span></span>
