---
title: “Cor调试代码调用类型”枚举
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22eeb8aba318d53efbc699d4492a86b2667bcfff
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274123"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>“Cor调试代码调用类型”枚举
描述导出函数如何调用托管代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|如果任何托管代码遭该方法调用，稍后将必须接受显式事件或断点定位。<br /><br /> --或者--<br /><br /> 我们或许只能错过该方法调用的一些托管代码，因为很难停在上面。<br /><br /> --或者--<br /><br /> 该方法可能无法调用托管代码。|  
|`CODE_INVOKE_KIND_RETURN`|该方法可通过返回指令调用托管代码。 在下一个托管代码处应跳出。|  
|`CODE_INVOKE_KIND_TAILCALL`|该方法可通过尾调调用托管代码。 在托管代码处应单步执行所有调用指令。|  
  
## <a name="remarks"></a>备注  
 此枚举由[ICorDebugProcess6：： GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md)方法用来提供有关单步执行托管代码的信息。  
  
> [!NOTE]
> 此枚举仅用于 .NET Native 调试方案。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试枚举](debugging-enumerations.md)
- [调试](index.md)
