---
title: ICLRDataTarget::Request 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179116"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request 方法
由通用语言运行时 （CLR） 数据访问服务调用，以请求由实现定义的操作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>parameters  
 `reqCode`  
 [在]用户定义。  
  
 `inBufferSize`  
 [在]用于传入请求的输入缓冲区的大小。  
  
 `inBuffer`  
 [在]包含请求的缓冲区。  
  
 `outBufferSize`  
 [在]用于响应的输出缓冲区的大小。  
  
 `outBuffer`  
 [出]包含响应的缓冲区。  
  
## <a name="remarks"></a>备注  
 该方法`Request`便于添加未指定的自定义操作。 也就是说，此方法提供可扩展性，而无需修订接口定义。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** ClrData.idl， ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRDataTarget 接口](iclrdatatarget-interface.md)
