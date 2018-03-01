---
title: "ISymUnmanagedBinder3::GetReaderFromCallback 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 648559936259e7412011f9fb7613bd0e938e4ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="ca760-102">ISymUnmanagedBinder3::GetReaderFromCallback 方法</span><span class="sxs-lookup"><span data-stu-id="ca760-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="ca760-103">允许用户实现或通过回调提供`IID_IDiaReadExeAtRVACallback`或`IID_IDiaReadExeAtOffsetCallback`以从内存中获取的调试目录信息。</span><span class="sxs-lookup"><span data-stu-id="ca760-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca760-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca760-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca760-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca760-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="ca760-106">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ca760-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ca760-107">[in]指向的文件名称的指针。</span><span class="sxs-lookup"><span data-stu-id="ca760-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="ca760-108">[in]搜索路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="ca760-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="ca760-109">[in]值为[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)枚举，它指定要执行搜索的符号读取器时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="ca760-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="ca760-110">[in]指向回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="ca760-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ca760-111">[out]一个指针，它设置为返回[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ca760-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca760-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ca760-112">Return Value</span></span>  
 <span data-ttu-id="ca760-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="ca760-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca760-114">惠?</span><span class="sxs-lookup"><span data-stu-id="ca760-114">Requirements</span></span>  
 <span data-ttu-id="ca760-115">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="ca760-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca760-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca760-116">See Also</span></span>  
 [<span data-ttu-id="ca760-117">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="ca760-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
