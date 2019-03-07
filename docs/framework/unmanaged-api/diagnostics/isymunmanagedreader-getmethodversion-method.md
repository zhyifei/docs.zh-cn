---
title: ISymUnmanagedReader::GetMethodVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 364742957d16f12508d2df6f4cd7f50d7956d4cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479449"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="8cd1b-102">ISymUnmanagedReader::GetMethodVersion 方法</span><span class="sxs-lookup"><span data-stu-id="8cd1b-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="8cd1b-103">获取方法版本。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-103">Gets the method version.</span></span> <span data-ttu-id="8cd1b-104">方法版本从 1 开始，在每的次递增的方法重新编译。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="8cd1b-105">重新编译可发生该方法无需进行更改。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cd1b-106">语法</span><span class="sxs-lookup"><span data-stu-id="8cd1b-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cd1b-107">参数</span><span class="sxs-lookup"><span data-stu-id="8cd1b-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="8cd1b-108">[in]要为其获取版本方法。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="8cd1b-109">[out]指向一个变量来接收方法版本的指针。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cd1b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8cd1b-110">Return Value</span></span>  
 <span data-ttu-id="8cd1b-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8cd1b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd1b-112">要求</span><span class="sxs-lookup"><span data-stu-id="8cd1b-112">Requirements</span></span>  
 <span data-ttu-id="8cd1b-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8cd1b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd1b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cd1b-114">See also</span></span>
- [<span data-ttu-id="8cd1b-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="8cd1b-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
