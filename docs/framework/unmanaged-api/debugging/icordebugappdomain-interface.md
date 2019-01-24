---
title: ICorDebugAppDomain 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9588ac26c698a8369f1ae4be89af7440a2dd1de4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546301"
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain 接口 1
提供用于调试应用程序域的方法。 此接口是 ICorDebugController 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Attach 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|将调试器附加到应用程序域。|  
|[EnumerateAssemblies 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|获取可枚举的程序集应用程序域中。|  
|[EnumerateBreakpoints 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|获取应用程序域中所有活动断点的枚举数。|  
|[EnumerateSteppers 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|获取可枚举所有活动分档应用程序域中。|  
|[GetId 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|获取应用程序域的唯一 ID。|  
|[GetModuleFromMetaDataInterface 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|获取具有给定元数据接口的 icor 调试模块对象。|  
|[GetName 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|获取应用程序域的名称。|  
|[GetObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|获取对公共语言运行时 (CLR) 应用程序域的接口指针。|  
|[GetProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|获取包含应用程序域的进程。|  
|[IsAttached 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|确定调试器是否附加到应用程序域。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
