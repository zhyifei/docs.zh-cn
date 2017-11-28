---
title: 'Icorprofilerinfo7:: Readinmemorysymbols'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ada9f629c3a3c3d8b7c32ebc180c4788b6f6d3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>Icorprofilerinfo7:: Readinmemorysymbols
[支持版本：[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 及更高版本]  
  
 从内存中的符号流读取字节。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 [in]包含内存中流的模块的标识符。  
  
 `symbolsReadOffset`  
 [in]在开始读取字节的内存中流内的偏移量。  
  
 `pSymbolBytes`  
 [out]指向数据将复制到其中的缓冲区的指针。 缓冲区应有`countSymbolBytes`的可用空间。  
  
 `countSymbolBytes`  
 [in]要复制的字节数。  
  
 `pCountSymbolBytesRead`  
 [out]方法返回时，包含实际读取的字节数。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果已读取的字节非零值数。  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`如果该模块使用创建<xref:System.Reflection.Emit>。  
  
## <a name="remarks"></a>备注  
 `ReadInMemorySymbols`方法尝试读取`countSymbolBytes`的数据从偏移量开始`symbolsReadOffset`内存中流中。 将数据复制到`pSymbolBytes`，这应该具有`countSymbolBytes`的可用空间。     `pCountSymbolsBytesRead`包含的实际读取，这可能会更少的字节数比`countSymbolBytes`如果已到达流结尾。  
  
> [!NOTE]
>  当前实现不支持 Reflection.Emit。 如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
