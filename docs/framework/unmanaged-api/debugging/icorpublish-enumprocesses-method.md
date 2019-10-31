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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121794"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses 方法
获取在此计算机上运行的托管进程的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>参数  
 `Type`  
 [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)枚举的一个值，该值指定要检索的进程的类型。 在当前版本中，只有 COR_PUB_MANAGEDONLY 是有效的。  
  
 `ppIEnum`  
 一个指针，指向作为进程枚举器的[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)实例的地址。  
  
## <a name="remarks"></a>备注  
 枚举器的进程集合基于在调用 `EnumProcesses` 方法时正在运行的进程的快照。 枚举器将不包含在调用 `EnumProcesses` 之后终止或启动的任何进程。  
  
 在此[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)实例上，可以多次调用 `EnumProcesses` 方法，以创建新的最新进程集合。 `EnumProcesses` 方法的后续调用将不会影响现有集合。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorPublish 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
