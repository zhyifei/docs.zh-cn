---
title: “ICor调试数据目标2”接口
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976429"
---
# <a name="icordebugdatatarget2-interface"></a>“ICor调试数据目标2”接口
对[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口进行逻辑扩展。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[CreateVirtualUnwinder 方法](icordebugdatatarget2-createvirtualunwinder-method.md)|创建一个从初始上下文（不一定是线程叶）开始展开的新堆栈开卷机。|  
|[EnumerateThreadIDs 方法](icordebugdatatarget2-enumeratethreadids-method.md)|返回一组活动线程 ID。|  
|[GetImageFromPointer 方法](icordebugdatatarget2-getimagefrompointer-method.md)|返回该模块地址中的模块基址和大小。|  
|[GetImageLocation 方法](icordebugdatatarget2-getimagelocation-method.md)|返回模块基址中的模块路径。|  
|[GetSymbolProviderForImage 方法](icordebugdatatarget2-getsymbolproviderforimage-method.md)|返回该模块基址中的模块符号提供程序。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
