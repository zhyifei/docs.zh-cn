---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 067be401b793c227d8b5caa2706f84a59d3a09df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499038"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="7eafe-102">ISymUnmanagedWriter2::DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="7eafe-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="7eafe-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="7eafe-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eafe-104">语法</span><span class="sxs-lookup"><span data-stu-id="7eafe-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eafe-105">参数</span><span class="sxs-lookup"><span data-stu-id="7eafe-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7eafe-106">[in]全局变量名称。</span><span class="sxs-lookup"><span data-stu-id="7eafe-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="7eafe-107">[in]全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="7eafe-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="7eafe-108">[in]签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7eafe-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="7eafe-109">[in]地址类型。</span><span class="sxs-lookup"><span data-stu-id="7eafe-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="7eafe-110">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="7eafe-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="7eafe-111">[in]参数规格的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="7eafe-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="7eafe-112">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="7eafe-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7eafe-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7eafe-113">Return Value</span></span>  
 <span data-ttu-id="7eafe-114">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7eafe-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eafe-115">要求</span><span class="sxs-lookup"><span data-stu-id="7eafe-115">Requirements</span></span>  
 <span data-ttu-id="7eafe-116">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="7eafe-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eafe-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7eafe-117">See also</span></span>
- [<span data-ttu-id="7eafe-118">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="7eafe-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="7eafe-119">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="7eafe-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
