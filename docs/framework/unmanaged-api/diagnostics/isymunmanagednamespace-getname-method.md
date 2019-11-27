---
title: ISymUnmanagedNamespace::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: 43f32ac85bebc12d0a9253205aae3f1de0dc9e5b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433971"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="3ea77-102">ISymUnmanagedNamespace::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="3ea77-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="3ea77-103">获取此命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="3ea77-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea77-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ea77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ea77-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ea77-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3ea77-106">中一个 `ULONG32`，指示 `szName` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="3ea77-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3ea77-107">弄指向 `ULONG32` 的指针，该指针接收包含命名空间名称所需的缓冲区大小（包括 null 终止）。</span><span class="sxs-lookup"><span data-stu-id="3ea77-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3ea77-108">弄指向包含命名空间名称的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="3ea77-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ea77-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3ea77-109">Return Value</span></span>  
 <span data-ttu-id="3ea77-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3ea77-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea77-111">要求</span><span class="sxs-lookup"><span data-stu-id="3ea77-111">Requirements</span></span>  
 <span data-ttu-id="3ea77-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3ea77-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea77-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ea77-113">See also</span></span>

- [<span data-ttu-id="3ea77-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="3ea77-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
