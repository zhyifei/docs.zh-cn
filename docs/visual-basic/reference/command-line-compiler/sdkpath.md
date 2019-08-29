---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 25368d23c398fb3674d5c2d75d4997f917a1c3d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937356"
---
# <a name="-sdkpath"></a>-sdkpath
指定 mscorlib.dll 和 Microsoft. .dll 的位置。  
  
## <a name="syntax"></a>语法  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>自变量  
 `path`  
 包含要用于编译的 mscorlib.dll 和 Microsoft 的版本的目录。 在加载之前, 不会对其进行验证。 如果目录名称包含空格, 则将其用引号 ("") 引起来。  
  
## <a name="remarks"></a>备注  
 此选项告知 Visual Basic 编译器从非默认位置加载 mscorlib.dll 和 Microsoft. .dll 文件。 选项设计为与[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)一起使用。 `-sdkpath` .NET Compact Framework 使用这些支持库的不同版本, 以避免使用在设备上找不到的类型和语言功能。  
  
> [!NOTE]
> 此`-sdkpath`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。 加载`-sdkpath` Visual Basic 设备项目时, 设置选项。  
  
 您可以通过使用`-vbruntime`编译器选项指定编译器应编译, 而无需引用 Visual Basic 运行时库。 有关详细信息, 请参阅[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。  
  
## <a name="example"></a>示例  
 下面的代码使用`Myfile.vb` .NET Compact Framework 进行编译, 其中使用了 C 驱动器上 .NET Compact Framework 的默认安装目录中的 mscorlib.dll 和 Microsoft. .dll 版本。 通常, 您将使用最新版本的 .NET Compact Framework。  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
