---
title: ISymUnmanagedWriter2::DefineLocalVariable2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53f02499bbc64f1502951ff9fbf16a848e77f0ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430803"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="e46c3-102">ISymUnmanagedWriter2::DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="e46c3-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="e46c3-103">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="e46c3-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="e46c3-104">在范围内具有多个 home 具有相同名称的变量，此方法可以调用多次。</span><span class="sxs-lookup"><span data-stu-id="e46c3-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="e46c3-105">在此情况下，但是，值`startOffset`和`endOffset`参数不能重叠。</span><span class="sxs-lookup"><span data-stu-id="e46c3-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46c3-106">语法</span><span class="sxs-lookup"><span data-stu-id="e46c3-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e46c3-107">参数</span><span class="sxs-lookup"><span data-stu-id="e46c3-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e46c3-108">[in]本地的变量名称。</span><span class="sxs-lookup"><span data-stu-id="e46c3-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="e46c3-109">[in]本地变量的特性。</span><span class="sxs-lookup"><span data-stu-id="e46c3-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="e46c3-110">[in]签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e46c3-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="e46c3-111">[in]地址类型中。</span><span class="sxs-lookup"><span data-stu-id="e46c3-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="e46c3-112">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="e46c3-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="e46c3-113">[in]参数规范第二个地址。</span><span class="sxs-lookup"><span data-stu-id="e46c3-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="e46c3-114">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="e46c3-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="e46c3-115">[in]变量起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="e46c3-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="e46c3-116">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="e46c3-116">This parameter is optional.</span></span> <span data-ttu-id="e46c3-117">如果该值为 0，将忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="e46c3-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="e46c3-118">如果它为非零值，该变量将位于偏移量的当前作用域内。</span><span class="sxs-lookup"><span data-stu-id="e46c3-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e46c3-119">[in]变量结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="e46c3-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="e46c3-120">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="e46c3-120">This parameter is optional.</span></span> <span data-ttu-id="e46c3-121">如果该值为 0，将忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="e46c3-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="e46c3-122">如果它为非零值，该变量将位于偏移量的当前作用域内。</span><span class="sxs-lookup"><span data-stu-id="e46c3-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e46c3-123">返回值</span><span class="sxs-lookup"><span data-stu-id="e46c3-123">Return Value</span></span>  
 <span data-ttu-id="e46c3-124">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e46c3-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e46c3-125">要求</span><span class="sxs-lookup"><span data-stu-id="e46c3-125">Requirements</span></span>  
 <span data-ttu-id="e46c3-126">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="e46c3-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46c3-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e46c3-127">See Also</span></span>  
 [<span data-ttu-id="e46c3-128">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="e46c3-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="e46c3-129">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="e46c3-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
