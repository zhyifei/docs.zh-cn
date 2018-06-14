---
title: -nostdlib（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216130"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib（C# 编译器选项）
-nostdlib 可防止导入 mscorlib.dll，后者定义了整个 System 命名空间。  
  
## <a name="syntax"></a>语法  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>备注  
 如果你想要定义或创建自己的 System 命名空间和对象，请使用此选项。  
  
 如果未指定 -nostdlib，则 mscorlib.dll 将被导入到程序中（与指定 -nostdlib- 相同）。 指定 -nostdlib 与指定 -nostdlib+ 相同。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1.  打开项目的“属性”  页。  
  
2.  单击“生成”  属性页。  
  
3.  单击 **“高级”** 按钮。  
  
4.  修改“不引用 mscorlib.dll”  属性。  
  
 有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>。  
  
## <a name="see-also"></a>请参阅  
 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)
