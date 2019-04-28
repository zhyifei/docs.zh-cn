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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706060"
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest。\_CoreResponse 字段

`HttpWebRequest._CoreResponse` 是一个对象 (任一[CoreResponseData](coreresponsedata.md)或<xref:System.Exception>) 包含的 HTTP 响应分析结果。

## <a name="syntax"></a>语法
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 此 API 不应在代码中直接使用。 相反，应使用<xref:System.Diagnostics.DiagnosticSource>挂接网络代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> 在生产应用程序在任何情况下，Microsoft 不支持此类使用。

## <a name="requirements"></a>要求

**Namespace**：<xref:System.Net>

**程序集：**（在 System.dll) 的系统

**.NET framework 版本：** 自 2.0 之后可用。
