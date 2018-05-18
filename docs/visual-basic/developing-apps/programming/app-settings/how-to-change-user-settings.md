---
title: 如何：在 Visual Basic 中更改用户设置
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: 2f67c3713a77c37ce43647980a9d3b17e47ba1bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>如何：在 Visual Basic 中更改用户设置
可以通过将新值赋予 `My.Settings` 对象上的设置属性来更改用户设置。  
  
 `My.Settings` 对象将每个设置公开为一个属性。 属性名称就是设置的名称，属性类型就是设置类型。 设置的“范围”决定属性是否为只读；“应用程序”范围设置的属性是只读属性，而“用户”范围设置的属性是读-写属性。 有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。  
  
> [!NOTE]
>  虽然可以在运行时更改并保存用户范围设置的值，但是应用程序范围设置是只读的，不能以编程方式进行更改。 可以在创建应用程序时通过“项目设计器”，或者编辑应用程序的配置文件来更改应用程序范围设置。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="example"></a>示例  
 此示例更改 `Nickname` 用户设置的值。  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 若要使用本示例，应用程序必须具有类型为 `String` 的 `Nickname` 用户设置。  
  
 应用程序在关闭时会保存用户设置。 若要立即保存设置，请调用 `My.Settings.Save` 方法。 有关详细信息，请参阅[如何：在 Visual Basic 中保存用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)。  
  
## <a name="see-also"></a>请参阅  
 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [如何：在 Visual Basic 中读取应用程序设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [如何：在 Visual Basic 中保存用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [如何：在 Visual Basic 中创建用户设置的属性网格](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
