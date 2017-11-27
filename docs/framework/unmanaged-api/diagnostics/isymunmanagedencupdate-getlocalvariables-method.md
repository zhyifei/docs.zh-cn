---
title: "ISymUnmanagedENCUpdate::GetLocalVariables 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.GetLocalVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 492d41402531cb6fb92f90ab0e533fb20c6129df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="18de6-102">ISymUnmanagedENCUpdate::GetLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="18de6-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="18de6-103">获取本地变量。</span><span class="sxs-lookup"><span data-stu-id="18de6-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18de6-104">语法</span><span class="sxs-lookup"><span data-stu-id="18de6-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18de6-105">参数</span><span class="sxs-lookup"><span data-stu-id="18de6-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="18de6-106">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="18de6-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="18de6-107">[in]A `ULONG` ，该值指示的大小`rgLocals`参数。</span><span class="sxs-lookup"><span data-stu-id="18de6-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="18de6-108">[out]返回的数组的<!--zz<xref:ISymUnmanagedVariable>-->`ISymUnmanagedVariable`实例。</span><span class="sxs-lookup"><span data-stu-id="18de6-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="18de6-109">[out]指向的指针`ULONG`接收的大小`rgLocals`包含局部变量所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="18de6-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18de6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="18de6-110">Return Value</span></span>  
 <span data-ttu-id="18de6-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="18de6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18de6-112">要求</span><span class="sxs-lookup"><span data-stu-id="18de6-112">Requirements</span></span>  
 <span data-ttu-id="18de6-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18de6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18de6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18de6-114">See Also</span></span>  
 [<span data-ttu-id="18de6-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="18de6-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
