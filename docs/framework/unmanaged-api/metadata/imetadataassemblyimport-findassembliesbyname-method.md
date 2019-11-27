---
title: IMetaDataAssemblyImport::FindAssembliesByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c12d3a7a7d1e52529435361aa12e22e4edeecf03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448289"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 方法
使用由公共语言运行时（CLR）用于解析引用的标准规则，获取具有指定 `szAssemblyName` 参数的程序集的数组。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>参数  
 `szAppBase`  
 中要在其中搜索给定程序集的根目录。 如果此值设置为 `null`，`FindAssembliesByName` 将仅在程序集的全局程序集缓存中查找。  
  
 `szPrivateBin`  
 中要在其中搜索程序集的根目录下以分号分隔的子目录（例如 "bin; bin2"）的列表。 除了在默认探测规则中指定的目录之外，还会探测这些目录。  
  
 `szAssemblyName`  
 中要查找的程序集的名称。 此字符串的格式在 <xref:System.Reflection.AssemblyName>的 "类引用" 页中定义。  
  
 `ppIUnk`  
 中要在其中放置 `IMetadataAssemblyImport` 接口指针的[IUnknown](/cpp/atl/iunknown)类型的数组。  
  
 `cMax`  
 弄可在 `ppIUnk`中放置的接口指针的最大数目。  
  
 `pcAssemblies`  
 弄返回的接口指针的数目。 即，实际置于 `ppIUnk`的接口指针的数目。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` 成功返回。|  
|`S_FALSE`|没有程序集。|  
  
## <a name="remarks"></a>备注  
 在给定程序集名称的情况下，`FindAssembliesByName` 方法根据解析程序集引用的标准规则查找程序集。 （有关详细信息，请参阅[运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。）`FindAssembliesByName` 允许调用方配置程序集解析程序上下文的各个方面，例如应用程序基和专用搜索路径。  
  
 `FindAssembliesByName` 方法要求在进程中初始化 CLR，以便调用程序集解析逻辑。 因此，在调用 `FindAssembliesByName`之前，必须先调用[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) （传递 COINITEE_DEFAULT），然后调用[CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。  
  
 `FindAssembliesByName` 返回一个[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指针，该指针指向包含传入的程序集名称的程序集清单的文件。 如果给定的程序集名称未完全指定（例如，如果不包含版本），则可能会返回多个程序集。  
  
 `FindAssembliesByName` 通常由尝试在编译时查找引用的程序集的编译器使用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
