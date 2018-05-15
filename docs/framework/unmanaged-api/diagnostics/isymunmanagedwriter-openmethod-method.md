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
ms.openlocfilehash: bc41acd6a4f2ef2557d3b39523c5e398c887c454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="de2b8-102">ISymUnmanagedWriter::OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="de2b8-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="de2b8-103">打开一个到哪些符号发出信息的方法。</span><span class="sxs-lookup"><span data-stu-id="de2b8-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="de2b8-104">给定的方法成为当前方法的调用定义序列点、 参数和词法范围。</span><span class="sxs-lookup"><span data-stu-id="de2b8-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="de2b8-105">没有整个方法隐式词法范围。</span><span class="sxs-lookup"><span data-stu-id="de2b8-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="de2b8-106">重新打开之前关闭的方法清除为该方法的任何先前定义的符号。</span><span class="sxs-lookup"><span data-stu-id="de2b8-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="de2b8-107">一次可以有只有一个打开方法。</span><span class="sxs-lookup"><span data-stu-id="de2b8-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2b8-108">语法</span><span class="sxs-lookup"><span data-stu-id="de2b8-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de2b8-109">参数</span><span class="sxs-lookup"><span data-stu-id="de2b8-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="de2b8-110">[in]若要打开方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="de2b8-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de2b8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="de2b8-111">Return Value</span></span>  
 <span data-ttu-id="de2b8-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="de2b8-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2b8-113">要求</span><span class="sxs-lookup"><span data-stu-id="de2b8-113">Requirements</span></span>  
 <span data-ttu-id="de2b8-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de2b8-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2b8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="de2b8-115">See Also</span></span>  
 [<span data-ttu-id="de2b8-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="de2b8-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="de2b8-117">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="de2b8-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="de2b8-118">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="de2b8-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
