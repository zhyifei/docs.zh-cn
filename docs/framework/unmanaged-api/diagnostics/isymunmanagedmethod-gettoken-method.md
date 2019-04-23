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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ec6e25452a40ae67570badde8a883878d103f95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187391"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="1a43b-102">ISymUnmanagedMethod::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="1a43b-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="1a43b-103">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1a43b-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a43b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a43b-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a43b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a43b-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="1a43b-106">[out]一个指向`mdMethodDef`用于接收大小，以字符为单位，包含的元数据所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1a43b-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a43b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1a43b-107">Return Value</span></span>  
 <span data-ttu-id="1a43b-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="1a43b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a43b-109">要求</span><span class="sxs-lookup"><span data-stu-id="1a43b-109">Requirements</span></span>  
 <span data-ttu-id="1a43b-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a43b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a43b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a43b-111">See also</span></span>

- [<span data-ttu-id="1a43b-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="1a43b-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
