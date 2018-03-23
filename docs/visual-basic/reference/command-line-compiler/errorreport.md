---
title: -errorreport
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59dc833299161eac7b119e654c94534f202b1cb7
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-errorreport"></a>-errorreport
指定 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器应报告内部编译器错误的方式。  
  
## <a name="syntax"></a>语法  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>备注  
 此选项可以方便地向报表[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]到内部编译器错误 (ICE) [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Microsoft 团队。 默认情况下，编译器会向 Microsoft 发送任何信息。 但是，如果您遇到内部编译器错误，此选项允许你向 Microsoft 报告错误。 该信息将帮助 Microsoft 工程师确定原因以及可帮助改善的下一个版本[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
 发送报表用户的能力取决于计算机和用户策略权限。  
  
 下表总结了的效果`-errorreport`选项。  
  
|选项|行为|  
|---|---|  
|`prompt`|如果发生内部编译器错误，弹出对话框，以便你可以查看编译器收集的确切数据。 你可以判断是否有任何错误报告中的敏感信息和做出决策的是否将其发送给 Microsoft。 如果你决定发送它，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。|  
|`queue`|将错误报告排入队列。 当使用管理员特权登录时，可以报告自上次登录以来的任何故障 （你不会提示发送故障报告一次以上每隔三天）。 这是默认行为时`-errorreport`未指定选项。|  
|`send`|如果发生内部编译器错误，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。<br /><br /> 选项`-errorreport:send`尝试自动向 Microsoft 发送错误的信息。 此选项将依赖于注册表中。 有关在注册表中设置适当的值的详细信息，请参阅[如何自动错误报告在 Visual Studio 2008 命令行工具中打开](http://go.microsoft.com/fwlink/?LinkID=184695)。|  
|`none`|如果发生内部编译器错误，它不会收集或发送给 Microsoft。|  
  
 编译器将发送一个错误，它通常包含某些源代码时包括堆栈的数据。 如果`-errorreport`用于[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，然后发送整个源文件。  
  
 此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它可让 Microsoft 工程师能更轻松地再现错误。  
  
> [!NOTE]
>  `-errorreport`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码尝试编译`T2.vb`，如果编译器遇到内部编译器错误，它会提示你向 Microsoft 发送错误报告。  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
