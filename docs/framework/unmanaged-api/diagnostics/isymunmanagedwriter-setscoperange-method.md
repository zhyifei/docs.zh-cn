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
ms.openlocfilehash: 495089ca33df3b36656da149da45019c30b81d39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428721"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="6dbe7-102">ISymUnmanagedWriter::SetScopeRange 方法</span><span class="sxs-lookup"><span data-stu-id="6dbe7-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="6dbe7-103">定义指定词法范围的偏移量范围。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="6dbe7-104">作用域成为新的当前范围和推送到堆栈的作用域。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="6dbe7-105">作用域必须形成一个层次结构。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="6dbe7-106">同级不允许重叠。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbe7-107">语法</span><span class="sxs-lookup"><span data-stu-id="6dbe7-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dbe7-108">参数</span><span class="sxs-lookup"><span data-stu-id="6dbe7-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="6dbe7-109">[in]作用域的作用域标识符。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="6dbe7-110">[in]偏移量，以字节为单位，从开始处的词法作用域中的方法的第一个指令。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="6dbe7-111">[in]偏移量，以字节为单位的方法从开始处的词法范围中最后一个指令。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dbe7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6dbe7-112">Return Value</span></span>  
 <span data-ttu-id="6dbe7-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dbe7-114">备注</span><span class="sxs-lookup"><span data-stu-id="6dbe7-114">Remarks</span></span>  
 <span data-ttu-id="6dbe7-115">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回可以用于一个不透明的作用域标识符`ISymUnmanagedWriter::SetScopeRange`若要定义的作用域的起始和结束偏移量在更高版本时。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="6dbe7-116">在这种情况下，偏移量传递给`ISymUnmanagedWriter::OpenScope`和[isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)将被忽略。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="6dbe7-117">范围标识符只会在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="6dbe7-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbe7-118">要求</span><span class="sxs-lookup"><span data-stu-id="6dbe7-118">Requirements</span></span>  
 <span data-ttu-id="6dbe7-119">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6dbe7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbe7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dbe7-120">See Also</span></span>  
 [<span data-ttu-id="6dbe7-121">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6dbe7-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
