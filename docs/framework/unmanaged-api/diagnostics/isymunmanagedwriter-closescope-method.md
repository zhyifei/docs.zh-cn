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
ms.openlocfilehash: 4d8790dc68bc063deed4c58ba0df8e9ea258b9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610075"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="2bbdf-102">ISymUnmanagedWriter::CloseScope 方法</span><span class="sxs-lookup"><span data-stu-id="2bbdf-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="2bbdf-103">关闭当前词法范围。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bbdf-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bbdf-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bbdf-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bbdf-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="2bbdf-106">中词法范围中最后一个指令结束时点的方法开头的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bbdf-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2bbdf-107">Return Value</span></span>  
 <span data-ttu-id="2bbdf-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bbdf-109">备注</span><span class="sxs-lookup"><span data-stu-id="2bbdf-109">Remarks</span></span>  
 <span data-ttu-id="2bbdf-110">范围结束后，不能再定义更多变量。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="2bbdf-111">[ISymUnmanagedWriter：： OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回一个不透明的范围标识符，该标识符可与[ISymUnmanagedWriter：： SetScopeRange](isymunmanagedwriter-setscoperange-method.md)一起使用，以便稍后定义作用域的起始和结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="2bbdf-112">在这种情况下，忽略传递到 `ISymUnmanagedWriter::OpenScope` 和 `ISymUnmanagedWriter::CloseScope` 的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="2bbdf-113">范围标识符只在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="2bbdf-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bbdf-114">要求</span><span class="sxs-lookup"><span data-stu-id="2bbdf-114">Requirements</span></span>  
 <span data-ttu-id="2bbdf-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2bbdf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbdf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bbdf-116">See also</span></span>

- [<span data-ttu-id="2bbdf-117">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="2bbdf-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
