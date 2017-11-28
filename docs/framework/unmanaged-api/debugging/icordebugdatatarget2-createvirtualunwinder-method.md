---
title: "ICorDebugDataTarget2::CreateVirtualUnwinder 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 421cff28e84106c0859889e6f9e99e870b469a98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>ICorDebugDataTarget2::CreateVirtualUnwinder 方法
创建一个从初始上下文（不一定是线程叶）开始展开的新堆栈开卷机。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a>参数  
 本机线程ID  
 [输入] 线程（其堆栈未展开）的本机线程 ID。  
  
 上下文标记  
 [输入] `initialContext` 中规定了指定上下文部分的标记。  
  
 cb上下文  
 [输入] `initialContext` 的大小。  
  
 初始上下文  
 [输入] 上下文中的数据。  
  
 pp开卷机  
 [输出] 指针指向“ICor调试虚拟开卷机”接口对象的地址。  
  
## <a name="return-value"></a>返回值  
 `S_OK` 如果成功。 所有其他 `HRESULT` 都表示故障。 任何失败`HRESULT`由 mscordbi 接收被视为是致命并导致[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)方法返回`CORDBG_E_DATA_TARGET_ERROR`。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugDataTarget2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
