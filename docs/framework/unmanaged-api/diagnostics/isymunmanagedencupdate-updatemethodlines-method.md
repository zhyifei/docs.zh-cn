---
title: ISymUnmanagedENCUpdate::UpdateMethodLines 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448990"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>ISymUnmanagedENCUpdate::UpdateMethodLines 方法
允许更新尚未重新编译但行已单独移动的方法的行信息。 允许每个语句的增量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>参数  
 `mdMethodToken`  
 中方法标记的元数据。  
  
 `pDeltas`  
 中一个 `INT32` 值的数组，该值指示方法中的每个序列点的增量。  
  
 `cDeltas`  
 中包含 `pDeltas` 参数大小的 `ULONG`。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedENCUpdate 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
