---
title: ICorDebugAppDomain3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c130b92fd5114d067730da3b7cd138d98cf0577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407400"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 接口
提供用于检索有关托管表示形式的信息方法[!INCLUDE[wrt](../../../../includes/wrt-md.md)]当前加载的应用程序域中的类型。 此接口是 ICorDebugAppDomain 和 ICorDebugAppDomain2 接口的扩展。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|获取所有缓存的枚举数[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。|  
|[Icordebugappdomain3:: Getcachedwinrttypesforiids](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|获取一个枚举器，为缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。|  
  
## <a name="remarks"></a>备注  
 此接口旨在由结合函数评估调用调试器使用`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`。 当方法检索支持的接口标识符[!INCLUDE[wrt](../../../../includes/wrt-md.md)]服务器对象时，调试器可能使用此接口中定义的方法可将其映射为对应于这些接口的托管类型。  
  
 若要检索此接口的实例，运行`QueryInterface`ICorDebugAppDomain 或 ICorDebugAppDomain2 接口的实例上。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
