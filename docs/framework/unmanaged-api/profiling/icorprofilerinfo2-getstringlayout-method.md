---
title: ICorProfilerInfo2::GetStringLayout 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490710"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 方法
获取有关字符串对象布局的信息。 此方法在.NET Framework 4 中，已弃用，并且已被取代[ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>参数  
 `pBufferLengthOffset`  
 [out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串的长度。 长度存储为`DWORD`。  
  
> [!NOTE]
>  此参数将返回字符串本身，而不是缓冲区的长度的长度。 缓冲区的长度不再可用。  
  
 `PStringLengthOffset`  
 [out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串本身的长度。 长度存储为`DWORD`。  
  
 `pBufferOffset`  
 [out]指向缓冲区，相对于的偏移量的`ObjectID`指针，存储的宽字符字符串。  
  
## <a name="remarks"></a>备注  
 `GetStringLayout`方法获取偏移量，相对于`ObjectID`指针，以下在其中存储的位置：  
  
- 字符串的缓冲区的长度。  
  
- 该字符串本身的长度。  
  
- 包含实际的宽字符字符串的缓冲区。  
  
 字符串可以是以 null 结尾。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
