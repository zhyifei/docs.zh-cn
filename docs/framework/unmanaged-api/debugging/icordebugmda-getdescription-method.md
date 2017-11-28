---
title: "ICorDebugMDA::GetDescription 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetDescription
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18ffd8ab92829404b1eadae33f067a1ea8391396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetdescription-method"></a>ICorDebugMDA::GetDescription 方法
获取一个字符串，该字符串包含由表示托管调试助手 (MDA) 的说明[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cchName`  
 [in]将存储说明字符串缓冲区的大小。  
  
 `pcchName`  
 [out]指向字符串缓冲区中返回的字节数的指针。  
  
 `szName`  
 [out]包含 MDA 的说明的字符串缓冲区。  
  
## <a name="remarks"></a>备注  
 字符串可以是零长度。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugMDA 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
