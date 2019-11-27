---
title: ISymUnmanagedWriter::DefineLocalVariable 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: f6a741df3ea57b5e9b4fa8bc5d304bfedd1d6c15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428010"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="818f2-102">ISymUnmanagedWriter::DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="818f2-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="818f2-103">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="818f2-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="818f2-104">对于在整个范围内具有多个住宅的同名变量，可以多次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="818f2-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="818f2-105">但在这种情况下，`startOffset` 和 `endOffset` 参数的值不得重叠。</span><span class="sxs-lookup"><span data-stu-id="818f2-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="818f2-106">语法</span><span class="sxs-lookup"><span data-stu-id="818f2-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="818f2-107">参数</span><span class="sxs-lookup"><span data-stu-id="818f2-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="818f2-108">中一个指针，指向用于定义局部变量名称的 `WCHAR`。</span><span class="sxs-lookup"><span data-stu-id="818f2-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="818f2-109">中局部变量特性。</span><span class="sxs-lookup"><span data-stu-id="818f2-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="818f2-110">中一个 `ULONG32`，指示 `signature` 缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="818f2-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="818f2-111">中局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="818f2-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="818f2-112">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="818f2-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="818f2-113">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="818f2-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="818f2-114">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="818f2-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="818f2-115">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="818f2-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="818f2-116">中变量的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="818f2-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="818f2-117">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="818f2-117">This parameter is optional.</span></span> <span data-ttu-id="818f2-118">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="818f2-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="818f2-119">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="818f2-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="818f2-120">中变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="818f2-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="818f2-121">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="818f2-121">This parameter is optional.</span></span> <span data-ttu-id="818f2-122">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="818f2-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="818f2-123">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="818f2-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="818f2-124">返回值</span><span class="sxs-lookup"><span data-stu-id="818f2-124">Return Value</span></span>  
 <span data-ttu-id="818f2-125">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="818f2-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="818f2-126">要求</span><span class="sxs-lookup"><span data-stu-id="818f2-126">Requirements</span></span>  
 <span data-ttu-id="818f2-127">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="818f2-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818f2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="818f2-128">See also</span></span>

- [<span data-ttu-id="818f2-129">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="818f2-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="818f2-130">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="818f2-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="818f2-131">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="818f2-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
