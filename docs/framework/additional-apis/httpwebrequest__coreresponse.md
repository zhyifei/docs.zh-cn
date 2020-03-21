---
title: httpWeb请求._CoreResponse字段
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155916"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWeb请求。\_核心响应字段

`HttpWebRequest._CoreResponse`是包含 HTTP 响应分析结果的对象（[核心响应数据](coreresponsedata.md)或<xref:System.Exception>）。

## <a name="syntax"></a>语法
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 此 API 不应直接用于代码。 相反，您应该使用 挂钩<xref:System.Diagnostics.DiagnosticSource>网络代码。 请参阅[诊断源用户指南](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此类。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
