---
title: httpWeb请求._CoreResponse字段
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155916"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="2cee1-102">HttpWeb请求。\_核心响应字段</span><span class="sxs-lookup"><span data-stu-id="2cee1-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="2cee1-103">`HttpWebRequest._CoreResponse`是包含 HTTP 响应分析结果的对象（[核心响应数据](coreresponsedata.md)或<xref:System.Exception>）。</span><span class="sxs-lookup"><span data-stu-id="2cee1-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cee1-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cee1-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="2cee1-105">此 API 不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="2cee1-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="2cee1-106">相反，您应该使用 挂钩<xref:System.Diagnostics.DiagnosticSource>网络代码。</span><span class="sxs-lookup"><span data-stu-id="2cee1-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="2cee1-107">请参阅[诊断源用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="2cee1-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="2cee1-108">在任何情况下，Microsoft 都不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="2cee1-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2cee1-109">要求</span><span class="sxs-lookup"><span data-stu-id="2cee1-109">Requirements</span></span>

<span data-ttu-id="2cee1-110">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2cee1-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2cee1-111">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="2cee1-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2cee1-112">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="2cee1-112">**.NET Framework versions:** Available since 2.0.</span></span>
