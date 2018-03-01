---
title: "ICorDebugProcess::WriteMemory 方法"
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
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory 方法
将数据写入的此进程中的内存区域。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]A`CORDB_ADDRESS`写入到的数据的内存区域的基址的值。 数据传输发生之前，系统将验证开始的基址的指定大小的内存区域可以进行写入访问。 如果它是不可访问，该方法将失败。  
  
 `size`  
 [in]要写入到内存区域的字节数。  
  
 `buffer`  
 [in]包含要写入的数据的缓冲区。  
  
 `written`  
 [out]指向一个变量来接收此过程中的内存区域写入的字节数的指针。 如果`written`为 NULL，则忽略此参数。  
  
## <a name="remarks"></a>备注  
 在任意断点后，会自动写入数据。 在.NET Framework 2.0 版中，本机调试器不应使用此方法来插入指令流的断点。 使用[icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)相反。  
  
 `WriteMemory`方法应仅在托管代码之外使用。 如果使用不正确，此方法会损坏运行时。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
