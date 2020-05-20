---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: ed3c841c34b71b30f740117899353aa289e478d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614703"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="dad0d-102">ISymUnmanagedWriter2::DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="dad0d-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="dad0d-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="dad0d-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dad0d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dad0d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dad0d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dad0d-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dad0d-106">中全局变量名称。</span><span class="sxs-lookup"><span data-stu-id="dad0d-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="dad0d-107">中全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="dad0d-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="dad0d-108">中签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="dad0d-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="dad0d-109">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="dad0d-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="dad0d-110">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="dad0d-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="dad0d-111">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="dad0d-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="dad0d-112">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="dad0d-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dad0d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="dad0d-113">Return Value</span></span>  
 <span data-ttu-id="dad0d-114">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="dad0d-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dad0d-115">要求</span><span class="sxs-lookup"><span data-stu-id="dad0d-115">Requirements</span></span>  
 <span data-ttu-id="dad0d-116">**标头：** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="dad0d-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad0d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dad0d-117">See also</span></span>

- [<span data-ttu-id="dad0d-118">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="dad0d-118">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="dad0d-119">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="dad0d-119">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
