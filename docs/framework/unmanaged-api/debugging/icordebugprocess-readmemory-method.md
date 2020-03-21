---
title: ICorDebugProcess::ReadMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178655"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory 方法
读取此过程的指定内存区域。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>parameters  
 `address`  
 [在]指定`CORDB_ADDRESS`要读取的内存的基本地址的值。  
  
 `size`  
 [在]要从内存中读取的字节数。  
  
 `buffer`  
 [出]接收内存内容的缓冲区。  
  
 `read`  
 [出]指向传输到指定缓冲区的字节数的指针。  
  
## <a name="remarks"></a>备注  
 该方法`ReadMemory`主要用于内部调试，以检查调试器的非托管部分正在使用的内存区域。 此方法还可用于读取 Microsoft 中间语言 （MSIL） 代码和本机 JIT 编译代码。  
  
 任何托管断点都将从`buffer`参数中返回的数据中删除。 [ICorDebugProcess2：：：setUn托管断点](icordebugprocess2-setunmanagedbreakpoint-method.md)设置的本机断点不会进行调整。  
  
 不执行进程内存的缓存。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
