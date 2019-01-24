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
ms.openlocfilehash: b641f463eb9b664597b4806a6353278e8027d5b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709099"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="52efc-102">ISymUnmanagedWriter3::OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="52efc-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="52efc-103">打开一个方法，并提供其实际节偏移量为映像中。</span><span class="sxs-lookup"><span data-stu-id="52efc-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52efc-104">语法</span><span class="sxs-lookup"><span data-stu-id="52efc-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52efc-105">参数</span><span class="sxs-lookup"><span data-stu-id="52efc-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="52efc-106">[in]若要打开方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="52efc-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="52efc-107">[in]图像的部分偏移量。</span><span class="sxs-lookup"><span data-stu-id="52efc-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="52efc-108">[in]图像的偏移量。</span><span class="sxs-lookup"><span data-stu-id="52efc-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52efc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="52efc-109">Return Value</span></span>  
 <span data-ttu-id="52efc-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="52efc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52efc-111">要求</span><span class="sxs-lookup"><span data-stu-id="52efc-111">Requirements</span></span>  
 <span data-ttu-id="52efc-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52efc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52efc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="52efc-113">See also</span></span>
- [<span data-ttu-id="52efc-114">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="52efc-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="52efc-115">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="52efc-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
