---
title: "ICorDebugAppDomain::GetObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8206c6e5efbee8522f425f9078d99a39bbdd42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject 方法
公共语言运行时 (CLR) 应用程序域中获取的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppObject`  
 [out]指向一个 ICorDebugValue 接口对象，表示 CLR 应用程序域的地址的指针。  
  
## <a name="return-value"></a>返回值  
 如果托管<xref:System.AppDomain?displayProperty=nameWithType>对象尚未为此应用程序域中构造，该方法返回`S_FALSE`并放置`NULL`中`*ppObject`。  
  
## <a name="remarks"></a>备注  
 每个应用程序域的过程中可能具有托管<xref:System.AppDomain?displayProperty=nameWithType>表示它的运行时中的对象。 此函数获取对应于此管理的 ICorDebugValue 接口对象<xref:System.AppDomain?displayProperty=nameWithType>对象。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
