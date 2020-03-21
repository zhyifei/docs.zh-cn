---
title: ICorDebugProcess6::DecodeEvent 方法
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: a0b77724a5a70461073d554a9794c5a904f6a363
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178583"
---
# <a name="icordebugprocess6decodeevent-method"></a>ICorDebugProcess6::DecodeEvent 方法
对封装于特殊构造的本机异常调试事件有效载荷中的托管调试事件进行解码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pRecord`  
 [输入] 包含托管调试事件相关信息的本机异常调试事件中的字节数组指针。  
  
 `countBytes`  
 [输入] `pRecord` 字节数组中的元素数量。  
  
 `format`  
 [在]一个[CorDebugRecord格式](cordebugrecordformat-enumeration.md)枚举成员，用于指定非托管调试事件的格式。  
  
 `dwFlags`  
 [输入] 位域依赖于目标体系结构并指定调试事件相关的其他信息。 对于 Windows 系统，它可以是[CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)枚举的成员。  
  
 `dwThreadId`  
 [输入] 引发异常的线程的操作系统识别符。  
  
 `ppEvent`  
 [出]指向[ICorDebugDebugEvent](icordebugdebugevent-interface.md)对象地址的指针，该对象表示已解码的托管调试事件。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess6 接口](icordebugprocess6-interface.md)
- [调试接口](debugging-interfaces.md)
