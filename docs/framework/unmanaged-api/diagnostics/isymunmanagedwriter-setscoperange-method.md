---
title: ISymUnmanagedWriter::SetScopeRange 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da50542d9f57e008b31ce2e6ed9698df1275d5eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618801"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="eb48b-102">ISymUnmanagedWriter::SetScopeRange 方法</span><span class="sxs-lookup"><span data-stu-id="eb48b-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="eb48b-103">定义指定词法范围的偏移量范围。</span><span class="sxs-lookup"><span data-stu-id="eb48b-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="eb48b-104">范围将成为新的当前作用域，并推送到的作用域堆栈上。</span><span class="sxs-lookup"><span data-stu-id="eb48b-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="eb48b-105">作用域必须形成层次结构。</span><span class="sxs-lookup"><span data-stu-id="eb48b-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="eb48b-106">同级不能重叠。</span><span class="sxs-lookup"><span data-stu-id="eb48b-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb48b-107">语法</span><span class="sxs-lookup"><span data-stu-id="eb48b-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb48b-108">参数</span><span class="sxs-lookup"><span data-stu-id="eb48b-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="eb48b-109">[in]作用域范围标识符。</span><span class="sxs-lookup"><span data-stu-id="eb48b-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="eb48b-110">[in]偏移量，以字节为单位，从开始处的词法作用域中的第一个指令的方法。</span><span class="sxs-lookup"><span data-stu-id="eb48b-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="eb48b-111">[in]偏移量，以字节为单位，从开始处的词法作用域中的最后一个指令的方法。</span><span class="sxs-lookup"><span data-stu-id="eb48b-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb48b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="eb48b-112">Return Value</span></span>  
 <span data-ttu-id="eb48b-113">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="eb48b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb48b-114">备注</span><span class="sxs-lookup"><span data-stu-id="eb48b-114">Remarks</span></span>  
 <span data-ttu-id="eb48b-115">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回可用于不透明的范围标识符`ISymUnmanagedWriter::SetScopeRange`来定义范围的起始和结束偏移量在更高版本时。</span><span class="sxs-lookup"><span data-stu-id="eb48b-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="eb48b-116">在这种情况下，偏移量传递给`ISymUnmanagedWriter::OpenScope`并[isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)将被忽略。</span><span class="sxs-lookup"><span data-stu-id="eb48b-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="eb48b-117">范围标识符只是在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="eb48b-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb48b-118">要求</span><span class="sxs-lookup"><span data-stu-id="eb48b-118">Requirements</span></span>  
 <span data-ttu-id="eb48b-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eb48b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb48b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb48b-120">See also</span></span>
- [<span data-ttu-id="eb48b-121">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="eb48b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
