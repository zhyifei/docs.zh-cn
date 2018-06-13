---
title: _CorValidateImage 函数
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101271823f7b7877bb7f007588b6a164233e5b45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432372"
---
# <a name="corvalidateimage-function"></a>_CorValidateImage 函数
验证托管的模块映像，并通知操作系统加载程序后将其加载。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ImageBase`  
 [in]指向要验证的图像的起始位置的托管代码。 该映像必须已加载到内存中。  
  
 `FileName`  
 [in]图像的文件名。  
  
## <a name="return-value"></a>返回值  
 此函数将返回的标准值`E_INVALIDARG`， `E_OUTOFMEMORY`， `E_UNEXPECTED`，和`E_FAIL`，以及以下值。  
  
|返回值|描述|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|该映像已无效。 此值具有 HRESULT 0xC000007BL。|  
|`STATUS_SUCCESS`|映像是有效的。 此值具有 HRESULT 0x00000000L。|  
  
## <a name="remarks"></a>备注  
 在 Windows XP 和更高版本中，操作系统加载程序通过检查常见对象文件格式 (COFF) 标头中的 COM 描述符目录位检查托管模块。 一个设置位指示的托管的模块。 如果加载程序检测到的托管的模块，它将加载 MsCorEE.dll 和调用`_CorValidateImage`，这将执行以下操作：  
  
-   确认该图像是有效的托管的模块。  
  
-   更改为公共语言运行时 (CLR) 中的入口点的映像中的入口点。  
  
-   对于 64 位版本的 Windows，修改通过将其从 PE32 转换为 PE32 + 格式是内存中的映像。  
  
-   返回到加载程序加载托管的模块映像时。  
  
 对于可执行映像，操作系统加载程序然后调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数，而不考虑可执行文件中指定的入口点。 对于 DLL 的程序集图像，加载程序将调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。  
  
 `_CorExeMain` 或`_CorDllMain`执行下列操作：  
  
-   初始化 CLR。  
  
-   查找程序集的 CLR 标头中的托管的入口点。  
  
-   开始执行。  
  
 加载程序调用[_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)函数时托管模块映像将被卸载。 但是，此函数不执行任何操作;它只返回。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
