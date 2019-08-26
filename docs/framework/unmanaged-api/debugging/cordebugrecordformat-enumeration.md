---
title: “Cor调试记录格式”枚举
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6ed7d25593f9dd5d5d01f8c06024dcf8acfcfea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916477"
---
# <a name="cordebugrecordformat-enumeration"></a>“Cor调试记录格式”枚举
描述包含本机异常调试事件相关信息的字节数组的数据格式。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|数据为 32 位 Windows 异常记录。|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|数据为 64 位 Windows 异常记录。|  
  
## <a name="remarks"></a>备注  
 `CorDebugRecordFormat`枚举的成员将传递给[DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法, 以便在其`pRecord`参数中指示字节数组的格式。  
  
> [!NOTE]
> 此枚举仅用于 .NET Native 调试方案。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
