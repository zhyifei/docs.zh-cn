---
title: 使用 My.Application、My.Computer 和 My.User 执行任务 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 84ac57bf1bcf60664e2b18fed16a3bbe6c03dc68
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755003"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>使用 My.Application、My.Computer 和 My.User 执行任务 (Visual Basic)
三个主要`My`对象提供对信息和常用的访问功能一起使用的是`My.Application`(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>)， `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)，和`My.User`(<xref:Microsoft.VisualBasic.ApplicationServices.User>)。 可以使用这些对象分别访问与当前应用程序、，安装应用程序的计算机或应用程序，当前用户相关的信息。  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application、 My.Computer 和 My.User  
 下面的示例演示如何能够信息检索使用`My`。  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 除了检索信息，通过这三个对象公开的成员还允许您执行与该对象相关的方法。 例如，可以访问多种方法来处理文件或更新通过注册表`My.Computer`。  
  
 文件 I/O 将变得更加容易和快速使用`My`，其中包括各种方法和属性用于操作文件、 目录和驱动器。 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>对象使用户可以从大型结构化的文件具有分隔或固定宽度的字段中读取。 此示例打开`TextFieldParser``reader`并使用它来从读取`C:\TestFolder1\test1.txt`。  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` 可以更改你的应用程序的区域性。 下面的示例演示如何调用此方法。  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [My 对项目类型的依赖方式](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
