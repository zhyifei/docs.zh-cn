---
title: ISymUnmanagedWriter::CloseScope 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428075"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="6982c-102">ISymUnmanagedWriter::CloseScope 方法</span><span class="sxs-lookup"><span data-stu-id="6982c-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="6982c-103">关闭当前词法范围。</span><span class="sxs-lookup"><span data-stu-id="6982c-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6982c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6982c-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6982c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6982c-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="6982c-106">中词法范围中最后一个指令结束时点的方法开头的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6982c-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6982c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6982c-107">Return Value</span></span>  
 <span data-ttu-id="6982c-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="6982c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6982c-109">备注</span><span class="sxs-lookup"><span data-stu-id="6982c-109">Remarks</span></span>  
 <span data-ttu-id="6982c-110">范围结束后，不能再定义更多变量。</span><span class="sxs-lookup"><span data-stu-id="6982c-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="6982c-111">[ISymUnmanagedWriter：： OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回一个不透明的范围标识符，该标识符可与[ISymUnmanagedWriter：： SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)一起使用，以便稍后定义作用域的起始和结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="6982c-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="6982c-112">在这种情况下，忽略传递到 `ISymUnmanagedWriter::OpenScope` 和 `ISymUnmanagedWriter::CloseScope` 的偏移量。</span><span class="sxs-lookup"><span data-stu-id="6982c-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="6982c-113">范围标识符只在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="6982c-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6982c-114">要求</span><span class="sxs-lookup"><span data-stu-id="6982c-114">Requirements</span></span>  
 <span data-ttu-id="6982c-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="6982c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6982c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6982c-116">See also</span></span>

- [<span data-ttu-id="6982c-117">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6982c-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
