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
ms.openlocfilehash: 39a14a3df5059cc47cd4879e4d4ba351cc7b655b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156111"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="70ff2-102">CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="70ff2-102">CoreResponseData Class</span></span>

<span data-ttu-id="70ff2-103">类`CoreResponseData`表示 HTTP 标头和响应正文的解析。</span><span class="sxs-lookup"><span data-stu-id="70ff2-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="70ff2-104">语法</span><span class="sxs-lookup"><span data-stu-id="70ff2-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="70ff2-105">此 API 是内部的，它不打算直接用于您的代码。</span><span class="sxs-lookup"><span data-stu-id="70ff2-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="70ff2-106">相反，您应该使用 挂钩<xref:System.Diagnostics.DiagnosticSource>网络代码。</span><span class="sxs-lookup"><span data-stu-id="70ff2-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="70ff2-107">请参阅[诊断源用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="70ff2-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="70ff2-108">在任何情况下，Microsoft 都不支持在生产应用程序中使用此类。</span><span class="sxs-lookup"><span data-stu-id="70ff2-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="70ff2-109">要求</span><span class="sxs-lookup"><span data-stu-id="70ff2-109">Requirements</span></span>

<span data-ttu-id="70ff2-110">**命名空间：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="70ff2-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="70ff2-111">**装配：** 系统（系统中）</span><span class="sxs-lookup"><span data-stu-id="70ff2-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="70ff2-112">**.NET 框架版本：** 自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="70ff2-112">**.NET Framework versions:** Available since 2.0.</span></span>
