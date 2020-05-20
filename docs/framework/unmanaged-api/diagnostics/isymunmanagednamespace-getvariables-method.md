---
title: ISymUnmanagedNamespace::GetVariables 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 091f497024b48589953456e1ea6daf6635738240
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615080"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="a7505-102">ISymUnmanagedNamespace::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="a7505-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="a7505-103">返回在此命名空间中的全局范围内定义的所有变量。</span><span class="sxs-lookup"><span data-stu-id="a7505-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7505-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7505-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7505-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7505-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="a7505-106">中`ULONG32`指示数组大小的 `pVars` 。</span><span class="sxs-lookup"><span data-stu-id="a7505-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="a7505-107">弄指向的指针 `ULONG32` ，该指针接收包含命名空间所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="a7505-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="a7505-108">弄指向包含命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="a7505-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7505-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a7505-109">Return Value</span></span>  
 <span data-ttu-id="a7505-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a7505-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7505-111">要求</span><span class="sxs-lookup"><span data-stu-id="a7505-111">Requirements</span></span>  
 <span data-ttu-id="a7505-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a7505-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7505-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7505-113">See also</span></span>

- [<span data-ttu-id="a7505-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="a7505-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
