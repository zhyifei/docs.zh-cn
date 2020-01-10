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
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest.\_CoreResponse 字段

`HttpWebRequest._CoreResponse` 是包含 HTTP 响应分析结果的对象（ [CoreResponseData](coreresponsedata.md)或 <xref:System.Exception>）。

## <a name="syntax"></a>语法
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此类。

## <a name="requirements"></a>需求

**Namespace**：<xref:System.Net>

**程序集**：系统 （在 System.dll)

**.NET framework 版本**：自 2.0 之后可用。
