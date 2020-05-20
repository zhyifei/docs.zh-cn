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
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615496"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="1c463-102">ISymUnmanagedReader::GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="1c463-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="1c463-103">返回指定为模块的用户入口点的方法（如果有）。</span><span class="sxs-lookup"><span data-stu-id="1c463-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="1c463-104">例如，在 main 方法之前，此方法可以是用户的 main 方法，而不是编译器生成的存根。</span><span class="sxs-lookup"><span data-stu-id="1c463-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c463-105">语法</span><span class="sxs-lookup"><span data-stu-id="1c463-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c463-106">参数</span><span class="sxs-lookup"><span data-stu-id="1c463-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="1c463-107">弄指向接收入口点的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="1c463-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c463-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1c463-108">Return Value</span></span>  
 <span data-ttu-id="1c463-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="1c463-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c463-110">要求</span><span class="sxs-lookup"><span data-stu-id="1c463-110">Requirements</span></span>  
 <span data-ttu-id="1c463-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="1c463-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c463-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c463-112">See also</span></span>

- [<span data-ttu-id="1c463-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="1c463-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
