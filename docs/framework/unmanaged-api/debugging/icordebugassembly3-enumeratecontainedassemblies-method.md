---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa99e7289e0e86032f7bb85bbe209932f5c50d16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627572"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>ICorDebugAssembly3::EnumerateContainedAssemblies 方法
获取该程序集中所包含的程序集的枚举器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppAssemblies`  
 [out]指向一个 ICorDebugAssemblyEnum 接口对象，它枚举器的地址的指针。  
  
## <a name="return-value"></a>返回值  
 `S_OK` 若该 `ICorDebugAssembly3` 对象为容器；反之，`S_FALSE`，枚举为空。  
  
## <a name="remarks"></a>备注  
 需用符号来列举包含的程序集。 如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugAssembly3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
