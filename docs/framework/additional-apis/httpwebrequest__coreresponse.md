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
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest。\_CoreResponse 字段

`HttpWebRequest._CoreResponse` 是一个对象 (任一[CoreResponseData](coreresponsedata.md)或<xref:System.Exception>) 包含的 HTTP 响应分析结果。

## <a name="syntax"></a>语法
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 此 API 不是在代码中直接使用。 相反，应使用<xref:System.Diagnostics.DiagnosticSource>连接网络的代码。 请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。
> 
> Microsoft 不支持在生产应用程序在任何情况下使用此类。

## <a name="requirements"></a>要求

**Namespace:** <xref:System.Net>

**程序集：** 系统 （在 System.dll)

**.NET framework 版本：** 自 2.0 之后可用。
