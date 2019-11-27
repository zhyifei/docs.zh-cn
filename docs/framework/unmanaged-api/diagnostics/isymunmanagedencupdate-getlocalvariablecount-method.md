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
ms.openlocfilehash: cba4af737cc6a6441d38ba0f940fffe54f5c4f09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449062"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="29495-102">ISymUnmanagedENCUpdate::GetLocalVariableCount 方法</span><span class="sxs-lookup"><span data-stu-id="29495-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="29495-103">获取局部变量的数目。</span><span class="sxs-lookup"><span data-stu-id="29495-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29495-104">语法</span><span class="sxs-lookup"><span data-stu-id="29495-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29495-105">参数</span><span class="sxs-lookup"><span data-stu-id="29495-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="29495-106">中方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="29495-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="29495-107">弄指向 `ULONG32` 的指针，该指针接收包含局部变量数所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="29495-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29495-108">返回值</span><span class="sxs-lookup"><span data-stu-id="29495-108">Return Value</span></span>  
 <span data-ttu-id="29495-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="29495-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29495-110">要求</span><span class="sxs-lookup"><span data-stu-id="29495-110">Requirements</span></span>  
 <span data-ttu-id="29495-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="29495-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29495-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29495-112">See also</span></span>

- [<span data-ttu-id="29495-113">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="29495-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
