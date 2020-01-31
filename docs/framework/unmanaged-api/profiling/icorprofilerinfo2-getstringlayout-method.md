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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868611"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 方法
获取有关字符串对象布局的信息。 此方法在 .NET Framework 4 中已弃用，并且被[ICorProfilerInfo3：： GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md)方法取代。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>参数  
 `pBufferLengthOffset`  
 弄一个指针，它指向存储字符串长度的位置相对于 `ObjectID` 指针的位置偏移量。 长度作为 `DWORD`存储。  
  
> [!NOTE]
> 此参数返回字符串本身的长度，而不是缓冲区的长度。 缓冲区的长度不再可用。  
  
 `PStringLengthOffset`  
 弄一个指针，它指向存储字符串本身的长度的位置相对于 `ObjectID` 指针的偏移量。 长度作为 `DWORD`存储。  
  
 `pBufferOffset`  
 弄一个指针，它指向存储宽字符字符串的缓冲区相对于 `ObjectID` 指针的偏移量。  
  
## <a name="remarks"></a>备注  
 `GetStringLayout` 方法获取以下位置的相对于 `ObjectID` 指针的偏移量：  
  
- 字符串缓冲区的长度。  
  
- 字符串本身的长度。  
  
- 包含宽字符实际字符串的缓冲区。  
  
 字符串可以以 null 结尾。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](icorprofilerinfo2-interface.md)
