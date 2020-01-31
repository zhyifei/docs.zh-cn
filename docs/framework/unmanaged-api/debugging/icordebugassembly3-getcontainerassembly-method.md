---
title: ICorDebugAssembly3::GetContainerAssembly 方法
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778073"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>ICorDebugAssembly3::GetContainerAssembly 方法
返回该 `ICorDebugAssembly3` 对象的容器程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppAssembly`  
 指向表示容器程序集的 ICorDebugAssembly 对象地址的指针; 如果方法调用失败，则为**null** 。  
  
## <a name="return-value"></a>返回值  
 如果方法调用成功，则为 `S_OK`;否则，`S_FALSE`和 `ppAssembly` 为**null**。  
  
## <a name="remarks"></a>备注  
 如果程序集和单独容器程序集内的其他程序集合并，则方法返回容器程序集。 有关详细信息和术语，请参阅[ICorDebugProcess6：： EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md)主题。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugAssembly3 接口](icordebugassembly3-interface.md)
- [调试接口](debugging-interfaces.md)
