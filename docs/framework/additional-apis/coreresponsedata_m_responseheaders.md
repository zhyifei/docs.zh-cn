---
title: 核心响应数据.m_ResponseHeaders字段
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
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156098"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="d85d9-102">核心响应数据.m\_响应标题字段</span><span class="sxs-lookup"><span data-stu-id="d85d9-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="d85d9-103">`CoreResponseData.m_ResponseHeaders`是与<xref:System.Net.WebHeaderCollection>服务器响应关联的标头。</span><span class="sxs-lookup"><span data-stu-id="d85d9-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="d85d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="d85d9-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="d85d9-105">此 API 不应直接用于代码。</span><span class="sxs-lookup"><span data-stu-id="d85d9-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="d85d9-106">相反，您应该使用 挂钩<xref:System.Diagnostics.DiagnosticSource>网络代码。</span><span class="sxs-lookup"><span data-stu-id="d85d9-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="d85d9-107">请参阅[诊断源用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="d85d9-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="d85d9-108">在任何情况下，Microsoft 都不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="d85d9-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d85d9-109">要求</span><span class="sxs-lookup"><span data-stu-id="d85d9-109">Requirements</span></span>

<span data-ttu-id="d85d9-110">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d85d9-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d85d9-111">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="d85d9-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d85d9-112">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="d85d9-112">**.NET Framework versions:** Available since 2.0.</span></span>
