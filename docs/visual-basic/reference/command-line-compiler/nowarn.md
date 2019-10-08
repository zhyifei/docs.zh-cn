---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005399"
---
# <a name="-nowarn"></a>-nowarn
禁止编译器生成警告的能力。  
  
## <a name="syntax"></a>语法  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`numberList`|可选。 编译器应禁止显示的警告 ID 号的逗号分隔列表。 如果未指定警告 Id，将禁止显示所有警告。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项导致编译器不会生成警告。 若要禁止显示单个警告，请将警告 ID 提供给后面跟在冒号后面的 `-nowarn` 选项。 用逗号分隔多个警告编号。  
  
 只需指定警告标识符的数值部分。 例如，如果要禁止显示 BC42024，则对未使用的局部变量指定警告，指定 `-nowarn:42024`。  
  
 有关警告 ID 号的详细信息，请参阅[在 Visual Basic 中配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
|在 Visual Studio 集成开发环境中设置-nowarn|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.选中 "**禁用所有警告**" 复选框以禁用所有警告。<br />     - 或 -<br />     若要禁用特定警告，请在警告旁边的下拉列表中单击 "**无**"。|  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb`，并且不显示任何警告。  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb`，并且不显示未使用的局部变量（42024）的警告。  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
