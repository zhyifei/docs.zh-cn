---
title: CoreResponseData.m_ResponseHeaders 字段
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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705969"
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="e73ac-102">CoreResponseData.m\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="e73ac-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="e73ac-103">`CoreResponseData.m_ResponseHeaders` 是<xref:System.Net.WebHeaderCollection>与服务器的响应关联的标头。</span><span class="sxs-lookup"><span data-stu-id="e73ac-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="e73ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="e73ac-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="e73ac-105">此 API 不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="e73ac-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="e73ac-106">相反，应使用<xref:System.Diagnostics.DiagnosticSource>挂接网络代码。</span><span class="sxs-lookup"><span data-stu-id="e73ac-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="e73ac-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="e73ac-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="e73ac-108">在生产应用程序在任何情况下，Microsoft 不支持此类使用。</span><span class="sxs-lookup"><span data-stu-id="e73ac-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e73ac-109">要求</span><span class="sxs-lookup"><span data-stu-id="e73ac-109">Requirements</span></span>

<span data-ttu-id="e73ac-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e73ac-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e73ac-111">**程序集：**（在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="e73ac-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e73ac-112">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="e73ac-112">**.NET Framework versions:** Available since 2.0.</span></span>
