---
title: ICorDebugAppDomainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 38603fb53b9cd6548595437b05c1e99ef208d940
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895098"
---
# <a name="icordebugappdomainenum-interface"></a>ICorDebugAppDomainEnum 接口

提供`Next`方法，该方法从枚举中的下`ICorDebugAppDomainEnum`一个位置开始返回指定数目的值。 此接口是 "ICorDebugEnum" 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[Next 方法](icordebugappdomainenum-next-method.md)|从当前游标位置开始，获取集合中指定数量的应用程序域。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebug 接口](icordebug-interface.md)
- [调试接口](debugging-interfaces.md)
