---
title: ISymUnmanagedENCUpdate::GetLocalVariables 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: b5fc8b6807a4c8eb700ab3fa181a216e48a732ff
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449029"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables 方法
获取局部变量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>参数  
 `mdMethodToken`  
 中方法的元数据标记。  
  
 `cLocals`  
 中一个 `ULONG`，指示 `rgLocals` 参数的大小。  
  
 `rgLocals`  
 弄返回的[ISymUnmanagedVariable](isymunmanagedvariable-interface.md)实例的数组。  
  
 `pceltFetched`  
 弄指向 `ULONG` 的指针，该指针接收包含局部变量所需的 `rgLocals` 缓冲区的大小。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedENCUpdate 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
