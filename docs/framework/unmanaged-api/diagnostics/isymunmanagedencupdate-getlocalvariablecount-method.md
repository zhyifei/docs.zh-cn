---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a75ca89a3537ce8ee72e8ba24401800eacff20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153772"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="58452-102">ISymUnmanagedENCUpdate::GetLocalVariableCount 方法</span><span class="sxs-lookup"><span data-stu-id="58452-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="58452-103">获取本地变量的数目。</span><span class="sxs-lookup"><span data-stu-id="58452-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58452-104">语法</span><span class="sxs-lookup"><span data-stu-id="58452-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58452-105">参数</span><span class="sxs-lookup"><span data-stu-id="58452-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="58452-106">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="58452-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="58452-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含本地变量数所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="58452-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58452-108">返回值</span><span class="sxs-lookup"><span data-stu-id="58452-108">Return Value</span></span>  
 <span data-ttu-id="58452-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="58452-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58452-110">要求</span><span class="sxs-lookup"><span data-stu-id="58452-110">Requirements</span></span>  
 <span data-ttu-id="58452-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="58452-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58452-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="58452-112">See also</span></span>

- [<span data-ttu-id="58452-113">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="58452-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
