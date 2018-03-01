---
title: "ExportNestedType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6d40fffb2d40012d69599ad1bfcdbdaf454aa02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="49e65-102">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="49e65-102">ExportNestedType Method</span></span>
<span data-ttu-id="49e65-103">为可导出指定嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="49e65-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="49e65-104">[ExportType 方法](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)还可以导出嵌套类型，但此方法也越快。</span><span class="sxs-lookup"><span data-stu-id="49e65-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e65-105">语法</span><span class="sxs-lookup"><span data-stu-id="49e65-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="49e65-106">参数</span><span class="sxs-lookup"><span data-stu-id="49e65-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="49e65-107">要从导出程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="49e65-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="49e65-108">文件的标记或定义的类型，要成为可导出的文件的程序集。</span><span class="sxs-lookup"><span data-stu-id="49e65-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="49e65-109">键入要成为可导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="49e65-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="49e65-110">父类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="49e65-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="49e65-111">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="49e65-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="49e65-112">`ComType`标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="49e65-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="49e65-113">此值可能会传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="49e65-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="49e65-114">收到导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="49e65-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49e65-115">返回值</span><span class="sxs-lookup"><span data-stu-id="49e65-115">Return Value</span></span>  
 <span data-ttu-id="49e65-116">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="49e65-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e65-117">惠?</span><span class="sxs-lookup"><span data-stu-id="49e65-117">Requirements</span></span>  
 <span data-ttu-id="49e65-118">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="49e65-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e65-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="49e65-119">See Also</span></span>  
 [<span data-ttu-id="49e65-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="49e65-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="49e65-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="49e65-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="49e65-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="49e65-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
