---
title: "ICorDebugMergedAssemblyRecord::GetCulture 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7963d311707d12aa697c606605f9a34b6f65d1eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>ICorDebugMergedAssemblyRecord::GetCulture 方法
获取程序集的区域性名称字符串。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cchCulture`  
 [in] `szCulture` 缓冲区中的字符数。  
  
 `pcchCulture`  
 [out] 实际写入 `szCulture` 缓冲区的字符数。  
  
 `szCulture`  
 [out] 包含区域性名称的字符数组。  
  
## <a name="remarks"></a>备注  
 区域性名称是用于标识区域性的唯一字符串，例如“EN-US”（针对美式英语区域性）或“neutral”（针对非特定区域性）。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugMergedAssemblyRecord 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
