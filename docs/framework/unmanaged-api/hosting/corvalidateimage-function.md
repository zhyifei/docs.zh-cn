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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178220"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage 函数
验证托管模块映像，并在加载操作系统加载器后通知它们。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>parameters  
 `ImageBase`  
 [在]指向映像的起始位置的指针，以验证为托管代码。 图像必须已加载到内存中。  
  
 `FileName`  
 [在]图像的文件名。  
  
## <a name="return-value"></a>返回值  
 此函数返回标准`E_INVALIDARG`值`E_OUTOFMEMORY`、和`E_UNEXPECTED` `E_FAIL`，以及以下值。  
  
|返回值|说明|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|图像无效。 此值具有 HRESULT 0xC000007BL。|  
|`STATUS_SUCCESS`|图像有效。 此值具有 HRESULT 0x0000000L。|  
  
## <a name="remarks"></a>备注  
 在 Windows XP 和更高版本中，操作系统加载程序通过检查公共对象文件格式 （COFF） 标头中的 COM 描述符目录位来检查托管模块。 设置位表示托管模块。 如果加载程序检测到托管模块，它将加载 MsCorEE.dll 和调用`_CorValidateImage`，这将执行以下操作：  
  
- 确认映像是有效的托管模块。  
  
- 将图像中的入口点更改为通用语言运行时 （CLR） 中的入口点。  
  
- 对于 64 位版本的 Windows，通过将映像从 PE32 转换为 PE32+ 格式来修改内存中的图像。  
  
- 加载托管模块映像时返回加载程序。  
  
 对于可执行映像，操作系统加载程序然后调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数，而不考虑可执行文件中指定的入口点。 对于 DLL 装配体映像，加载程序调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。  
  
 `_CorExeMain`或`_CorDllMain`执行以下操作：  
  
- 初始化 CLR。  
  
- 从程序集的 CLR 标头中查找托管入口点。  
  
- 开始执行。  
  
 卸载托管模块映像时，加载程序调用[_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)函数。 但是，此函数不执行任何操作;因此，此操作不会执行任何操作。它只是返回。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
