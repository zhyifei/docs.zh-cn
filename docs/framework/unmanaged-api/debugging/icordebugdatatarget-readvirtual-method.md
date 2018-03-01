---
title: "ICorDebugDataTarget::ReadVirtual 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a406af14d4cb5612009972542c0efe9c1b5f62cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual 方法
获取指定的地址处开始的连续内存块，并在提供的缓冲区中将其返回。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]起始地址的请求的内存。  
  
 `pbuffer`  
 [out]将存储内存缓冲区。  
  
 `bytesRequested`  
 [in]要获得的目标地址的字节数。  
  
 `pBytesRead`  
 [out]从目标地址实际读取的字节数。 这可能是数不能超过`bytesRequested`。  
  
## <a name="remarks"></a>备注  
 如果可以读取 （在指定的开始地址中） 的第一个字节，则调用应返回成功 （用于支持高效读取使用自我描述长度，如以 null 结尾的字符串的数据结构）。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
