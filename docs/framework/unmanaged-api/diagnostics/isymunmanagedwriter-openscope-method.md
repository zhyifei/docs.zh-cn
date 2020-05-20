---
title: ISymUnmanagedWriter::OpenScope 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 4008b2a7d785781da5f35b3dc1e564487cb8e760
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609776"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="2983f-102">ISymUnmanagedWriter::OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="2983f-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="2983f-103">在当前方法中打开新的词法范围。</span><span class="sxs-lookup"><span data-stu-id="2983f-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="2983f-104">范围将成为新的当前范围，并推送到作用域的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="2983f-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="2983f-105">范围必须构成层次结构。</span><span class="sxs-lookup"><span data-stu-id="2983f-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="2983f-106">同级不允许重叠。</span><span class="sxs-lookup"><span data-stu-id="2983f-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2983f-107">语法</span><span class="sxs-lookup"><span data-stu-id="2983f-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2983f-108">参数</span><span class="sxs-lookup"><span data-stu-id="2983f-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="2983f-109">中词法范围中第一个指令的偏移量（以字节为单位），从方法的开头开始。</span><span class="sxs-lookup"><span data-stu-id="2983f-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2983f-110">弄指向的指针 `ULONG32` ，该指针接收作用域标识符。</span><span class="sxs-lookup"><span data-stu-id="2983f-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2983f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2983f-111">Return Value</span></span>  
 <span data-ttu-id="2983f-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2983f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2983f-113">备注</span><span class="sxs-lookup"><span data-stu-id="2983f-113">Remarks</span></span>  
 <span data-ttu-id="2983f-114">`ISymUnmanagedWriter::OpenScope`返回一个不透明的范围标识符，该标识符可以与[ISymUnmanagedWriter：： SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)一起使用，以定义范围的起始和结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="2983f-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="2983f-115">在这种情况下，将忽略传递到 `ISymUnmanagedWriter::OpenScope` 和[ISymUnmanagedWriter：： CloseScope](isymunmanagedwriter-closescope-method.md)的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2983f-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="2983f-116">范围标识符只在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="2983f-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2983f-117">要求</span><span class="sxs-lookup"><span data-stu-id="2983f-117">Requirements</span></span>  
 <span data-ttu-id="2983f-118">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2983f-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2983f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2983f-119">See also</span></span>

- [<span data-ttu-id="2983f-120">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="2983f-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
