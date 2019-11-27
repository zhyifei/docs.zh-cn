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
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446518"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="cd22e-102">EmitAssemblyCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="cd22e-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="cd22e-103">调用以设置程序集级别的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="cd22e-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd22e-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd22e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cd22e-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd22e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cd22e-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="cd22e-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cd22e-107">定义属性的文件。</span><span class="sxs-lookup"><span data-stu-id="cd22e-107">File that defiles the attribute.</span></span> <span data-ttu-id="cd22e-108">如果 `AssemblyID` 不指示未绑定 .netmodule，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cd22e-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="cd22e-109">自定义属性的类型。</span><span class="sxs-lookup"><span data-stu-id="cd22e-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="cd22e-110">自定义值数据。</span><span class="sxs-lookup"><span data-stu-id="cd22e-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="cd22e-111">自定义值数据的长度。</span><span class="sxs-lookup"><span data-stu-id="cd22e-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="cd22e-112">如果自定义属性与程序集签名相关，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="cd22e-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="cd22e-113">如果要发出多个属性，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="cd22e-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd22e-114">返回值</span><span class="sxs-lookup"><span data-stu-id="cd22e-114">Return Value</span></span>  
 <span data-ttu-id="cd22e-115">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="cd22e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd22e-116">要求</span><span class="sxs-lookup"><span data-stu-id="cd22e-116">Requirements</span></span>  
 <span data-ttu-id="cd22e-117">需要 alink</span><span class="sxs-lookup"><span data-stu-id="cd22e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd22e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd22e-118">See also</span></span>

- [<span data-ttu-id="cd22e-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="cd22e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cd22e-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="cd22e-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cd22e-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="cd22e-121">ALink API</span></span>](index.md)
