---
title: IMetaDataImport::GetCustomAttributeByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437682"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="c0aaa-102">IMetaDataImport::GetCustomAttributeByName 方法</span><span class="sxs-lookup"><span data-stu-id="c0aaa-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="c0aaa-103">获取自定义特性（给定其名称和所有者）。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0aaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0aaa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0aaa-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0aaa-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="c0aaa-106">中一个元数据标记，它表示拥有自定义特性的对象。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="c0aaa-107">中自定义属性的名称。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="c0aaa-108">弄一个指针，它指向作为自定义属性的值的数据数组。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c0aaa-109">弄在 \*`ppData`中返回的数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0aaa-110">备注</span><span class="sxs-lookup"><span data-stu-id="c0aaa-110">Remarks</span></span>  
 <span data-ttu-id="c0aaa-111">为同一个所有者定义多个自定义属性是合法的;它们甚至可能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="c0aaa-112">但 `GetCustomAttributeByName` 仅返回一个实例。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="c0aaa-113">（`GetCustomAttributeByName` 返回它遇到的第一个实例。）若要查找自定义属性的所有实例，请调用[IMetaDataImport：： EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0aaa-114">要求</span><span class="sxs-lookup"><span data-stu-id="c0aaa-114">Requirements</span></span>  
 <span data-ttu-id="c0aaa-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0aaa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0aaa-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c0aaa-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0aaa-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c0aaa-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0aaa-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0aaa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0aaa-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0aaa-119">See also</span></span>

- [<span data-ttu-id="c0aaa-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c0aaa-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c0aaa-121">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c0aaa-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
