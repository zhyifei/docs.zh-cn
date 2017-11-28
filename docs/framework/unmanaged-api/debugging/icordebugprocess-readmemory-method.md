---
title: "ICorDebugProcess::ReadMemory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ReadMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33345ada6606bc1a43a630340251d3ba1404b2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory 方法
读取此进程的内存的指定的区域。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]A`CORDB_ADDRESS`指定的内存要读取的基址的值。  
  
 `size`  
 [in]要从内存读取的字节数。  
  
 `buffer`  
 [out]用于接收缓冲区的内存的内容。  
  
 `read`  
 [out]指向的字节数的传输到指定的缓冲区。  
  
## <a name="remarks"></a>备注  
 `ReadMemory`方法主要用于通过互操作调试用于检查正在使用的调试对象的非托管部分的内存区域。 此方法还可以用于读取 Microsoft 中间语言 (MSIL) 代码和本机 JIT 编译代码。  
  
 将从中返回的数据中删除任何托管的断点`buffer`参数。 将进行任何调整，为本机断点通过设置[icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)。  
  
 执行进程内存无缓存。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
