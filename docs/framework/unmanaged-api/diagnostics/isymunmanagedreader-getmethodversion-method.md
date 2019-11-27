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
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436007"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="f1339-102">ISymUnmanagedReader::GetMethodVersion 方法</span><span class="sxs-lookup"><span data-stu-id="f1339-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="f1339-103">获取方法版本。</span><span class="sxs-lookup"><span data-stu-id="f1339-103">Gets the method version.</span></span> <span data-ttu-id="f1339-104">方法版本从1开始，并在每次重新编译方法时递增。</span><span class="sxs-lookup"><span data-stu-id="f1339-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="f1339-105">重新编译可能会发生，而不会对方法进行更改。</span><span class="sxs-lookup"><span data-stu-id="f1339-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1339-106">语法</span><span class="sxs-lookup"><span data-stu-id="f1339-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1339-107">参数</span><span class="sxs-lookup"><span data-stu-id="f1339-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="f1339-108">中要获取其版本的方法。</span><span class="sxs-lookup"><span data-stu-id="f1339-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="f1339-109">弄指向接收方法版本的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="f1339-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1339-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f1339-110">Return Value</span></span>  
 <span data-ttu-id="f1339-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="f1339-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1339-112">要求</span><span class="sxs-lookup"><span data-stu-id="f1339-112">Requirements</span></span>  
 <span data-ttu-id="f1339-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="f1339-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1339-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1339-114">See also</span></span>

- [<span data-ttu-id="f1339-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="f1339-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
