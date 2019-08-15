---
title: ICLRDataTarget3::GetExceptionRecord 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b667ac16a4bbe6bdab1814b66fb1121b34b2d945
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039584"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>ICLRDataTarget3::GetExceptionRecord 方法
由公共语言运行时 (CLR) 数据访问服务调用，以检索与目标进程关联的异常记录。 例如, 对于转储目标, 此操作等效于通过`ExceptionParam` Windows 调试帮助库 (dbghelp.dll) 中的[MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump)函数的参数传入的异常记录。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>参数  
 `bufferSize`  
 [in] 输入缓冲区大小（以字节为单位）。 该值必须等于`sizeof(` [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`。  
  
 `bufferUsed`  
 [out] 指向接收实际写入缓冲区的字节数的 `ULONG32` 类型的指针。  
  
 `buffer`  
 [out] 指向接收异常记录副本的内存缓冲区的指针。 异常记录作为[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)类型返回。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。 `HRESULT` 代码可以包括但不限于以下代码：  
  
|返回代码|描述|  
|-----------------|-----------------|  
|`S_OK`|方法成功。 已将异常记录复制到输出缓冲区。|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|没有与目标关联的异常记录。|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|输入缓冲区大小不等于 `sizeof(MINIDUMP_EXCEPTION)`。|  
  
## <a name="remarks"></a>备注  
 [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)是在 Windows SDK 中的 dbghelp.dll 和 imagehlp.dll 中定义的结构。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData, ClrData  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRDataTarget3 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionContextRecord 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [GetExceptionThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
