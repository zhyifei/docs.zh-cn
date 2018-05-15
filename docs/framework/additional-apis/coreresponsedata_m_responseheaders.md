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
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="4f99c-102">CoreResponseData.m\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="4f99c-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="4f99c-103">`CoreResponseData.m_ResponseHeaders` 是<xref:System.Net.WebHeaderCollection>与服务器响应关联的标头。</span><span class="sxs-lookup"><span data-stu-id="4f99c-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f99c-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f99c-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="4f99c-105">此 API 不是在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="4f99c-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="4f99c-106">相反，应使用<xref:System.Diagnostics.DiagnosticSource>连接网络的代码。</span><span class="sxs-lookup"><span data-stu-id="4f99c-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="4f99c-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="4f99c-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="4f99c-108">Microsoft 不支持在生产应用程序在任何情况下使用此类。</span><span class="sxs-lookup"><span data-stu-id="4f99c-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f99c-109">要求</span><span class="sxs-lookup"><span data-stu-id="4f99c-109">Requirements</span></span>

<span data-ttu-id="4f99c-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4f99c-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4f99c-111">**程序集：** 系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="4f99c-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4f99c-112">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="4f99c-112">**.NET Framework versions:** Available since 2.0.</span></span>
