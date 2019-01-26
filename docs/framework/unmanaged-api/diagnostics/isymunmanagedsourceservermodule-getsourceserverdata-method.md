---
title: ISymUnmanagedSourceServerModule::GetSourceServerData 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71251af116fc8d634b822e1daa49d90e91fec6f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648818"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>ISymUnmanagedSourceServerModule::GetSourceServerData 方法
返回该模块的源服务器数据。 调用方必须释放资源使用`CoTaskMemFree`。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a>参数  
 `pDataByteCount`  
 [out]一个指向`ULONG32`用于接收大小，以字节为单位的源服务器数据。  
  
 `ppData`  
 [out]指向返回的指针`pDataByteCount`值。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedSourceServerModule 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
