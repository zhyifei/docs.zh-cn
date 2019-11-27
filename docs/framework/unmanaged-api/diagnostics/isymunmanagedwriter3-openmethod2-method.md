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
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438123"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="ad844-102">ISymUnmanagedWriter3::OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="ad844-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="ad844-103">打开方法并在图像中提供其实际节偏移量。</span><span class="sxs-lookup"><span data-stu-id="ad844-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad844-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad844-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad844-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad844-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="ad844-106">中要打开的方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ad844-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="ad844-107">中图像中的节偏移量。</span><span class="sxs-lookup"><span data-stu-id="ad844-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="ad844-108">中图像中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="ad844-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad844-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ad844-109">Return Value</span></span>  
 <span data-ttu-id="ad844-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="ad844-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad844-111">要求</span><span class="sxs-lookup"><span data-stu-id="ad844-111">Requirements</span></span>  
 <span data-ttu-id="ad844-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ad844-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad844-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad844-113">See also</span></span>

- [<span data-ttu-id="ad844-114">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="ad844-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="ad844-115">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="ad844-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
