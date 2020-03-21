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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177805"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 方法
使用通用语言运行时 （CLR） 采用的标准规则解析引用，获取具有指定`szAssemblyName`参数的程序集数组。  
  
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
  
## <a name="parameters"></a>parameters  
 `szAppBase`  
 [在]要在其中搜索给定程序集的根目录。 如果此值设置为`null`，`FindAssembliesByName`将仅在程序集的全局程序集缓存中查找。  
  
 `szPrivateBin`  
 [在]在根目录下搜索程序集的分号分隔子目录（例如，"bin;bin2"）的列表。 除了默认探测规则中指定的目录外，这些目录还被探测。  
  
 `szAssemblyName`  
 [在]要查找的程序集的名称。 此字符串的格式在 的类引用页中<xref:System.Reflection.AssemblyName>定义。  
  
 `ppIUnk`  
 [在]放置`IMetadataAssemblyImport`接口指针的[I 未知](/cpp/atl/iunknown)类型的数组。  
  
 `cMax`  
 [出]可放置在 中的最大接口指针数`ppIUnk`。  
  
 `pcAssemblies`  
 [出]返回的接口指针数。 也就是说，实际上放置在 中的`ppIUnk`接口指针数。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`已成功返回。|  
|`S_FALSE`|没有程序集。|  
  
## <a name="remarks"></a>备注  
 给定程序集名称，`FindAssembliesByName`该方法通过遵循解析程序集引用的标准规则来查找程序集。 （有关详细信息，请参阅[运行时如何查找程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。`FindAssembliesByName`允许调用方配置程序集解析器上下文的各个方面，如应用程序库和专用搜索路径。  
  
 该方法`FindAssembliesByName`要求在进程中初始化 CLR，以便调用程序集解析逻辑。 因此，在调用`FindAssembliesByName`之前必须调用[Co初始化EEE（](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)传递COINITEE_DEFAULT），然后调用[CoUn初始化Cor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。  
  
 `FindAssembliesByName`返回[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指针，指向包含传入的程序集名称的程序集清单的文件。 如果未完全指定给定程序集名称（例如，如果不包括版本），则可能会返回多个程序集。  
  
 `FindAssembliesByName`尝试在编译时查找引用程序集的编译器通常使用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
