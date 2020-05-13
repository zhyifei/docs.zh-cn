---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 6de75e1e27660ac91bd6320a501db47f3b055fb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212251"
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
  
## <a name="parameters"></a>参数  
 `flags`  
 一个[WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)枚举值，该值指定目标进程中的元数据的内存中更新对调试器是否可见（ `WriteableMetadataUpdateMode::AlwaysShowUpdates` ）或不可见（ `WriteableMetadataUpdateMode::LegacyCompatPolicy` ）。  
  
## <a name="remarks"></a>备注  
 目标进程中元数据的更新可以来自于“编辑并继续”、探查器或 <xref:System.Reflection.Emit?displayProperty=nameWithType>。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugProcess7 接口](icordebugprocess7-interface.md)
- [调试接口](debugging-interfaces.md)
