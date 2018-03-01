---
title: "ICLRDataTarget::Request 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e7bde3a0bc26a6bc93124fa835c4203cd596906
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request 方法
调用由公共语言运行时 (CLR) 数据访问服务以请求操作，如由实现定义。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `reqCode`  
 [in]用户定义。  
  
 `inBufferSize`  
 [in]输入缓冲区，用于传入请求的大小。  
  
 `inBuffer`  
 [in]包含请求的缓冲区。  
  
 `outBufferSize`  
 [in]输出缓冲区，用于响应的大小。  
  
 `outBuffer`  
 [out]包含响应的缓冲区。  
  
## <a name="remarks"></a>备注  
 `Request`方法方便了添加的未指定自定义操作。 也就是说，此方法还提供扩展性而无需的接口定义的修订版本。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl、 ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
