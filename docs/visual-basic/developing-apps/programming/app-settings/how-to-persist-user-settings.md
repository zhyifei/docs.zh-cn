---
title: "如何：在 Visual Basic 中保存用户设置"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e1cf424a4e587818a8e2766a5e27c084010c084c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>如何：在 Visual Basic 中保存用户设置
可以使用 `My.Settings.Save` 方法来保存对用户设置的更改。  
  
 通常情况下，将应用程序设计为在应用程序关闭时保存用户设置的更改。 这是因为保存设置需要几秒钟，具体取决于多种因素。  
  
 有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。  
  
> [!NOTE]
>  虽然可以在运行时更改并保存用户范围设置的值，但是应用程序范围设置是只读的，不能以编程方式进行更改。 可以在创建应用程序时通过**项目设计器**，或者编辑应用程序的配置文件来更改应用程序范围设置。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="example"></a>示例  
 本示例更改 `LastChanged` 用户设置的值，并通过调用 `My.Settings.Save` 方法来保存此更改。  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 若要使用本示例，应用程序必须具有类型为 `Date` 的 `LastChanged` 用户设置。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="see-also"></a>另请参阅  
 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [如何：在 Visual Basic 中读取应用程序设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [如何：在 Visual Basic 中更改用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [如何：在 Visual Basic 中创建用户设置的属性网格](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
