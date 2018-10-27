---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 89f6566bd733ff92d464c026102429d3fc5cf0c1
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50047847"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
使编译器将第一个匹配项的警告视为错误。  
  
## <a name="syntax"></a>语法  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|+ &#124; -|可选。 默认情况下，`-warnaserror-`是有效; 警告不会阻止编译器生成的输出文件。 `-warnaserror`选项，这是相同作为`-warnaserror+`，导致将警告视为错误。|  
|`numberList`|可选。 警告 ID 以逗号分隔列表数字到`-warnaserror`选项适用。 如果不指定了任何警告 ID，`-warnaserror`选项适用于所有警告。|  
  
## <a name="remarks"></a>备注  
 `-warnaserror`选项将所有警告视为错误。 任何将通常报告为警告被报告为错误的消息。 编译器会报告为警告相同的警告的后续匹配项。  
  
 默认情况下，`-warnaserror-`将起作用，导致只能是信息性警告。 `-warnaserror`选项，这是相同作为`-warnaserror+`，导致将警告视为错误。  
  
 如果您希望仅将一些特定警告视为错误，则可以指定逗号分隔警告编号，以将视为错误的列表。  
  
> [!NOTE]
>  `-warnaserror`选项不控制警告的显示方式。 使用[-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)选项来禁用警告。  
  
|若要设置-warnaserror 将所有警告都视为错误，Visual Studio IDE 中|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.请确保**禁用所有警告**复选框处于未选中状态。<br />4.检查**将所有警告视为错误**复选框。|  
  
|若要设置-warnaserror 将特定警告视为错误，Visual Studio IDE 中|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。<br />2.单击“编译”选项卡。<br />3.请确保**禁用所有警告**复选框处于未选中状态。<br />4.请确保**将所有警告视为错误**复选框处于未选中状态。<br />5.选择**错误**从**通知**应视为错误的警告旁边的列。|  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`并指示编译器显示错误会在每个警告的第一个匹配项。  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`和仅对未使用的本地变量 (42024) 的警告视为错误。  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
