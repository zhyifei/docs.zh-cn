---
title: ISymUnmanagedScope::GetEndOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e28a351b6d47d14f171b9e760b2fa2c6755e3f8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986176"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="7ff29-102">ISymUnmanagedScope::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7ff29-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="7ff29-103">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="7ff29-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff29-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ff29-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff29-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ff29-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7ff29-106">[out]一个指向`ULONG32`，它接收的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="7ff29-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ff29-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7ff29-107">Return Value</span></span>  
 <span data-ttu-id="7ff29-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7ff29-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff29-109">要求</span><span class="sxs-lookup"><span data-stu-id="7ff29-109">Requirements</span></span>  
 <span data-ttu-id="7ff29-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7ff29-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff29-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ff29-111">See also</span></span>

- [<span data-ttu-id="7ff29-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="7ff29-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="7ff29-113">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7ff29-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
