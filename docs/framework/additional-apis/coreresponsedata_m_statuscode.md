---
title: CoreResponseData.m_StatusCode 字段
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
ms.openlocfilehash: 53338c75d31cef3ab89879632710dba3e52091ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675398"
---
# <a name="coreresponsedatamstatuscode-field"></a>CoreResponseData.m\_StatusCode 字段

`CoreResponseData.m_StatusCode` 是<xref:System.Net.HttpStatusCode>包含响应的状态。

## <a name="syntax"></a>语法
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用<xref:System.Diagnostics.DiagnosticSource>挂接网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在生产应用程序在任何情况下，Microsoft 不支持此类使用。

## <a name="requirements"></a>要求

**Namespace**：<xref:System.Net>

**程序集：**（在 System.dll) 的系统

**.NET framework 版本：** 自 2.0 之后可用。
