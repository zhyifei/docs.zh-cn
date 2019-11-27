---
title: My.Settings 对象
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350358"
---
# <a name="mysettings-object"></a>My.Settings 对象
提供用于访问应用程序设置的属性和方法。  
  
## <a name="remarks"></a>备注  
 `My.Settings` 对象提供对应用程序设置的访问权限，并允许您动态存储和检索应用程序的属性设置和其他信息。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="properties"></a>属性  
 `My.Settings` 对象的属性提供对应用程序设置的访问。 若要添加或删除设置，请使用 "**设置设计器**"。  
  
 每个设置都具有**名称**、**类型**、**作用域**和**值**，并且这些设置确定如何在 `My.Settings` 对象中显示每个设置的属性：  
  
- **名称**确定属性的名称。  
  
- **类型**确定属性的类型。  
  
- **Scope**指示属性是否为只读。 如果值为 "**应用程序**"，则属性是只读的;如果值是**User**，则属性是可读写的。  
  
- **值**是属性的默认值。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|---|---|  
|`Reload`|重新加载上次保存的值中的用户设置。|  
|`Save`|保存当前用户设置。|  
  
 `My.Settings` 对象还提供从 <xref:System.Configuration.ApplicationSettingsBase> 类继承的高级属性和方法。  
  
## <a name="tasks"></a>任务  
 下表列出了涉及 `My.Settings` 对象的任务示例。  
  
|至|请参阅|  
|---|---|  
|读取应用程序设置|[如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|更改用户设置|[如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|持久保存用户设置|[如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|创建用户设置的属性网格|[如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>示例  
 此示例显示 `Nickname` 设置的值。  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 若要使此示例正常工作，应用程序必须具有类型为 `Nickname` 的 `String` 设置。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.ApplicationSettingsBase>
- [如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
