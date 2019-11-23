---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005225"
---
# <a name="-removeintchecks"></a>-removeintchecks
启用或禁用对整数操作的溢出错误检查。  
  
## <a name="syntax"></a>语法  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>参数  
  
|术语|Definition|  
|---|---|  
|`+` &#124; `-`|可选。 `-removeintchecks-` 选项导致编译器检查所有整数计算是否存在溢出错误。 默认值为 `-removeintchecks-`。<br /><br /> 指定 `-removeintchecks` 或 `-removeintchecks+` 可防止错误检查并可以更快地进行整数计算。 但是，如果不进行错误检查，且数据类型容量溢出，则可能会存储不正确的结果，而不会引发错误。|  
  
|在 Visual Studio 集成开发环境中设置-removeintchecks|  
|---|  
|1. 在**解决方案资源管理器**中选择了一个项目。 在“项目”菜单上，单击“属性”。 <br />2. 单击 "**编译**" 选项卡。<br />3. 单击 "**高级**" 按钮。<br />4. 修改 "**删除整数溢出检查**" 框的值。|  
  
## <a name="example"></a>示例  
 下面的代码编译 `Test.vb` 并关闭整数溢出错误检查。  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
