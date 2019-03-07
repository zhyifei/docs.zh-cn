---
title: ExportTypeForwarder 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 737f4600d04a4fa443fbd5b422b26eff11178d82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473534"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="3ceb4-102">ExportTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="3ceb4-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="3ceb4-103">将类型转发器添加到给定的程序集的 type 表。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ceb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ceb4-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ceb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ceb4-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="3ceb4-106">类型转发器所引用的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3ceb4-107">若要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3ceb4-108">`ComType` 标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="3ceb4-109">此值可能会传递到[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="3ceb4-110">接收导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-110">Receives the token of the exported type.</span></span> <span data-ttu-id="3ceb4-111">这是只需将发出嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ceb4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="3ceb4-112">Return Value</span></span>  
 <span data-ttu-id="3ceb4-113">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3ceb4-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ceb4-114">要求</span><span class="sxs-lookup"><span data-stu-id="3ceb4-114">Requirements</span></span>  
 <span data-ttu-id="3ceb4-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="3ceb4-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ceb4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ceb4-116">See also</span></span>
- [<span data-ttu-id="3ceb4-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="3ceb4-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3ceb4-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="3ceb4-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3ceb4-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="3ceb4-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
