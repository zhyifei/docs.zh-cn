---
title: ExportNestedTypeForwarder 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed615ea641293f8ea3fdf962e3f84d602934df60
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494683"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="8db7d-102">ExportNestedTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="8db7d-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="8db7d-103">将嵌套类型的类型转发器添加到给定的程序集的 type 表。</span><span class="sxs-lookup"><span data-stu-id="8db7d-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db7d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8db7d-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db7d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8db7d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8db7d-106">要从导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="8db7d-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8db7d-107">标记或程序集的文件 ID 定义的类型的文件。</span><span class="sxs-lookup"><span data-stu-id="8db7d-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="8db7d-108">类型的标记。</span><span class="sxs-lookup"><span data-stu-id="8db7d-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="8db7d-109">父类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="8db7d-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="8db7d-110">若要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8db7d-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8db7d-111">`ComType` 标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="8db7d-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="8db7d-112">收到的导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="8db7d-112">Receives token of export type.</span></span> <span data-ttu-id="8db7d-113">这是只需将发出嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8db7d-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8db7d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="8db7d-114">Return Value</span></span>  
 <span data-ttu-id="8db7d-115">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8db7d-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db7d-116">要求</span><span class="sxs-lookup"><span data-stu-id="8db7d-116">Requirements</span></span>  
 <span data-ttu-id="8db7d-117">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="8db7d-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db7d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8db7d-118">See also</span></span>
- [<span data-ttu-id="8db7d-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="8db7d-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8db7d-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="8db7d-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8db7d-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="8db7d-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
