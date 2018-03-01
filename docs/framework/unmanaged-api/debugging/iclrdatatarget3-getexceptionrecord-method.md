---
title: "ICLRDataTarget3::GetExceptionRecord 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3e78131eda9d10646a881dbbd4e3f7a4aaf8f607
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>ICLRDataTarget3::GetExceptionRecord 方法
由公共语言运行时 (CLR) 数据访问服务调用，以检索与目标进程关联的异常记录。 例如，对于转储目标时，这将是等效于通过传入的异常记录`ExceptionParam`参数[MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) Windows 调试帮助库中 (DbgHelp) 的函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bufferSize`  
 [in] 输入缓冲区大小（以字节为单位）。 这必须是等于`sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`。  
  
 `bufferUsed`  
 [out] 指向接收实际写入缓冲区的字节数的 `ULONG32` 类型的指针。  
  
 `buffer`  
 [out] 指向接收异常记录副本的内存缓冲区的指针。 异常记录将作为[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)类型。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。 `HRESULT` 代码可以包括但不限于以下代码：  
  
|返回代码|描述|  
|-----------------|-----------------|  
|`S_OK`|方法成功。 已将异常记录复制到输出缓冲区。|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|没有与目标关联的异常记录。|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|输入缓冲区大小不等于 `sizeof(MINIDUMP_EXCEPTION)`。|  
  
## <a name="remarks"></a>备注  
 [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)是 dbghelp.h 和 imagehlp.h 中 Windows SDK 中定义的结构。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl、 ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRDataTarget3 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [GetExceptionContextRecord 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [GetExceptionThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
