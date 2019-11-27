---
title: ISymUnmanagedWriter2::DefineConstant2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 6600ca7e70ac77ffba0c75812f27d388c354ece6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438327"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="3ddcf-102">ISymUnmanagedWriter2::DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="3ddcf-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="3ddcf-103">定义常数值的名称。</span><span class="sxs-lookup"><span data-stu-id="3ddcf-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddcf-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ddcf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ddcf-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ddcf-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3ddcf-106">中常量名称。</span><span class="sxs-lookup"><span data-stu-id="3ddcf-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="3ddcf-107">中常量的值。</span><span class="sxs-lookup"><span data-stu-id="3ddcf-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="3ddcf-108">中常数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3ddcf-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ddcf-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3ddcf-109">Return Value</span></span>  
 <span data-ttu-id="3ddcf-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3ddcf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ddcf-111">要求</span><span class="sxs-lookup"><span data-stu-id="3ddcf-111">Requirements</span></span>  
 <span data-ttu-id="3ddcf-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3ddcf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddcf-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ddcf-113">See also</span></span>

- [<span data-ttu-id="3ddcf-114">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="3ddcf-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="3ddcf-115">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="3ddcf-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
