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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179418"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="a8b19-102">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="a8b19-102">ExportNestedType Method</span></span>
<span data-ttu-id="a8b19-103">将嵌套类型指定为可导出类型。</span><span class="sxs-lookup"><span data-stu-id="a8b19-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="a8b19-104">[导出类型方法](exporttype-method.md)还可以导出嵌套类型，但此方法更快。</span><span class="sxs-lookup"><span data-stu-id="a8b19-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b19-105">语法</span><span class="sxs-lookup"><span data-stu-id="a8b19-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a8b19-106">parameters</span><span class="sxs-lookup"><span data-stu-id="a8b19-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a8b19-107">要导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="a8b19-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a8b19-108">文件令牌或文件程序集，用于定义要导出的类型。</span><span class="sxs-lookup"><span data-stu-id="a8b19-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a8b19-109">类型令牌，使可导出。</span><span class="sxs-lookup"><span data-stu-id="a8b19-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a8b19-110">父类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="a8b19-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a8b19-111">要导出的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="a8b19-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a8b19-112">`ComType`标志，如`tdPublic``tdNested`或 。</span><span class="sxs-lookup"><span data-stu-id="a8b19-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="a8b19-113">此值可以传递给[定义导出类型方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a8b19-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="a8b19-114">接收导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="a8b19-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8b19-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a8b19-115">Return Value</span></span>  
 <span data-ttu-id="a8b19-116">如果方法成功，则返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="a8b19-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b19-117">要求</span><span class="sxs-lookup"><span data-stu-id="a8b19-117">Requirements</span></span>  
 <span data-ttu-id="a8b19-118">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="a8b19-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b19-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b19-119">See also</span></span>

- [<span data-ttu-id="a8b19-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="a8b19-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a8b19-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="a8b19-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a8b19-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="a8b19-122">ALink API</span></span>](index.md)
