---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 0383a5e369ee4a8146764c13b2f12f48ebe52190
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-bugreport"></a>-bugreport
创建文件一个 bug 报告时，可以使用一个文件。  
  
## <a name="syntax"></a>语法  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`file`|必须的。 将包含 bug 报告文件的名称。 将文件名括在双引号 ("") 如果名称包含空格。|  
  
## <a name="remarks"></a>备注  
 以下信息添加到`file`:  
  
-   编译中所有源代码文件的副本。  
  
-   用编译中使用的编译器选项的列表。  
  
-   有关编译器、 公共语言运行时和操作系统的版本信息。  
  
-   编译器输出（如有）。  
  
-   此问题，提示你的说明。  
  
-   应修复您的想法问题的说明，提示你。  
  
 因为所有源代码文件的副本包含在`file`，你可能想要重现尽可能短的程序中 （可疑的） 代码缺陷。  
  
> [!IMPORTANT]
>  `-bugreport`选项生成包含潜在敏感信息的文件。 这包括当前时间，编译器版本[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]版本、 操作系统版本、 用户名称、 命令行自变量，可编译器已运行，所有源代码和二进制形式的任何引用程序集。 可以通过指定的服务器端编译的 Web.config 文件中的命令行选项来访问此选项[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]应用程序。 若要防止此情况，修改要禁止在服务器上进行编译的用户的 Machine.config 文件。  
  
 如果此选项用于`-errorreport:prompt`， `-errorreport:queue`，或`-errorreport:send`，并且你的应用程序遇到内部编译器错误中的信息`file`发送到 Microsoft Corporation。 该信息将帮助确定错误原因的 Microsoft 工程师，并且可能帮助改进 Visual Basic 的下一个版本。 默认情况下，任何信息不发送给 Microsoft。 但是，当你编译应用程序使用`-errorreport:queue`，这默认启用的应用程序收集其错误报告。 然后，在计算机的管理员登录，错误报告系统将显示一个弹出窗口，使管理员能够将转发给 Microsoft 自登录以来发生的任何错误报告。  
  
> [!NOTE]
>  `/bugreport`选项不是可从 Visual Studio 开发环境中; 它是可用仅编译时从命令行。  
  
## <a name="example"></a>示例  
 下面的示例将编译`T2.vb`并放置在文件的所有 bug 报告信息`Problem.txt`。  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-调试 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [trustLevel 元素为 securityPolicy （ASP.NET 设置架构）](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
