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
ms.openlocfilehash: 0c112819ef3bc4f9a7146ee80f55202ff89d689a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178320"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="09dd8-102">ISymUnmanagedWriter3::OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="09dd8-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="09dd8-103">打开方法并在图像中提供其实际截面偏移。</span><span class="sxs-lookup"><span data-stu-id="09dd8-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09dd8-104">语法</span><span class="sxs-lookup"><span data-stu-id="09dd8-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09dd8-105">parameters</span><span class="sxs-lookup"><span data-stu-id="09dd8-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="09dd8-106">[在]要打开的方法的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="09dd8-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="09dd8-107">[在]图像中的截面偏移。</span><span class="sxs-lookup"><span data-stu-id="09dd8-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="09dd8-108">[在]图像中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="09dd8-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09dd8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="09dd8-109">Return Value</span></span>  
 <span data-ttu-id="09dd8-110">如果方法成功，S_OK;否则，E_FAIL或其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="09dd8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09dd8-111">要求</span><span class="sxs-lookup"><span data-stu-id="09dd8-111">Requirements</span></span>  
 <span data-ttu-id="09dd8-112">**标题：** 科西姆.伊德尔，科西姆.h</span><span class="sxs-lookup"><span data-stu-id="09dd8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09dd8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09dd8-113">See also</span></span>

- [<span data-ttu-id="09dd8-114">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="09dd8-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="09dd8-115">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="09dd8-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
