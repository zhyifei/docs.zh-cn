---
title: ICorDebugDataTarget2::CreateVirtualUnwinder 方法
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 9fc4facda6253d0c68dcf89b2a1b06e639734efe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788857"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>ICorDebugDataTarget2::CreateVirtualUnwinder 方法
创建一个从初始上下文（不一定是线程叶）开始展开的新堆栈开卷机。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>参数  
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
 `S_OK` 如果成功。 所有其他 `HRESULT` 都表示故障。 Mscordbi.dll 收到的任何失败的 `HRESULT` 都被视为致命错误，并导致[ICorDebug](icordebug-interface.md)方法返回 `CORDBG_E_DATA_TARGET_ERROR`。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugDataTarget2 接口](icordebugdatatarget2-interface.md)
- [调试接口](debugging-interfaces.md)
