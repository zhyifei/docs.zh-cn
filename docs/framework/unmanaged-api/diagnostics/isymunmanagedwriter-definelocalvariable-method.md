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
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614820"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="e7024-102">ISymUnmanagedWriter::DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="e7024-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="e7024-103">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="e7024-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="e7024-104">对于在整个范围内具有多个住宅的同名变量，可以多次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="e7024-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="e7024-105">但在这种情况下， `startOffset` 和参数的值 `endOffset` 不能重叠。</span><span class="sxs-lookup"><span data-stu-id="e7024-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7024-106">语法</span><span class="sxs-lookup"><span data-stu-id="e7024-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e7024-107">参数</span><span class="sxs-lookup"><span data-stu-id="e7024-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e7024-108">中指向 `WCHAR` 的指针，该指针定义局部变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e7024-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="e7024-109">中局部变量特性。</span><span class="sxs-lookup"><span data-stu-id="e7024-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e7024-110">中一个 `ULONG32` ，该值指示缓冲区的大小（以字节为单位） `signature` 。</span><span class="sxs-lookup"><span data-stu-id="e7024-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="e7024-111">中局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="e7024-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="e7024-112">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="e7024-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="e7024-113">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="e7024-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="e7024-114">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="e7024-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="e7024-115">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="e7024-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="e7024-116">中变量的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7024-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="e7024-117">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="e7024-117">This parameter is optional.</span></span> <span data-ttu-id="e7024-118">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="e7024-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="e7024-119">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="e7024-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e7024-120">中变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7024-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="e7024-121">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="e7024-121">This parameter is optional.</span></span> <span data-ttu-id="e7024-122">如果为0，则忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="e7024-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="e7024-123">如果它是非零值，则该变量将处于当前范围的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="e7024-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7024-124">返回值</span><span class="sxs-lookup"><span data-stu-id="e7024-124">Return Value</span></span>  
 <span data-ttu-id="e7024-125">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e7024-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7024-126">要求</span><span class="sxs-lookup"><span data-stu-id="e7024-126">Requirements</span></span>  
 <span data-ttu-id="e7024-127">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e7024-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7024-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7024-128">See also</span></span>

- [<span data-ttu-id="e7024-129">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e7024-129">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e7024-130">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="e7024-130">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="e7024-131">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="e7024-131">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
