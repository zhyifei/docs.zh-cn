---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961301"
---
# <a name="-win32resource"></a>-win32resource
将 Win32 资源文件插入到输出文件中。  
  
## <a name="syntax"></a>语法  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>自变量  
 `filename`  
 要添加到输出文件的资源文件的名称。 如果文件名包含空格, 请将文件名用引号 ("") 引起来。  
  
## <a name="remarks"></a>备注  
 您可以使用 Microsoft Windows 资源编译器 (RC) 创建 Win32 资源文件。  
  
 Win32 资源可以包含版本或位图 (图标) 信息, 这些信息有助于在**文件资源管理器**中标识您的应用程序。 如果不指定`-win32resource`, 则编译器将根据程序集版本生成版本信息。 `-win32resource` 和`-win32icon`选项是互斥的。  
  
 请参阅[-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)以引用 .NET Framework 资源文件或[-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)来附加 .NET Framework 资源文件。  
  
> [!NOTE]
> 此`-win32resource`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`并附加 Win32 资源`Rf.res`文件:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
