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
ms.openlocfilehash: 63ad2532240c9f18a00421281fae0d111dbfaec5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963794"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 方法
获取有关字符串对象布局的信息。 此方法在 .NET Framework 4 中已弃用, 并且被[ICorProfilerInfo3:: GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法取代。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>参数  
 `pBufferLengthOffset`  
 弄一个指针, 它指向存储字符串长度的相对`ObjectID`于指针的位置偏移量。 长度存储为`DWORD`。  
  
> [!NOTE]
> 此参数返回字符串本身的长度, 而不是缓冲区的长度。 缓冲区的长度不再可用。  
  
 `PStringLengthOffset`  
 弄指向位置偏移量的指针, 该位置相对`ObjectID`于指针存储字符串本身的长度。 长度存储为`DWORD`。  
  
 `pBufferOffset`  
 弄一个指针, 它指向存储宽字符字符串的缓冲区相对`ObjectID`于指针的偏移量。  
  
## <a name="remarks"></a>备注  
 方法获取在其中存储下列位置的相对`ObjectID`于指针的偏移量: `GetStringLayout`  
  
- 字符串缓冲区的长度。  
  
- 字符串本身的长度。  
  
- 包含宽字符实际字符串的缓冲区。  
  
 字符串可以以 null 结尾。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
