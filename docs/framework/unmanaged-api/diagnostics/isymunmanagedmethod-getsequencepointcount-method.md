---
title: ISymUnmanagedMethod::GetSequencePointCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: a44f81deb2d57b49f1fd0650fa52c06383210352
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614430"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="564c0-102">ISymUnmanagedMethod::GetSequencePointCount 方法</span><span class="sxs-lookup"><span data-stu-id="564c0-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="564c0-103">获取此方法中序列点的计数。</span><span class="sxs-lookup"><span data-stu-id="564c0-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="564c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="564c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="564c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="564c0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="564c0-106">弄指向的指针 `ULONG32` ，该指针接收包含序列点所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="564c0-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="564c0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="564c0-107">Return Value</span></span>  
 <span data-ttu-id="564c0-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="564c0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="564c0-109">要求</span><span class="sxs-lookup"><span data-stu-id="564c0-109">Requirements</span></span>  
 <span data-ttu-id="564c0-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="564c0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564c0-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="564c0-111">See also</span></span>

- [<span data-ttu-id="564c0-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="564c0-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
