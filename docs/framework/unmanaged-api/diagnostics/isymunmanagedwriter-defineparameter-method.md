---
title: ISymUnmanagedWriter::DefineParameter 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: bc1b65de026a674a3dff183050a5a205fd7052c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427996"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="262f6-102">ISymUnmanagedWriter::DefineParameter 方法</span><span class="sxs-lookup"><span data-stu-id="262f6-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="262f6-103">在当前方法中定义一个参数。</span><span class="sxs-lookup"><span data-stu-id="262f6-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="262f6-104">参数类型从参数在方法签名中的位置（序列）中获取。</span><span class="sxs-lookup"><span data-stu-id="262f6-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="262f6-105">如果在给定方法的元数据中定义了参数，则无需使用此方法再次定义这些参数。</span><span class="sxs-lookup"><span data-stu-id="262f6-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="262f6-106">符号读取器必须在检查符号存储区之前检查参数的正常元数据。</span><span class="sxs-lookup"><span data-stu-id="262f6-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262f6-107">语法</span><span class="sxs-lookup"><span data-stu-id="262f6-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="262f6-108">参数</span><span class="sxs-lookup"><span data-stu-id="262f6-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="262f6-109">中参数名称。</span><span class="sxs-lookup"><span data-stu-id="262f6-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="262f6-110">中参数特性。</span><span class="sxs-lookup"><span data-stu-id="262f6-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="262f6-111">中参数签名。</span><span class="sxs-lookup"><span data-stu-id="262f6-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="262f6-112">中地址类型。</span><span class="sxs-lookup"><span data-stu-id="262f6-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="262f6-113">中参数规范的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="262f6-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="262f6-114">中参数规范的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="262f6-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="262f6-115">中参数规范的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="262f6-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="262f6-116">返回值</span><span class="sxs-lookup"><span data-stu-id="262f6-116">Return Value</span></span>  
 <span data-ttu-id="262f6-117">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="262f6-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="262f6-118">要求</span><span class="sxs-lookup"><span data-stu-id="262f6-118">Requirements</span></span>  
 <span data-ttu-id="262f6-119">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="262f6-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262f6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="262f6-120">See also</span></span>

- [<span data-ttu-id="262f6-121">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="262f6-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
