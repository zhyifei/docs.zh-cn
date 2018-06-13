---
title: ICorDebugCode2::GetCodeChunks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdfcd45b15ddc1491b12de0fa42901b6d3f7fe9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413148"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks 方法
获取此代码对象组成的代码块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbufSize`  
 [in]大小`chunks`数组。  
  
 `pcnumChunks`  
 [out]在中返回的区块的数量`chunks`数组。  
  
 `chunks`  
 [out]"CodeChunkInfo"结构数组，其中每个表示的单一代码块。 如果值`cbufSize`为 0，此参数可以为 null。  
  
## <a name="remarks"></a>备注  
 代码块将永远不会重叠，而且它们将遵循的顺序，它们将连接通过公共[icordebugcode::](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)。 .NET Framework 2.0 版中的 Microsoft 中间语言 (MSIL) 代码对象将构成单个代码块。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
