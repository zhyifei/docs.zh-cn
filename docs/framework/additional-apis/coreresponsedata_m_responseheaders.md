---
title: CoreResponseData 字段 m_ResponseHeaders
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
ms.openlocfilehash: df0b592a5f85d4c99dee4ecb60963f4abb560a13
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741008"
---
# <a name="coreresponsedatam_responseheaders-field"></a>CoreResponseData\_ResponseHeaders 字段

`CoreResponseData.m_ResponseHeaders` 是与服务器响应关联的标头的 <xref:System.Net.WebHeaderCollection>。

## <a name="syntax"></a>语法
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用 <xref:System.Diagnostics.DiagnosticSource> 挂钩网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此类。

## <a name="requirements"></a>需求

**Namespace**：<xref:System.Net>

**程序集**：系统 （在 System.dll)

**.NET framework 版本**：自 2.0 之后可用。
