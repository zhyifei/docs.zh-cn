---
title: ICorDebugLoadedModule::GetSize 方法
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183464"
---
# <a name="icordebugloadedmodulegetsize-method"></a>ICorDebugLoadedModule::GetSize 方法
获取加载模块的大小（以字节为单位）。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>参数  
 `pcBytes`  
 [out] 指向已加载模块中字节数的指针。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugLoadedModule 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
