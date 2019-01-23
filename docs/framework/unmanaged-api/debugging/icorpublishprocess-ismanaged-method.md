---
title: ICorPublishProcess::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b57a8bcc584ffd209def5a84a99b15daa7480ee6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534938"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged 方法
获取一个值，该值指示是否引用的进程这[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)已知具有托管代码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbManaged`  
 [out]指向一个布尔值，该值指示是否处理具有托管代码的指针。 值是`true`如果进程具有托管代码; 否则为`false`。  
  
## <a name="remarks"></a>备注  
 由于当前版本的`ICorPublishProcess`仅允许访问具有托管代码中，进程`IsManaged`始终返回`true`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorPublishProcess 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
