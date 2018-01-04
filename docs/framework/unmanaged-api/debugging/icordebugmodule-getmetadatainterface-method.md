---
title: "ICorDebugModule::GetMetaDataInterface 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetMetaDataInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d374b83155ccc8511c6e3217a8a49819d81a7d48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface 方法
获取可用于检查该模块的元数据的元数据接口对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a>参数  
 `riid`  
 [in]指定的元数据接口引用 ID。  
  
 `ppObj`  
 [out]指向的地址的指针`T:IUnknown`对象之一的[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。  
  
## <a name="remarks"></a>备注  
 可以使用调试器`GetMetaDataInterface`方法来执行的模块，它必须这样做才能编辑该模块的原始元数据的副本。 该调试器将调用`GetMetaDataInterface`获取[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口对象模块，然后调用[imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)将模块的元数据的副本保存到内存。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据](../../../../docs/framework/unmanaged-api/metadata/index.md)
