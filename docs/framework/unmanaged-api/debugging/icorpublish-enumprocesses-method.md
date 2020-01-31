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
ms.openlocfilehash: 5f785b22a3fbda6403c124ec70757b16f5335907
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790758"
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
 一个[COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md)枚举的值，该值指定要检索的进程的类型。 在当前版本中，只有 COR_PUB_MANAGEDONLY 是有效的。  
  
 `ppIEnum`  
 一个指针，指向作为进程枚举器的[ICorPublishProcessEnum](icorpublishprocessenum-interface.md)实例的地址。  
  
## <a name="remarks"></a>备注  
 枚举器的进程集合基于在调用 `EnumProcesses` 方法时正在运行的进程的快照。 枚举器将不包含在调用 `EnumProcesses` 之后终止或启动的任何进程。  
  
 在此[ICorPublish](icorpublish-interface.md)实例上，可以多次调用 `EnumProcesses` 方法，以创建新的最新进程集合。 `EnumProcesses` 方法的后续调用将不会影响现有集合。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorPublish 接口](icorpublish-interface.md)
