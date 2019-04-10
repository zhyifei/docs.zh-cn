---
title: ICorDebugILCode 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 51c4de0c-3813-4142-be25-a85bb84efb90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 279a87039c4cbc12c7ec5f734928c851185280f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175716"
---
# <a name="icordebugilcode-interface"></a>ICorDebugILCode 接口
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 表示中间语言 (IL) 代码段。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetEHClauses 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)|返回指向为此 IL 定义的异常处理 (EH) 子句列表的指针。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
