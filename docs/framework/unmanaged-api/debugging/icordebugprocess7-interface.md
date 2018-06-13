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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a684a5daa0619b0614ca074b7b1e3b9d0b25882
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421433"
---
# <a name="icordebugprocess7-interface"></a>ICorDebugProcess7 接口
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[SetWriteableMetadataUpdateMode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)|设置一个值，用于确定调试器如何处理目标进程中元数据的内存中更新。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
