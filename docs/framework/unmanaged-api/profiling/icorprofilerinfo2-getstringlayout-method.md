---
title: "ICorProfilerInfo2::GetStringLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52a1b9218feb76f7653f747aa52c44284293221f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 方法
获取有关字符串对象布局的信息。 此方法已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，并且由取代[icorprofilerinfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a>参数  
 `pBufferLengthOffset`  
 [out]指向的位置，相对于的偏移量的指针`ObjectID`指针，用于存储字符串的长度。 作为存储长度`DWORD`。  
  
> [!NOTE]
>  此参数返回的字符串本身，而不缓冲区的长度的长度。 缓冲区的长度不再可用。  
  
 `PStringLengthOffset`  
 [out]指向的位置，相对于的偏移量的指针`ObjectID`指针，用于存储本身的字符串的长度。 作为存储长度`DWORD`。  
  
 `pBufferOffset`  
 [out]指向的缓冲区，相对于的偏移量的指针`ObjectID`指针，存储的宽字符字符串。  
  
## <a name="remarks"></a>备注  
 `GetStringLayout`方法获取相对于偏移量，`ObjectID`指针，以下存储所在的位置：  
  
-   字符串的缓冲区的长度。  
  
-   字符串本身的长度。  
  
-   包含实际的宽字符字符串的缓冲区。  
  
 字符串可能是以 null 结尾。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
