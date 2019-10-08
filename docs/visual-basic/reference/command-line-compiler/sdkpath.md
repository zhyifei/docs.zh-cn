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
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004689"
---
# <a name="-sdkpath"></a>-sdkpath
指定 mscorlib.dll 和 Microsoft. .dll 的位置。  
  
## <a name="syntax"></a>语法  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>参数  
 `path`  
 包含要用于编译的 mscorlib.dll 和 Microsoft 的版本的目录。 在加载之前，不会对其进行验证。 如果目录名称包含空格，则将其用引号（""）引起来。  
  
## <a name="remarks"></a>备注  
 此选项告知 Visual Basic 编译器从非默认位置加载 mscorlib.dll 和 Microsoft. .dll 文件。 @No__t-0 选项设计为与[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)一起使用。 .NET Compact Framework 使用这些支持库的不同版本，以避免使用在设备上找不到的类型和语言功能。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-sdkpath` 选项;仅当从命令行进行编译时，它才可用。 加载 Visual Basic 设备项目时，设置 `-sdkpath` 选项。  
  
 您可以通过使用 `-vbruntime` 编译器选项指定编译器应编译，而无需引用 Visual Basic 运行时库。 有关详细信息，请参阅[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。  
  
## <a name="example"></a>示例  
 下面的代码使用 C 驱动器上 .NET Compact Framework 的默认安装目录中的 Mscorlib.dll 和 Microsoft .NET Compact Framework 的版本，将 `Myfile.vb` 编译为。 通常，您将使用最新版本的 .NET Compact Framework。  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
