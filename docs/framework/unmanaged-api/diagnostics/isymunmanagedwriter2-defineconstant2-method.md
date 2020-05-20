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
ms.openlocfilehash: 70ee853ff657a75dcc4df1454c4354f9d3f8202f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614716"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="cb59d-102">ISymUnmanagedWriter2::DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="cb59d-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="cb59d-103">定义常数值的名称。</span><span class="sxs-lookup"><span data-stu-id="cb59d-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb59d-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb59d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb59d-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb59d-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cb59d-106">中常量名称。</span><span class="sxs-lookup"><span data-stu-id="cb59d-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="cb59d-107">中常量的值。</span><span class="sxs-lookup"><span data-stu-id="cb59d-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="cb59d-108">中常数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="cb59d-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb59d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cb59d-109">Return Value</span></span>  
 <span data-ttu-id="cb59d-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="cb59d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb59d-111">要求</span><span class="sxs-lookup"><span data-stu-id="cb59d-111">Requirements</span></span>  
 <span data-ttu-id="cb59d-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cb59d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb59d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb59d-113">See also</span></span>

- [<span data-ttu-id="cb59d-114">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="cb59d-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="cb59d-115">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="cb59d-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
