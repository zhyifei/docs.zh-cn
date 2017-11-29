---
title: "ISymUnmanagedWriter::CloseScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8df22e5f9ea2ca294f502fcebf4b2ed5cd7900d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="ace99-102">ISymUnmanagedWriter::CloseScope 方法</span><span class="sxs-lookup"><span data-stu-id="ace99-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="ace99-103">关闭当前词法范围。</span><span class="sxs-lookup"><span data-stu-id="ace99-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace99-104">语法</span><span class="sxs-lookup"><span data-stu-id="ace99-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ace99-105">参数</span><span class="sxs-lookup"><span data-stu-id="ace99-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="ace99-106">[in]从位于词法作用域，以字节为单位中的最后一个指令的末尾的点方法的开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="ace99-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ace99-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ace99-107">Return Value</span></span>  
 <span data-ttu-id="ace99-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="ace99-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ace99-109">备注</span><span class="sxs-lookup"><span data-stu-id="ace99-109">Remarks</span></span>  
 <span data-ttu-id="ace99-110">一旦关闭作用域时，可以在其中定义没有更多的变量。</span><span class="sxs-lookup"><span data-stu-id="ace99-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="ace99-111">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)返回可以用于一个不透明的作用域标识符[isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)以更高版本定义的作用域的起始和结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="ace99-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="ace99-112">在这种情况下，忽略传递到 `ISymUnmanagedWriter::OpenScope` 和 `ISymUnmanagedWriter::CloseScope` 的偏移量。</span><span class="sxs-lookup"><span data-stu-id="ace99-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="ace99-113">范围标识符是仅在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="ace99-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace99-114">要求</span><span class="sxs-lookup"><span data-stu-id="ace99-114">Requirements</span></span>  
 <span data-ttu-id="ace99-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ace99-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace99-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ace99-116">See Also</span></span>  
 [<span data-ttu-id="ace99-117">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="ace99-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
