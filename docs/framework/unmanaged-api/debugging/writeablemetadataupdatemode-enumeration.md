---
title: WriteableMetadataUpdateMode 枚举
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 98566176ff33000fc4b4587b5669a037c90268f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139097"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode 枚举
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 提供用于指定元数据的内存中更新对调试器是否可见的值。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Members  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|当使元数据的内存中更新可见时，保持与 .NET Framework 早期版本的兼容性。 有关详细信息，请参阅备注部分。|  
|`AlwaysShowUpdates`|使元数据的内存中更新对调试器可见。|  
  
## <a name="remarks"></a>备注  
 `WriteableMetadataUpdateMode` 枚举的成员可以传递给[SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)方法，以控制目标进程中元数据的内存中更新对调试器是否可见。  
  
 `LegacyCompatPolicy` 选项将强制执行与 4.5.2 之前的 .NET Framework 版本相同的行为。 这通常代表更新中的元数据不可见。 但是，对大量调试方法的调用会隐式强迫调试器使更新变得可见。 例如，如果调试器传递了[ICorDebugILFrame：： GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) ，而该方法的原始元数据中找不到该变量的索引，则该模块的所有元数据将更新为与该进程的当前状态匹配的快照。 也就是说，借助 `LegacyCompatPolicy` 选项，调试器可能看不见任何可用的元数据更新，或者可能看见一些或者所有可用的元数据更新，具体取决于它使用非托管调试 API 的其他部分的方式。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
