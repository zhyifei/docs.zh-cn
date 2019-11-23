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
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427917"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="095d9-102">ISymUnmanagedWriter::OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="095d9-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="095d9-103">Opens a method into which symbol information is emitted.</span><span class="sxs-lookup"><span data-stu-id="095d9-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="095d9-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span><span class="sxs-lookup"><span data-stu-id="095d9-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="095d9-105">There is an implicit lexical scope around the entire method.</span><span class="sxs-lookup"><span data-stu-id="095d9-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="095d9-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span><span class="sxs-lookup"><span data-stu-id="095d9-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="095d9-107">There can be only one open method at a time.</span><span class="sxs-lookup"><span data-stu-id="095d9-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="095d9-108">语法</span><span class="sxs-lookup"><span data-stu-id="095d9-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="095d9-109">参数</span><span class="sxs-lookup"><span data-stu-id="095d9-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="095d9-110">[in] The metadata token for the method to be opened.</span><span class="sxs-lookup"><span data-stu-id="095d9-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="095d9-111">返回值</span><span class="sxs-lookup"><span data-stu-id="095d9-111">Return Value</span></span>  
 <span data-ttu-id="095d9-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="095d9-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="095d9-113">要求</span><span class="sxs-lookup"><span data-stu-id="095d9-113">Requirements</span></span>  
 <span data-ttu-id="095d9-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="095d9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="095d9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="095d9-115">See also</span></span>

- [<span data-ttu-id="095d9-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="095d9-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="095d9-117">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="095d9-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="095d9-118">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="095d9-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
