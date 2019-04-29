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
# <a name="coreresponsedatamresponseheaders-field"></a>CoreResponseData.m\_ResponseHeaders 字段

`CoreResponseData.m_ResponseHeaders` 是<xref:System.Net.WebHeaderCollection>与服务器的响应关联的标头。

## <a name="syntax"></a>语法
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用<xref:System.Diagnostics.DiagnosticSource>挂接网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在生产应用程序在任何情况下，Microsoft 不支持此类使用。

## <a name="requirements"></a>要求

**Namespace**：<xref:System.Net>

**程序集：**（在 System.dll) 的系统

**.NET framework 版本：** 自 2.0 之后可用。
