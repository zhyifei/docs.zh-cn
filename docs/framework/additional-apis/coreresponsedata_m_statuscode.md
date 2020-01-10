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
# <a name="coreresponsedatam_statuscode-field"></a>CoreResponseData\_StatusCode 字段

`CoreResponseData.m_StatusCode` 是包含响应状态的 <xref:System.Net.HttpStatusCode>。

## <a name="syntax"></a>语法
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此类。

## <a name="requirements"></a>需求

**Namespace**：<xref:System.Net>

**程序集**：系统 （在 System.dll)

**.NET framework 版本**：自 2.0 之后可用。
