---
title: ConnectionGroup 字段 m_ConnectionList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
ms.openlocfilehash: d53eeb54d212adb011dae138e103ea5b30f7fb99
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215541"
---
# <a name="connectiongroupm_connectionlist-field"></a>ConnectionGroup\_ConnectionList 字段

`ConnectionGroup.m_ConnectionList` 是为同一 URI 提供服务的连接对象 <xref:System.Collections.ArrayList>，并为到期和身份验证等其他某些属性共享相同的值。

## <a name="syntax"></a>语法
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> `ConnectionGroup.m_ConnectionList` 字段是专用的，不应在代码中直接使用。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.Net>

**程序集：** 系统（在 System.web 中）

**.NET Framework 版本：** 自2.0 起可用。
