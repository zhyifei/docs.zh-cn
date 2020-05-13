---
title: ICorDebugInternalFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: ce3ca4745727a1738fdc1a526480d70ffc55ccf8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209898"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2 接口
提供有关内部帧的信息，包括堆栈地址和相对于 ICorDebugFrame 对象的位置。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetFrameAddress 方法](icordebuginternalframe2-getframeaddress-method.md)|返回内部帧的堆栈地址。|  
|[IsCloserToLeaf 方法](icordebuginternalframe2-isclosertoleaf-method.md)|检查 `this` 内部帧是否接近于指定的 ICorDebugFrame 对象。|  
  
## <a name="remarks"></a>备注  
 此接口扩展 ICorDebugInternalFrame 接口。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
