---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c979ada9984ef345ffbb6b5e29c2f30595c3074d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-delaysign"></a>-delaysign
指定程序集是完全签名的还是部分签名的。  
  
## <a name="syntax"></a>语法  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 如果需要完全签名的程序集，则使用 `-delaysign-`。 使用`-delaysign+`如果你想要将公钥放在有符号哈希的程序集和保留空间。 默认值为 `-delaysign-`。  
  
## <a name="remarks"></a>备注  
 `-delaysign`选项没有任何影响，除非用于[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)或[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)。  
  
 在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。 产生的数字签名存储在包含清单的文件中。 在程序集延迟签名时，编译器不会不计算和存储在文件的签名而预留空间，以便稍后可添加签名。  
  
 例如，通过使用`-delaysign+`，组织中的开发人员可以分发的程序集的测试人员可以全局程序集缓存中注册和使用的无符号的测试版本。 程序集上的工作完成后，负责组织的私钥的人员可以完全签名的程序集。 这种划分可防止组织的私钥泄露，同时允许所有开发人员能够对程序集。  
  
 请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关程序集进行签名的详细信息。  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>在 Visual Studio 集成的开发环境中设置-delaysign  
  
1.  在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。   
  
2.  单击“签名”选项卡。  
  
3.  设置中的值**仅延迟签名**框。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
