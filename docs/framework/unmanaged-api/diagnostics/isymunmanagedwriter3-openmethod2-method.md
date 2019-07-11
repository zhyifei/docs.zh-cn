---
title: ISymUnmanagedWriter3::OpenMethod2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e686e332cf1d35537e5d4306a3a9cbf9d46c47e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752365"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="40616-102">ISymUnmanagedWriter3::OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="40616-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="40616-103">打开一个方法，并提供其实际节偏移量为映像中。</span><span class="sxs-lookup"><span data-stu-id="40616-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40616-104">语法</span><span class="sxs-lookup"><span data-stu-id="40616-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40616-105">参数</span><span class="sxs-lookup"><span data-stu-id="40616-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="40616-106">[in]若要打开方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="40616-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="40616-107">[in]图像的部分偏移量。</span><span class="sxs-lookup"><span data-stu-id="40616-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="40616-108">[in]图像的偏移量。</span><span class="sxs-lookup"><span data-stu-id="40616-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40616-109">返回值</span><span class="sxs-lookup"><span data-stu-id="40616-109">Return Value</span></span>  
 <span data-ttu-id="40616-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="40616-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40616-111">要求</span><span class="sxs-lookup"><span data-stu-id="40616-111">Requirements</span></span>  
 <span data-ttu-id="40616-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40616-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40616-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="40616-113">See also</span></span>

- [<span data-ttu-id="40616-114">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="40616-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="40616-115">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="40616-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
