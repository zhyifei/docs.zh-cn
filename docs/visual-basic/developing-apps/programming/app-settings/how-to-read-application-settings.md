---
title: 如何：在 Visual Basic 中读取应用程序设置
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 3de6e59c2a69c430a0376ef36f8ce52e57f5f6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>如何：在 Visual Basic 中读取应用程序设置
可以通过访问 `My.Settings` 对象上用户设置的属性来读取该设置。  
  
 `My.Settings` 对象将每个设置公开为一个属性。 属性名称就是设置的名称，属性类型就是设置类型。 设置的“范围”指示属性是否为只读；“应用程序”范围设置的属性是只读属性，而“用户”范围设置的属性是读-写属性。 有关详细信息，请参阅 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)。  
  
## <a name="example"></a>示例  
 此示例显示 `Nickname` 设置的值。  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 若要使此示例正常工作，应用程序必须具有类型为 `String` 的 `Nickname` 设置。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="see-also"></a>请参阅  
 [My.Settings 对象](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [如何：在 Visual Basic 中更改用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [如何：在 Visual Basic 中保存用户设置](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [如何：在 Visual Basic 中创建用户设置的属性网格](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
