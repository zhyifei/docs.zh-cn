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
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789943"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="f6d5c-102">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="f6d5c-102">ExportNestedType Method</span></span>
<span data-ttu-id="f6d5c-103">指定为可导出的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="f6d5c-104">[ExportType 方法](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)还可以导出嵌套类型，但此方法速度更快。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6d5c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f6d5c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f6d5c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f6d5c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f6d5c-107">若要从导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f6d5c-108">文件标记或程序集的文件，用于定义要成为可导出的类型。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f6d5c-109">键入要成为可导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="f6d5c-110">父类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f6d5c-111">若要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f6d5c-112">`ComType` 标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="f6d5c-113">此值可能会传递到[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="f6d5c-114">接收导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6d5c-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f6d5c-115">Return Value</span></span>  
 <span data-ttu-id="f6d5c-116">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f6d5c-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6d5c-117">要求</span><span class="sxs-lookup"><span data-stu-id="f6d5c-117">Requirements</span></span>  
 <span data-ttu-id="f6d5c-118">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="f6d5c-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d5c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6d5c-119">See also</span></span>

- [<span data-ttu-id="f6d5c-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f6d5c-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f6d5c-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f6d5c-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f6d5c-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="f6d5c-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
