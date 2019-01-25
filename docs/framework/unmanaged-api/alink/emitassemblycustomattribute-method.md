---
title: EmitAssemblyCustomAttribute 方法
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b4909ae23d077ee079e062d0252dbf1ee11663c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538825"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="6b103-102">EmitAssemblyCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="6b103-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="6b103-103">调用以设置程序集级别自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6b103-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b103-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b103-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b103-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b103-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6b103-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="6b103-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6b103-107">定义该属性的文件。</span><span class="sxs-lookup"><span data-stu-id="6b103-107">File that defiles the attribute.</span></span> <span data-ttu-id="6b103-108">可以为 NULL，如果`AssemblyID`并不表示未绑定的 netmodule。</span><span class="sxs-lookup"><span data-stu-id="6b103-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6b103-109">自定义特性的类型。</span><span class="sxs-lookup"><span data-stu-id="6b103-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="6b103-110">自定义值的数据。</span><span class="sxs-lookup"><span data-stu-id="6b103-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="6b103-111">自定义值数据的长度。</span><span class="sxs-lookup"><span data-stu-id="6b103-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="6b103-112">如果自定义特性与程序集签名，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6b103-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="6b103-113">如果要在发出多个属性，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6b103-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b103-114">返回值</span><span class="sxs-lookup"><span data-stu-id="6b103-114">Return Value</span></span>  
 <span data-ttu-id="6b103-115">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="6b103-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b103-116">要求</span><span class="sxs-lookup"><span data-stu-id="6b103-116">Requirements</span></span>  
 <span data-ttu-id="6b103-117">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="6b103-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b103-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b103-118">See also</span></span>
- [<span data-ttu-id="6b103-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="6b103-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6b103-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="6b103-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6b103-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="6b103-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
