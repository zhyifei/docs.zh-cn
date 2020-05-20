---
title: ISymUnmanagedConstant::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 2dd70693528904459a34689dbad944c65c971254
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441638"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="57dfa-102">ISymUnmanagedConstant::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="57dfa-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="57dfa-103">获取常数的名称。</span><span class="sxs-lookup"><span data-stu-id="57dfa-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57dfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="57dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57dfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="57dfa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="57dfa-106">中参数指向的缓冲区的长度 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="57dfa-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="57dfa-107">弄指向的指针， `ULONG32` 该指针接收包含名称（包括 null 终止）所需的缓冲区的大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="57dfa-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="57dfa-108">弄存储名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="57dfa-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57dfa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="57dfa-109">Return Value</span></span>  
 <span data-ttu-id="57dfa-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="57dfa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57dfa-111">要求</span><span class="sxs-lookup"><span data-stu-id="57dfa-111">Requirements</span></span>  
 <span data-ttu-id="57dfa-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="57dfa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57dfa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57dfa-113">See also</span></span>

- [<span data-ttu-id="57dfa-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="57dfa-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="57dfa-115">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="57dfa-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="57dfa-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="57dfa-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
