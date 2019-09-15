---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 6d3c89d598714446e04ba40155951f771d474866
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971988"
---
# <a name="-delaysign"></a>-delaysign
指定程序集是完全签名的还是部分签名的。  
  
## <a name="syntax"></a>语法  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 如果需要完全签名的程序集，则使用 `-delaysign-`。 如果`-delaysign+`希望将公钥放在程序集中，并为签名的哈希保留空间，请使用。 默认值为 `-delaysign-`。  
  
## <a name="remarks"></a>备注  
 除非`-delaysign`与[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)或[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)一起使用，否则选项不起作用。  
  
 在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。 产生的数字签名存储在包含清单的文件中。 对程序集进行延迟签名时，编译器不会计算和存储签名，但会在文件中保留空间，以便以后可以添加签名。  
  
 例如，通过使用`-delaysign+`，组织中的开发人员可以分发测试人员可以向全局程序集缓存注册并使用的程序集的未签名测试版本。 在程序集上完成工作后，负责组织的私钥的人员可以对程序集进行完全签名。 此区室化可防止组织的私钥泄露，同时允许所有开发人员处理程序集。  
  
 有关对程序集进行签名的详细信息，请参阅[创建和使用具有强名称的程序集](../../../standard/assembly/create-use-strong-named.md)。  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>在 Visual Studio 集成开发环境中设置-delaysign  
  
1. 在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。   
  
2. 单击“签名”选项卡。  
  
3. 设置 "**仅延迟签名**" 框中的值。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
