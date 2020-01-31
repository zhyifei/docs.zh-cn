---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868338"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 从内存中的符号流中读取字节。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>参数  
 `moduleId`  
 中包含内存中流的模块的标识符。  
  
 `symbolsReadOffset`  
 中内存中流中的偏移量，从此处开始读取字节。  
  
 `pSymbolBytes`  
 弄指向数据将复制到的缓冲区的指针。 缓冲区的可用空间应 `countSymbolBytes`。  
  
 `countSymbolBytes`  
 中要复制的字节数。  
  
 `pCountSymbolBytesRead`  
 弄当该方法返回时，包含所读取的实际字节数。  
  
## <a name="return-value"></a>返回值  
 如果读取了非零字节数，则 `S_OK`。  
  
 如果该模块是使用 <xref:System.Reflection.Emit>创建的 `CORPROF_E_MODULE_IS_DYNAMIC`，则为。  
  
## <a name="remarks"></a>备注  
 `ReadInMemorySymbols` 方法尝试读取内存中流中 `symbolsReadOffset` 偏移开始的数据 `countSymbolBytes`。 数据将复制到 `pSymbolBytes`，这应该具有可用的空间 `countSymbolBytes`。     `pCountSymbolsBytesRead` 包含读取的实际字节数，如果已到达流的末尾，则该值可能小于 `countSymbolBytes`。  
  
> [!NOTE]
> 当前实现不支持反射。发出。 如果该模块是使用反射创建的，则该方法将返回 `CORPROF_E_MODULE_IS_DYNAMIC`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo7 接口](icorprofilerinfo7-interface.md)
