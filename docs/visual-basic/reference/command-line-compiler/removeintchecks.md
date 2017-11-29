---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a>/removeintchecks
启用溢出错误检查对整数运算打开或关闭。  
  
## <a name="syntax"></a>语法  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`+` &#124; `-`|可选。 `/removeintchecks-`选项使编译器以检查所用的溢出错误的所有整数计算。 默认值为 `/removeintchecks-`。<br /><br /> 指定`/removeintchecks`或`/removeintchecks+`禁止错误检查，可以使整数计算速度更快。 但是，如果没有错误检查，而如果数据类型容量被超出，可能不会生成错误存储不正确的结果。|  
  
|在 Visual Studio 中设置 /removeintchecks 集成开发环境|  
|---|  
|1.在 “解决方案资源管理器”中选择一个项目。 在“项目”菜单上，单击“属性”。 有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。<br />2.单击“编译”选项卡。<br />3.单击 **“高级”** 按钮。<br />4.修改的值**删除整数溢出检查**框。|  
  
## <a name="example"></a>示例  
 下面的代码编译`Test.vb`和将禁用整数溢出错误检查。  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
