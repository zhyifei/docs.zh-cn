---
title: 核心响应数据.m_StatusCode字段
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
ms.openlocfilehash: dfed9a748e959f0f751408566c7cbb4d2fa13e3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156068"
---
# <a name="coreresponsedatam_statuscode-field"></a>核心响应数据.m\_状态代码字段

`CoreResponseData.m_StatusCode`包含<xref:System.Net.HttpStatusCode>响应的状态。

## <a name="syntax"></a>语法
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> 此 API 不应直接用于代码。 相反，您应该使用 挂钩<xref:System.Diagnostics.DiagnosticSource>网络代码。 请参阅[诊断源用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此类。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
