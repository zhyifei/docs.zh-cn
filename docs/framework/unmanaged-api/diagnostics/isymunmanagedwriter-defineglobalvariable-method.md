---
title: ISymUnmanagedWriter::DefineGlobalVariable 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 674089f8a1076342a2479c64e253b7dda53ade87
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615197"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="00a85-102">ISymUnmanagedWriter::DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="00a85-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="00a85-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="00a85-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a85-104">语法</span><span class="sxs-lookup"><span data-stu-id="00a85-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00a85-105">参数</span><span class="sxs-lookup"><span data-stu-id="00a85-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="00a85-106">中指向 `WCHAR` 的指针，该指针定义全局变量名称。</span><span class="sxs-lookup"><span data-stu-id="00a85-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="00a85-107">中全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="00a85-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="00a85-108">中一个 `ULONG32` ，该值指示缓冲区的大小（以字符为字符） `signature` 。</span><span class="sxs-lookup"><span data-stu-id="00a85-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="00a85-109">中全局变量签名。</span><span class="sxs-lookup"><span data-stu-id="00a85-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="00a85-110">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="00a85-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="00a85-111">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="00a85-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="00a85-112">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="00a85-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="00a85-113">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="00a85-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00a85-114">返回值</span><span class="sxs-lookup"><span data-stu-id="00a85-114">Return Value</span></span>  
 <span data-ttu-id="00a85-115">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="00a85-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a85-116">要求</span><span class="sxs-lookup"><span data-stu-id="00a85-116">Requirements</span></span>  
 <span data-ttu-id="00a85-117">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="00a85-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a85-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00a85-118">See also</span></span>

- [<span data-ttu-id="00a85-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="00a85-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="00a85-120">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="00a85-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="00a85-121">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="00a85-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
