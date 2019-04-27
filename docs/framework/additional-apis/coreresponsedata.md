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
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675411"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="02fd6-102">CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="02fd6-102">CoreResponseData Class</span></span>

<span data-ttu-id="02fd6-103">`CoreResponseData`类表示分析 HTTP 标头和响应正文。</span><span class="sxs-lookup"><span data-stu-id="02fd6-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="02fd6-104">语法</span><span class="sxs-lookup"><span data-stu-id="02fd6-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="02fd6-105">内部，此 API，但并不在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="02fd6-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="02fd6-106">相反，应使用<xref:System.Diagnostics.DiagnosticSource>挂接网络代码。</span><span class="sxs-lookup"><span data-stu-id="02fd6-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="02fd6-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="02fd6-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="02fd6-108">在生产应用程序在任何情况下，Microsoft 不支持此类使用。</span><span class="sxs-lookup"><span data-stu-id="02fd6-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="02fd6-109">要求</span><span class="sxs-lookup"><span data-stu-id="02fd6-109">Requirements</span></span>

<span data-ttu-id="02fd6-110">**Namespace**：<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="02fd6-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="02fd6-111">**程序集：**（在 System.dll) 的系统</span><span class="sxs-lookup"><span data-stu-id="02fd6-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="02fd6-112">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="02fd6-112">**.NET Framework versions:** Available since 2.0.</span></span>
