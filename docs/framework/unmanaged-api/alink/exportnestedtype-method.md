---
title: ExportNestedType 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0afe4daa1c85f3e15addac55bdbe631d40e03f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407554"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="0c531-102">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="0c531-102">ExportNestedType Method</span></span>
<span data-ttu-id="0c531-103">为可导出指定嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="0c531-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="0c531-104">[ExportType 方法](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)还可以导出嵌套类型，但此方法也越快。</span><span class="sxs-lookup"><span data-stu-id="0c531-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c531-105">语法</span><span class="sxs-lookup"><span data-stu-id="0c531-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0c531-106">参数</span><span class="sxs-lookup"><span data-stu-id="0c531-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0c531-107">要从导出程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="0c531-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0c531-108">文件的标记或定义的类型，要成为可导出的文件的程序集。</span><span class="sxs-lookup"><span data-stu-id="0c531-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="0c531-109">键入要成为可导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="0c531-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="0c531-110">父类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="0c531-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="0c531-111">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="0c531-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0c531-112">`ComType` 标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="0c531-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="0c531-113">此值可能会传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0c531-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="0c531-114">收到导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="0c531-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c531-115">返回值</span><span class="sxs-lookup"><span data-stu-id="0c531-115">Return Value</span></span>  
 <span data-ttu-id="0c531-116">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0c531-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c531-117">要求</span><span class="sxs-lookup"><span data-stu-id="0c531-117">Requirements</span></span>  
 <span data-ttu-id="0c531-118">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="0c531-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c531-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c531-119">See Also</span></span>  
 [<span data-ttu-id="0c531-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0c531-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0c531-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0c531-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0c531-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="0c531-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
