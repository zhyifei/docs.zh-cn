---
title: ISymUnmanagedWriter::OpenMethod 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a5e50327e74e0b893bd5f8e6f716827f2168e37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557950"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="d1a1c-102">ISymUnmanagedWriter::OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d1a1c-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="d1a1c-103">打开的符号信息发送到一个方法。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="d1a1c-104">给定的方法将成为当前方法的调用，以定义序列点、 参数和词法范围。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="d1a1c-105">没有围绕整个方法的隐式词法作用域。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="d1a1c-106">重新打开之前关闭的方法会清除任何以前定义的符号，该方法。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="d1a1c-107">一次可以有一个 open 方法。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a1c-108">语法</span><span class="sxs-lookup"><span data-stu-id="d1a1c-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1a1c-109">参数</span><span class="sxs-lookup"><span data-stu-id="d1a1c-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="d1a1c-110">[in]若要打开方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1a1c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d1a1c-111">Return Value</span></span>  
 <span data-ttu-id="d1a1c-112">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d1a1c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a1c-113">要求</span><span class="sxs-lookup"><span data-stu-id="d1a1c-113">Requirements</span></span>  
 <span data-ttu-id="d1a1c-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d1a1c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a1c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a1c-115">See also</span></span>
- [<span data-ttu-id="d1a1c-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="d1a1c-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d1a1c-117">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d1a1c-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="d1a1c-118">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="d1a1c-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
