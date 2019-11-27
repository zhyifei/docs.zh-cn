---
title: ISymUnmanagedReader::GetUserEntryPoint 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: 50f41bb55b7c3dc45646a465032074ce90be0abf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444504"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="ec30e-102">ISymUnmanagedReader::GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="ec30e-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="ec30e-103">返回指定为模块的用户入口点的方法（如果有）。</span><span class="sxs-lookup"><span data-stu-id="ec30e-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="ec30e-104">例如，在 main 方法之前，此方法可以是用户的 main 方法，而不是编译器生成的存根。</span><span class="sxs-lookup"><span data-stu-id="ec30e-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec30e-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec30e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec30e-106">参数</span><span class="sxs-lookup"><span data-stu-id="ec30e-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="ec30e-107">弄指向接收入口点的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="ec30e-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec30e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ec30e-108">Return Value</span></span>  
 <span data-ttu-id="ec30e-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="ec30e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec30e-110">要求</span><span class="sxs-lookup"><span data-stu-id="ec30e-110">Requirements</span></span>  
 <span data-ttu-id="ec30e-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ec30e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec30e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec30e-112">See also</span></span>

- [<span data-ttu-id="ec30e-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="ec30e-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
