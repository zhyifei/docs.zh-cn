---
title: "ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法"
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
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e901fd623893b9c03e1b5835adc72c6bd225ead4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 配置调试器如何处理目标进程中元数据的内存中更新。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `flags`  
 A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)枚举值，该值指定内存中更新目标进程中的元数据是否可见 (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) 或不可见 (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) 到调试器。  
  
## <a name="remarks"></a>备注  
 目标进程中元数据的更新可以来自于“编辑并继续”、探查器或 <xref:System.Reflection.Emit?displayProperty=nameWithType>。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess7 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
