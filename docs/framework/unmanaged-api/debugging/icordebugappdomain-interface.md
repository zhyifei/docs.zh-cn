---
title: ICorDebugAppDomain 接口
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
ms.openlocfilehash: da7c0fb472df89d94fa702a13eff968a4c7e68e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785033"
---
# <a name="icordebugappdomain-interface"></a>ICorDebugAppDomain 接口

提供用于调试应用程序域的方法。 此接口是 ICorDebugController 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Attach 方法](icordebugappdomain-attach-method.md)|将调试器附加到应用程序域。|  
|[EnumerateAssemblies 方法](icordebugappdomain-enumerateassemblies-method.md)|获取应用程序域中的程序集的枚举器。|  
|[EnumerateBreakpoints 方法](icordebugappdomain-enumeratebreakpoints-method.md)|获取应用程序域中所有活动断点的枚举器。|  
|[EnumerateSteppers 方法](icordebugappdomain-enumeratesteppers-method.md)|获取应用程序域中所有活动 steppers 的枚举器。|  
|[GetId 方法](icordebugappdomain-getid-method.md)|获取应用程序域的唯一 ID。|  
|[GetModuleFromMetaDataInterface 方法](icordebugappdomain-getmodulefrommetadatainterface-method.md)|获取具有给定元数据接口的 ICorDebugModule 对象。|  
|[GetName 方法](icordebugappdomain-getname-method.md)|获取应用程序域的名称。|  
|[GetObject 方法](icordebugappdomain-getobject-method.md)|获取指向公共语言运行时（CLR）应用程序域的接口指针。|  
|[GetProcess 方法](icordebugappdomain-getprocess-method.md)|获取包含应用程序域的进程。|  
|[IsAttached 方法](icordebugappdomain-isattached-method.md)|确定调试器是否已附加到应用程序域。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
