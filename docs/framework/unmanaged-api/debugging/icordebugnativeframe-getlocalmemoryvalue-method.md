---
title: ICorDebugNativeFrame::GetLocalMemoryValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e8d0c16000c78fab0371b68c3a350bd2018aa1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664520"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryValue 方法
获取参数或存储在指定的内存位置的此本机帧中的本地变量的值。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]一个`CORDB_ADDRESS`值，该值指定内存位置包含的值。  
  
 `cbSigBlob`  
 [in]一个整数，指定的二进制元数据签名的由引用大小`pvSigBlob`参数。  
  
 `pvSigBlob`  
 [in]一个`PCCOR_SIGNATURE`指向值类型的二进制元数据签名的值。  
  
 `ppValue`  
 [out]指向表示检索到的值存储在指定的内存位置中的"ICorDebugValue"对象的地址的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

