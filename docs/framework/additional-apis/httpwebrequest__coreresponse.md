---
title: HttpWebRequest._CoreResponse 字段
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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356194"
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="76b36-102">HttpWebRequest。\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="76b36-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="76b36-103">`HttpWebRequest._CoreResponse` 是一个对象 (任一[CoreResponseData](coreresponsedata.md)或<xref:System.Exception>) 包含的 HTTP 响应分析结果。</span><span class="sxs-lookup"><span data-stu-id="76b36-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="76b36-104">语法</span><span class="sxs-lookup"><span data-stu-id="76b36-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="76b36-105">此 API 不是在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="76b36-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="76b36-106">相反，应使用<xref:System.Diagnostics.DiagnosticSource>连接网络的代码。</span><span class="sxs-lookup"><span data-stu-id="76b36-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="76b36-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="76b36-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="76b36-108">Microsoft 不支持在生产应用程序在任何情况下使用此类。</span><span class="sxs-lookup"><span data-stu-id="76b36-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="76b36-109">要求</span><span class="sxs-lookup"><span data-stu-id="76b36-109">Requirements</span></span>

<span data-ttu-id="76b36-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="76b36-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="76b36-111">**程序集：** 系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="76b36-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="76b36-112">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="76b36-112">**.NET Framework versions:** Available since 2.0.</span></span>
