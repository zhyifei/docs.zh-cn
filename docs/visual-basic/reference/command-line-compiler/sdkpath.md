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
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004689"
---
# <a name="-sdkpath"></a>-sdkpath
指定 mscorlib.dll 和 Microsoft.VisualBasic.dll 的位置。  
  
## <a name="syntax"></a>语法  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>自变量  
 `path`  
 目录中包含要用于编译的 mscorlib.dll 和 Microsoft.VisualBasic.dll 的版本。 加载此路径后才会对其进行验证。 如果目录名包含空格，则将名称括在引号 (" ") 内。  
  
## <a name="remarks"></a>备注  
 此选项告诉 Visual Basic 编译器从非默认位置加载 mscorlib.dll 和 Microsoft.VisualBasic.dll 文件。 `-sdkpath` 选项专门与 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) 一起使用。 .NET Compact Framework 使用这些支持库的不同版本，以避免使用设备上没有的类型和语言功能。  
  
> [!NOTE]
> `-sdkpath` 选项在 Visual Studio 开发环境内无法使用；仅当从命令行编译时才可用。 加载 Visual Basic 设备项目时，将设置 `-sdkpath` 选项。  
  
 可以使用 `-vbruntime` 编译器选项指定：应在不引用 Visual Basic 运行时库的情况下进行编译。 有关详细信息，请参阅 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。  
  
## <a name="example"></a>示例  
 以下代码使用 C 盘上 .NET Compact Framework 的默认安装目录中的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 版本，通过 .NET Compact Framework 编译 `Myfile.vb`。 通常，会使用 .NET Compact Framework 的最新版本。  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
