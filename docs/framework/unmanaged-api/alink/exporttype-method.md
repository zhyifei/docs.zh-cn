---
title: "ExportType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportType
api_location: alink.dll
api_type: COM
f1_keywords: ExportType
helpviewer_keywords: ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f7bd3991fa57f11674b7ef0b9b62d12376fa765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="exporttype-method"></a><span data-ttu-id="9cec3-102">ExportType 方法</span><span class="sxs-lookup"><span data-stu-id="9cec3-102">ExportType Method</span></span>
<span data-ttu-id="9cec3-103">指定类型为可导出。</span><span class="sxs-lookup"><span data-stu-id="9cec3-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cec3-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cec3-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cec3-105">参数</span><span class="sxs-lookup"><span data-stu-id="9cec3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9cec3-106">要从导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="9cec3-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9cec3-107">定义可导出的类型的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="9cec3-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="9cec3-108">要成为可导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="9cec3-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="9cec3-109">要成为可导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9cec3-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9cec3-110">`ComType`标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="9cec3-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="9cec3-111">此参数可能传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="9cec3-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="9cec3-112">收到导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="9cec3-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cec3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="9cec3-113">Return Value</span></span>  
 <span data-ttu-id="9cec3-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9cec3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cec3-115">要求</span><span class="sxs-lookup"><span data-stu-id="9cec3-115">Requirements</span></span>  
 <span data-ttu-id="9cec3-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="9cec3-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cec3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cec3-117">See Also</span></span>  
 [<span data-ttu-id="9cec3-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="9cec3-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9cec3-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="9cec3-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9cec3-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="9cec3-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
