---
title: "WriteableMetadataUpdateMode 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b32eca0bec61e6c7b6fcf83bb05650c30c2f9f16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="members"></a>成员  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|当使元数据的内存中更新可见时，保持与 .NET Framework 早期版本的兼容性。 有关详细信息，请参阅备注部分。|  
|`AlwaysShowUpdates`|使元数据的内存中更新对调试器可见。|  
  
## <a name="remarks"></a>备注  
 成员`WriteableMetadataUpdateMode`枚举可以传递给[SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)方法可控制是否对目标进程中的元数据更新内存中都可见的调试器。  
  
 `LegacyCompatPolicy` 选项将强制执行与 4.5.2 之前的 .NET Framework 版本相同的行为。 这通常代表更新中的元数据不可见。 但是，对大量调试方法的调用会隐式强迫调试器使更新变得可见。 例如，如果调试器将传递[icordebugilframe:: Getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)中找不到方法的原始元数据，所有元数据的模块更新为匹配的当前状态的快照的变量的索引过程。 也就是说，借助 `LegacyCompatPolicy` 选项，调试器可能看不见任何可用的元数据更新，或者可能看见一些或者所有可用的元数据更新，具体取决于它使用非托管调试 API 的其他部分的方式。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [SetWriteableMetadataUpdateMode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
