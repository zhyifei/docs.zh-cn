---
title: "CodeChunkInfo 结构 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CodeChunkInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: CodeChunkInfo
helpviewer_keywords: CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17727c8927f9db3de3ab26d2504dfae5215a1495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="codechunkinfo-structure1"></a>CodeChunkInfo 结构 1
表示内存中的单一代码块。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`startAddr`|A`CORDB_ADDRESS`值，该值指定的块区的起始地址。|  
|`length`|以字节为单位，区块的大小。|  
  
## <a name="remarks"></a>备注  
 的单一代码块是属于一个代码对象，如函数的本机代码的区域。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [GetCodeChunks 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
