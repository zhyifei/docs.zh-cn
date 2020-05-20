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
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614690"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="18baa-102">ISymUnmanagedWriter2::DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="18baa-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="18baa-103">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="18baa-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="18baa-104">对于在整个范围内具有多个住宅的同名变量，可以多次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="18baa-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="18baa-105">但在这种情况下， `startOffset` 和参数的值 `endOffset` 不能重叠。</span><span class="sxs-lookup"><span data-stu-id="18baa-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18baa-106">语法</span><span class="sxs-lookup"><span data-stu-id="18baa-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="18baa-107">参数</span><span class="sxs-lookup"><span data-stu-id="18baa-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="18baa-108">中局部变量名称。</span><span class="sxs-lookup"><span data-stu-id="18baa-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="18baa-109">中局部变量特性。</span><span class="sxs-lookup"><span data-stu-id="18baa-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="18baa-110">中签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="18baa-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="18baa-111">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="18baa-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="18baa-112">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="18baa-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="18baa-113">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="18baa-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="18baa-114">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="18baa-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="18baa-115">中变量的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="18baa-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="18baa-116">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="18baa-116">This parameter is optional.</span></span> <span data-ttu-id="18baa-117">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="18baa-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="18baa-118">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="18baa-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="18baa-119">中变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="18baa-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="18baa-120">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="18baa-120">This parameter is optional.</span></span> <span data-ttu-id="18baa-121">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="18baa-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="18baa-122">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="18baa-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18baa-123">返回值</span><span class="sxs-lookup"><span data-stu-id="18baa-123">Return Value</span></span>  
 <span data-ttu-id="18baa-124">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="18baa-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18baa-125">要求</span><span class="sxs-lookup"><span data-stu-id="18baa-125">Requirements</span></span>  
 <span data-ttu-id="18baa-126">**标头：** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="18baa-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18baa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18baa-127">See also</span></span>

- [<span data-ttu-id="18baa-128">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="18baa-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="18baa-129">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="18baa-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
