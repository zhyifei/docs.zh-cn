---
title: ISymUnmanagedBinder3::GetReaderFromCallback 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449309"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback 方法
允许用户通过回调来实现或提供，以从内存中获取调试目录信息 `IID_IDiaReadExeAtRVACallback` 或 `IID_IDiaReadExeAtOffsetCallback`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>参数  
 `importer`  
 中指向元数据导入接口的指针。  
  
 `fileName`  
 中指向文件名的指针。  
  
 `searchPath`  
 中指向搜索路径的指针。  
  
 `searchPolicy`  
 中[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)枚举的一个值，该值指定在搜索符号读取器时要使用的策略。  
  
 `callback`  
 中指向回调函数的指针。  
  
 `pRetVal`  
 弄设置为返回的[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym .idl  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedBinder3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
