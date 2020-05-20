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
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610036"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="e726d-102">ISymUnmanagedWriter::OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e726d-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="e726d-103">打开要在其中发出符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="e726d-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="e726d-104">给定方法将成为定义序列点、参数和词法范围的调用的当前方法。</span><span class="sxs-lookup"><span data-stu-id="e726d-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="e726d-105">围绕整个方法，存在一个隐式词法范围。</span><span class="sxs-lookup"><span data-stu-id="e726d-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="e726d-106">重新打开先前关闭的方法将会清除以前为该方法定义的所有符号。</span><span class="sxs-lookup"><span data-stu-id="e726d-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="e726d-107">一次只能有一个 open 方法。</span><span class="sxs-lookup"><span data-stu-id="e726d-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e726d-108">语法</span><span class="sxs-lookup"><span data-stu-id="e726d-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e726d-109">参数</span><span class="sxs-lookup"><span data-stu-id="e726d-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="e726d-110">中要打开的方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e726d-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e726d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e726d-111">Return Value</span></span>  
 <span data-ttu-id="e726d-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e726d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e726d-113">要求</span><span class="sxs-lookup"><span data-stu-id="e726d-113">Requirements</span></span>  
 <span data-ttu-id="e726d-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e726d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e726d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e726d-115">See also</span></span>

- [<span data-ttu-id="e726d-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e726d-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e726d-117">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e726d-117">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="e726d-118">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="e726d-118">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)
