---
title: ISymUnmanagedMethod::GetToken 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 0803f0b55f19b779f5b6608a9f8200d2b085b504
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615151"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="741c0-102">ISymUnmanagedMethod::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="741c0-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="741c0-103">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="741c0-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="741c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="741c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="741c0-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="741c0-106">弄指向的指针， `mdMethodDef` 该指针接收包含元数据所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="741c0-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="741c0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="741c0-107">Return Value</span></span>  
 <span data-ttu-id="741c0-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="741c0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="741c0-109">要求</span><span class="sxs-lookup"><span data-stu-id="741c0-109">Requirements</span></span>  
 <span data-ttu-id="741c0-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="741c0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741c0-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="741c0-111">See also</span></span>

- [<span data-ttu-id="741c0-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="741c0-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
