---
title: /warnaserror (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d472795affe0df098d1551daf51a2f0ae20723ba
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="warnaserror-visual-basic"></a>/warnaserror (Visual Basic)
使编译器将视为错误的警告的第一个匹配项。  
  
## <a name="syntax"></a>语法  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|+ &#124; -|可选。 默认情况下，`/warnaserror-`是有效，则警告不会阻止编译器生成的输出文件。 `/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。|  
|`numberList`|可选。 以逗号分隔列表的警告 ID 号到`/warnaserror`选项适用。 如果不指定任何警告 ID，则`/warnaserror`选项适用于所有警告。|  
  
## <a name="remarks"></a>备注  
 `/warnaserror`选项将所有警告视为错误。 任何将通常报告为警告而是会报告为错误的消息。 编译器将报告为警告相同的警告的后续匹配项。  
  
 默认情况下，`/warnaserror-`是起作用，这会导致仅为信息性的警告。 `/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。  
  
 如果你想仅几个特定警告视为错误，则可以指定逗号分隔警告编号，以将视为错误的列表。  
  
> [!NOTE]
>  `/warnaserror`选项不控制如何显示警告。 使用[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)选项来禁用的警告。  
  
|若要设置 /warnaserror 将所有警告视为 Visual Studio IDE 中的错误|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.请确保**禁用所有警告**复选框处于未选中状态。<br />4.检查**将所有警告视为错误**复选框。|  
  
|若要设置 /warnaserror 特定警告视为在 Visual Studio IDE 中的错误|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。<br />2.单击“编译”选项卡。<br />3.请确保**禁用所有警告**复选框处于未选中状态。<br />4.请确保**将所有警告视为错误**复选框处于未选中状态。<br />5.选择**错误**从**通知**应被视为错误的警告旁边的列。|  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`并指示编译器显示找到的每个警告的第一个匹配项错误。  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`，并将仅对未使用的局部变量 (42024) 警告视为错误。  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [在 Visual Basic 中配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)
