---
title: ICorPublish::EnumProcesses 方法
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2779138a0999e34ad6424d76ddfebbcfdf611d58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses 方法
获取在此计算机上运行的托管进程的枚举数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `Type`  
 值为[COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)指定的进程要检索的类型的枚举。 在最新版本，仅 COR_PUB_MANAGEDONLY 是有效的。  
  
 `ppIEnum`  
 指向的地址的指针[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)是进程的枚举器的实例。  
  
## <a name="remarks"></a>备注  
 进程的枚举器集合基于时正在运行的进程的快照`EnumProcesses`调用方法。 枚举数将不包含任何进程终止之前或之后开始`EnumProcesses`调用。  
  
 `EnumProcesses`方法可对这一次调用[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)实例来创建新的最新进程集合。 后续调用将不影响现有集合`EnumProcesses`方法。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorPublish 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
