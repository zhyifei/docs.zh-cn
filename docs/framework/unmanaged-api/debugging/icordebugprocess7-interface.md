---
title: ICorDebugProcess7 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess7
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 71aee5f3-5e10-44fa-be69-6d8a475f2c14
topic_type:
- apiref
ms.openlocfilehash: 76aaeef93028b2ff9526601450d7e11f918e063d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792187"
---
# <a name="icordebugprocess7-interface"></a>ICorDebugProcess7 接口
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[SetWriteableMetadataUpdateMode 方法](icordebugprocess7-setwriteablemetadataupdatemode-method.md)|设置一个值，用于确定调试器如何处理目标进程中元数据的内存中更新。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
