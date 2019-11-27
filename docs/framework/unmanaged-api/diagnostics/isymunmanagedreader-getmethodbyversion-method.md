---
title: ISymUnmanagedReader::GetMethodByVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: d5f42e5ed3ce7829cfcf921f3002c238985710a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426746"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="fa4b1-102">ISymUnmanagedReader::GetMethodByVersion 方法</span><span class="sxs-lookup"><span data-stu-id="fa4b1-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="fa4b1-103">在给定方法标记和编辑和复制版本号的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="fa4b1-104">版本号从1开始，并在每次通过编辑和复制操作更改方法时递增。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa4b1-105">语法</span><span class="sxs-lookup"><span data-stu-id="fa4b1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa4b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="fa4b1-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="fa4b1-107">中方法标记。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="fa4b1-108">中方法版本。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fa4b1-109">弄指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa4b1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="fa4b1-110">Return Value</span></span>  
 <span data-ttu-id="fa4b1-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fa4b1-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa4b1-112">要求</span><span class="sxs-lookup"><span data-stu-id="fa4b1-112">Requirements</span></span>  
 <span data-ttu-id="fa4b1-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fa4b1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4b1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa4b1-114">See also</span></span>

- [<span data-ttu-id="fa4b1-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="fa4b1-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
